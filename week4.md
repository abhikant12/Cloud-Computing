### 🔹 **IIT KGP On-Premise Cloud (Meghamala) using OpenStack Framework**
- **VM Creation:** Users can create Virtual Machines (VMs) via OpenStack Horizon Dashboard or CLI.
- **Accessing VM:** Users get public/private IPs or SSH keys to access VMs remotely.
- **Images of Cloud Instances:** Predefined OS images (Ubuntu, CentOS) are used to launch VMs in Meghamala.
- **VM Termination:** Users can stop, delete, or snapshot VMs as needed using OpenStack tools.

---

### 🔹 **Microsoft Azure Platform – Overview**
- Microsoft’s cloud computing platform offering IaaS, PaaS, and SaaS.

#### Components:
- **MS Azure:** Main platform providing scalable cloud services.
- **SQL Azure:** Cloud-based RDBMS for storing and querying structured data.
- **AppFabric:** Middleware for app integration, caching, and messaging.

#### Services:
- **Compute:** VMs, containers, and serverless computing (Azure Functions).
- **Storage:** Blobs, Queues, Tables, and Disks for various data types.
- **Fabric:** Underlying infrastructure for managing services and resources.

#### Instance Types:
- **Web Role:** For hosting front-end web applications (IIS enabled).
- **Worker Role:** For background processing tasks (no IIS).

#### Security & Data:
- **Protection Schemes:** Data encryption, firewalls, identity management.
- **Data Services:** Cosmos DB, SQL Database, Azure Synapse Analytics.

---

### 🔹 **Python Web-App Creation on Azure**
- Use **Azure App Services** to deploy Python Flask/Django apps.
- Supports **GitHub integration, CI/CD**, and **scalability**.
- Configure via Azure portal with runtime stacks and deployment slots.

---

### 🔹 **Google Cloud Platform (GCP) – Overview**
- Google’s cloud offering for compute, storage, machine learning, etc.

#### Features:
- High performance, global network, autoscaling, pay-as-you-go model.

#### Services:
- **Compute:** Compute Engine (VMs), Kubernetes Engine (GKE), App Engine.
- **Storage:** Cloud Storage (object), Persistent Disk (block), Firestore (NoSQL).
- **Analytics:** BigQuery (SQL for large datasets), Dataflow, Pub/Sub.

#### Web Hosting:
- Host static sites using **Cloud Storage** or dynamic sites via **App Engine**.
- Connect with domain, SSL, and deployment via CLI or console.

#### Web-App Using Google App Engine:
- Fully managed platform to deploy apps in Python, Node.js, Java, etc.
- Auto-scaling, versioning, and logging enabled by default.


---
---

 Thanks for sharing the assignment screenshot. Here's a question-by-question breakdown of **Week 4: Assignment 4** along with explanations for each correct and incorrect option:

---

### **Q1)**  
**In Google Cloud Platform (GCP), Cloud Datastore provides flexible object storage with global edge caching.**  
✅ **Correct Answer: (b) FALSE**

**Explanation:**  
Cloud Datastore is a NoSQL document database, not an object storage service. Object storage with edge caching is provided by **Cloud Storage**, not Datastore.

---

### **Q2)**  
**Match the following:**  
- A. Cinder, OpenStack → 4. Manages block storage in OpenStack.  
- B. GoogleAPIs → 2. Google's fully managed, petabyte scale, low cost analytics data warehouse.  
- C. Cloud SQL → 1. MySQL or NoSQL databases.

✅ **Correct Option: (a) A-4, B-3, C-1**

**Explanation:**  
- A. Cinder = OpenStack's block storage component → 4 ✅  
- B. GoogleAPIs = Provide various APIs, not a data warehouse → 3 ❌  
- C. Cloud SQL = MySQL or PostgreSQL databases → 1 ✅  
- So correct matching is: **A-4, B-3, C-1**

---

### **Q3)**  
**Statement 1: Azure supports public cloud platform.**  
**Statement 2: Azure App Service plan defines security.**  
✅ **Correct Answer: (a) Statement 1 is True and Statement 2 is False**

**Explanation:**  
- Azure *is* a public cloud platform ✅  
- Azure App Service plans define **compute resources**, not security ❌

---

### **Q4)**  
**Which component of OpenStack manages persistent block storage for instances?**  
✅ **Correct Answer: (b) Cinder**

**Explanation:**  
- **Cinder** handles persistent block storage  
- Nova = compute  
- Swift = object storage  
- So correct is **Cinder**


---
---

### **Q8)**  
**Azure App plan has a scale count of how many instances?**  
✅ **Correct Answer: (b) 1 to 20**

**Explanation:**  
- Basic App Service plan in Azure can scale from 1 to 20 instances  
- Other options are outside the allowed range

---

### **Q9)**  
**Match OpenStack storage types:**  
- A. Ephemeral storage → 1. Cinder ❌  
- B. Block storage → 2. Nova ❌  
- C. Object storage → 3. Swift ✅

✅ **Correct Answer: (d) A-2, B-1, C-3**

**Explanation:**  
- A. Ephemeral → Nova (temporary disk storage with VM)  
- B. Block storage → Cinder ✅  
- C. Object storage → Swift ✅

---

### **Q10)**  
**In GCP, "gcloud app browse" can be used to launch local dev server?**  
✅ **Correct Answer: (b) FALSE**

**Explanation:**  
- `gcloud app browse` opens the URL of the deployed app in the browser  
- It does **not** start a local server. For that, use `dev_appserver.py` or `gcloud emulators`

---
Thanks for the close-up of questions 6 and 7. Let's go over them carefully to clarify the confusion and explain each option:

---

### **Q6) Which of the following is/are App Services provided by Google Cloud Platform?**  
Options:  
(a) BigQuery  
(b) Cloud App Engine  
(c) Cloud Endpoints  
(d) Cloud SQL  

✅ **Accepted Answer: a, b, d**  
#### **Explanation of each option:**

- **(a) BigQuery** ✅  
  - While **not a typical "App Service"**, BigQuery can be considered part of Google's **serverless data services**, often used alongside app development for analytics.

- **(b) Cloud App Engine** ✅  
  - This is **definitely** a core App Service in GCP — it's Google's Platform-as-a-Service (PaaS) for building scalable web apps.

- **(c) Cloud Endpoints** ❌  
  - This is an **API gateway**, **not an App Service**. It's used for managing and securing APIs, not for hosting app logic directly.

- **(d) Cloud SQL** ✅  
  - A **managed relational database** service — while not an app in itself, it is widely considered a **backend service** for apps and is grouped under app services in GCP's broader categorization.

➡️ **Correct Answer: a, b, d**

---

### **Q7) Google Cloud End Points helps to:**  
Options:  
(a) Migrate the web app to Google Cloud Platform  
(b) Scale up the app according to demand/service requests  
(c) Provide flexible object storage with global edge caching  
(d) Integrate Google’s services into the application  

✅ **Accepted Answer: b**  
#### **Explanation:**

- **(a)** ❌ Migration is not a function of Cloud Endpoints  
- **(b)** ✅ Cloud Endpoints helps **scale and secure APIs**, which is key for scaling apps  
- **(c)** ❌ Edge caching is related to **Cloud Storage** and **CDNs**, not Cloud Endpoints  
- **(d)** ❌ Integration of services is too vague and not the primary purpose of Cloud Endpoints

➡️ **Correct Answer: b**

---














