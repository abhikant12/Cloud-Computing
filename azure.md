 
---

## ✅ **Demo 1: Reading Data from Azure SQL Database**

### 🔍 Code Breakdown:

```scala
val jdbcUsername = "infyadmin"
val jdbcPassword = "Password@1234"
val jdbcHostname = "vtechserver.database.windows.net"
val jdbcPort = 1433
val jdbcDatabase ="vtechdb"
```

* These are connection credentials and parameters for the Azure SQL Database.

```scala
import java.util.Properties
val jdbc_url = s"jdbc:sqlserver://${jdbcHostname}:${jdbcPort};database=${jdbcDatabase}"
```

* Creates the JDBC URL using the hostname, port, and DB name.

```scala
val connectionProperties = new Properties()
connectionProperties.put("user", s"${jdbcUsername}")
connectionProperties.put("password", s"${jdbcPassword}")
```

* Sets authentication properties (username and password) for SQL connection.

```scala
val sqlTableDF = spark.read.jdbc(jdbc_url, "dbo.VehicleDetails", connectionProperties)
sqlTableDF.show()
```

* Connects to the `VehicleDetails` table and displays its contents.

---

## 📝 **Short Notes: Azure SQL**

* Use `spark.read.jdbc()` to connect to SQL.
* JDBC URL format: `jdbc:sqlserver://<hostname>:<port>;database=<dbname>`
* Authentication via `Properties()` (user/password).
* `.show()` displays the dataframe.

---

## ✅ **Demo 2: Reading Data from Azure Blob Storage**

### 🔍 Code Breakdown:

```scala
dbutils.fs.mount(
  source = "wasbs://datacontainer@datatechstore.blob.core.windows.net/",
  mountPoint = "/mnt/mypath",
  extraConfigs = Map("fs.azure.account.key.datatechstore.blob.core.windows.net" ->
  "<storage_account_key>"))
```

* Mounts the blob container to Databricks File System (DBFS).

```sql
DROP TABLE IF EXISTS VehicleInfo;
CREATE TABLE VehicleInfo
USING json
OPTIONS (path "/mnt/mypath/VehcleDetails.json")
```

* Creates a SQL table from JSON file.

```sql
select * from VehicleInfo
```

* Reads all data from the newly created table.

---

## 📝 **Short Notes: Azure Blob**

* `dbutils.fs.mount()` mounts blob storage.
* `wasbs://<container>@<account>.blob.core.windows.net/` is the mount source.
* Tables can be created using SQL from JSON/CSV in mounted path.
* Use `USING json OPTIONS(path "<path>")` to create external table.

---

## ✅ **Demo 3: Using Azure Databricks with Azure Data Factory**

### 🔍 Code Breakdown:

```scala
spark.conf.set("dfs.adls.oauth2.client.id", "<APP-ID>")
spark.conf.set("dfs.adls.oauth2.credential", "<KEY>")
spark.conf.set("dfs.adls.oauth2.refresh.url", "https://login.microsoftonline.com/<TENANT-ID>/oauth2/token")
```

* Sets credentials for Azure Data Lake using OAuth2 authentication.

```scala
val customerDetails = spark.read.json("adl://datavtech.azuredatalakestore.net/datacontainer/CustomerDetails-VtechBranchOne.json")
customerDetails.show()
```

* Reads a JSON file from Azure Data Lake Store.

```scala
val specificColumns = customerDetails.select("CustomerId", "VehicleId", "DateOfPurchase")
```

* Selects only required columns.

---

## 📝 **Short Notes: Data Factory + Data Lake**

* Use OAuth2 credentials for secure access.
* Read JSON from Data Lake using `spark.read.json(<path>)`.
* Use `.select(<columns>)` for filtering relevant data.

---

## ✅ **Demo 4: Basic Transformations**

### 🔍 Code Breakdown:

```scala
val specificColumns = vehicleDetails.select("VehicleName", "QuantityAvailable", "Price")
val renamedColumn = specificColumns.withColumnRenamed("Price", "VehiclePrice")
```

* Selects specific fields and renames the column.

```scala
val blobStorage = "vtechstorage.blob.core.windows.net"
val tempDir = "wasbs://" + blobContainer + "@" + blobStorage +"/tempDirs"
sc.hadoopConfiguration.set(acntInfo, blobAccessKey)
```

* Sets up temporary storage path and access to blob.

```scala
val sqlDwUrlSmall = "jdbc:sqlserver://vtech-server.database.windows.net:1433;database=vtechdw;user=vtechuser;password=password@123"
```

* Builds connection URL for Azure SQL Data Warehouse.

```scala
renamedColumn.write
.format("com.databricks.spark.sqldw")
.option("url", sqlDwUrlSmall)
.option("dbtable", "VehicleDetails")
.option("tempdir", tempDir)
.mode("overwrite")
.save()
```

* Writes data to SQL Data Warehouse.

---

## 📝 **Short Notes: Transformations**

* `.withColumnRenamed()` changes column name.
* `.select()` extracts columns.
* `spark.write.format("com.databricks.spark.sqldw")` for DW writing.
* Use `.mode("overwrite")` to replace existing table.

---

## ✅ **Demo 5: Advanced Transformation using UDF**

### 🔍 Code Breakdown:

```scala
def CalculateDiscount(price: Double, discount: Double): Double = price - (discount / 100 * price)
val discountUDF = udf[Double, Double, Double](CalculateDiscount)
spark.udf.register("discount_UDF", discountUDF)
```

* Defines a local function and registers it as a User Defined Function (UDF).

```scala
vehicleDetails.createOrReplaceTempView("vehicle_table")
spark.sql("select VehicleId,Price,discount_UDF(Price,20) as DicountedPrice from vehicle_table").show()
```

* Calls the UDF in SQL to apply a 20% discount.

---

## 📝 **Short Notes: UDF**

* Use `udf[ReturnType, Arg1Type, Arg2Type](function)` to define UDF.
* Register with `spark.udf.register()`.
* UDFs are used in SQL via `select <udf>(col1, col2)`.

---

## ✅ **Demo 6: Join Operation**

### 🔍 Code Breakdown:

```scala
val vehicleDetails = spark.read.json("adl://.../VehicleDetails.json").as("vehicle")
val customerDetails = spark.read.json("adl://.../CustomerDetails.json").as("customer")
```

* Reads both datasets from Data Lake and assigns aliases.

```scala
val customerResult = vehicleDetails.join(customerDetails).where($"vehicle.VehicleId" === $"customer.VehicleId")
customerResult.select("CustomerId", "VehicleName", "DateOfPurchase").show()
```

* Joins on `VehicleId` and selects fields.

```scala
vehicleDetails.createOrReplaceTempView("VehicleView")
customerDetails.createOrReplaceTempView("CustomerView")
spark.sql("SELECT * FROM CustomerView c JOIN VehicleView v ON c.VehicleId = v.VehicleId").show()
```

* Performs same join using SQL view.

---

## 📝 **Short Notes: Joins**

* `.join()` used for DataFrame join.
* Use `.where()` or `.on()` to specify join condition.
* SQL joins require temp views using `.createOrReplaceTempView()`.
* SQL syntax: `SELECT ... FROM A JOIN B ON A.col = B.col`.

---

## ⚡ Final Quick Revision Sheet for MCQs

| **Topic**                  | **Key Syntax / Concept**                                       |
| -------------------------- | -------------------------------------------------------------- |
| Connect to SQL             | `spark.read.jdbc(jdbcUrl, table, properties)`                  |
| Mount Blob Storage         | `dbutils.fs.mount()` with `wasbs://` and account key           |
| Read JSON from Blob        | `spark.read.json("/mnt/path/file.json")`                       |
| Create SQL Table from JSON | `CREATE TABLE ... USING json OPTIONS (path "...")`             |
| OAuth2 Config for ADLS     | `spark.conf.set("dfs.adls.oauth2...")`                         |
| Select columns             | `df.select("col1", "col2")`                                    |
| Rename column              | `df.withColumnRenamed("old", "new")`                           |
| UDF                        | `val myUdf = udf(function); spark.udf.register("name", myUdf)` |
| Join                       | `df1.join(df2).where(df1("id") === df2("id"))`                 |
| Write to SQL DW            | `df.write.format("com.databricks.spark.sqldw")...save()`       |
| Create Temp View           | `df.createOrReplaceTempView("view_name")`                      |
| SQL Join                   | `SELECT * FROM A JOIN B ON A.col = B.col`                      |

---

 
