2-4,6-


---
---
| **Aspect**              | **Web Service SLA**                                                                 | **Cloud SLA**                                                                                      |
|------------------------|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| **QoS Parameters**     | Focus on response time, reliability (SLA violation rate), availability, and cost.   | Includes QoS for **security, privacy, trust, and management**, in addition to performance.         |
| **Automation**         | SLA negotiation, provisioning, monitoring are **mostly manual** or semi-automated. | SLA processes are **highly automated** to support **dynamic and scalable** cloud environments.     |
| **Resource Allocation**| Uses **UDDI** for service discovery and interaction between web services.           | Resources are **dynamically allocated and globally distributed**, **without a central directory**. |

**Summary:**
- **Web Service SLA** deals more with basic service metrics and manual operations.
- **Cloud SLA** encompasses broader concerns (e.g., trust, security) and is designed for dynamic, large-scale systems with automated processes.

---

## 🔹 **Service Level Agreement (SLA) – Short Notes**

### ✅ **Definition**
- Formal contract between a **Service Provider (SP)** and a **Service Consumer (SC)**
- Defines **performance and availability** guarantees
- Contains **Service Level Objectives (SLOs)** – measurable QoS parameters

---

### 📃 **SLA Contents**
- List and definition of services
- Roles of SP & SC
- Performance metrics & monitoring
- Remedies for SLA violations
- Change management process

---

### 🌐 **Web Service SLA**
- **WS-Agreement**: XML-based protocol for dynamic SLA negotiation and management
- **WSLA**: XML-schema for SLA with QoS monitoring

---

### ☁️ **Cloud SLA vs Web Service SLA**
| Aspect              | Web Service SLA                      | Cloud SLA                              |
|---------------------|--------------------------------------|----------------------------------------|
| QoS Parameters      | Response time, availability          | Security, trust, privacy               |
| Automation          | Manual                               | Automated                              |
| Resource Discovery  | UDDI                                 | Dynamic, global                        |

---

### 🧾 **Types of SLA**
- **Non-negotiable (Off-the-shelf)**: Fixed templates by provider
- **Negotiable**: Involves SLA agents for customization

---

### 🎯 **Service Level Objectives (SLOs)**
- Measurable QoS targets (e.g., 99.9% uptime, 3-5s response time)

---

### 🔍 **Service Level Management**
- Ensures services meet defined SLOs
- **Consumer**: Better usage decision  
- **Provider**: Align with business goals

---

### 📌 **Key Considerations**
- Business goals
- Provider-consumer responsibilities
- Disaster recovery
- Redundancy
- Data location, seizure, and jurisdiction
- Provider failure

---

### 🔐 **SLA Requirements**
- Security, encryption, privacy
- Data retention & deletion
- Compliance, certification
- Monitoring & auditability

---

### 📊 **Key Performance Indicators (KPIs)**
- Metrics: uptime, downtime, throughput, availability
- KPI ➝ SLO mapping (e.g., A = 1 - (downtime / uptime))

---

 

### **SLA Monitoring and Auditing Metrics – Short Notes**

- **Throughput**: Speed at which a service responds.
- **Availability**: % of uptime in a defined period (e.g., 99.9% per month).
- **Reliability**: Frequency of service availability (less frequent downtimes = more reliable).
- **Load Balancing**: Triggers elasticity—auto-scaling up/down of VMs based on load.
- **Durability**: Likelihood that data will be retained without loss (important for storage).
- **Elasticity**: Ability of the system to scale resources up/down as needed.
- **Linearity**: System’s ability to handle increased load proportionally (performance scales with demand).
- Here’s a **short note** summarizing the additional **SLA Monitoring and Auditing Metrics** for your **NPTEL exam**:
- **Agility**: Speed at which the provider adjusts resources based on load fluctuations.
- **Automation**: % of requests handled without human involvement (fully automated systems are preferred).
- **Customer Service Response Time**: Time taken by the provider’s support team to respond to issues.
- **Service-level Violation Rate**: Average rate at which the SLA terms are breached.
- **Transaction Time**: Total time from service invocation to completion, including delays.
- **Resolution Time**: Duration from issue detection to its complete resolution.


---

### 🧪 **Examples**
- **Amazon EC2 (IaaS)**: 99.95% uptime
- **Google App Engine (PaaS)**: 99.9% availability
- **Azure, Zoho, Rackspace, Nirvanix**: Varying SLAs based on delivery model

---

### ⚠️ **Limitations**
- Focus on uptime only
- Biased metrics, no active customer monitoring
- No formal SLA compliance check
- Gap between claimed QoS and actual delivery

---

### 📦 **Expected SLA Parameters**
| Model        | Parameters                                                             |
|--------------|------------------------------------------------------------------------|
| **IaaS**      | CPU, storage, VMs, boot time, scale up/down, cost, availability       |
| **PaaS**      | Integration, billing, deployment env., scalability                    |
| **SaaS**      | Reliability, usability, availability, customizability, response time |
| **Storage**   | Location, security, backup, bandwidth, throughput, fault tolerance    |

---
---
---

### **Cloud Properties – Economic Viewpoint**

#### **Core Attributes**
- **Common Infrastructure**: Shared, standardized resources with cost efficiency from **statistical multiplexing**.
- **Location Independence**: Services available anywhere; **reduced latency**, improved UX.
- **Online Connectivity**: Ensures access; **cost/performance** of networks assessed traditionally.
- **Utility Pricing**: **Pay-per-use**; ideal for variable demand.
- **On-Demand Resources**: Scalable, elastic, with minimal delay/cost of change.

---

### **Economies of Scale**
- **Reduced overhead**, volume-based cost savings.
- **Statistics of Scale**:
  - Built to peak: higher utilization, lower cost per resource.
  - Built below peak: reduces unserved demand, SLA penalties.

---

### **Coefficient of Variation (CV)**
- **CV = σ / |μ|**
- Lower CV = smoother demand curve.
- Aggregating *n* independent demands:  
  - Mean = *nμ*, Std Dev = √nσ → CV = **CV/√n**
- Aggregation → lower penalty (e.g., 100 workloads → 10% CV)

---

### **Demand Correlation Effects**
- **Negative correlation**: Better smoothing.
- **Positive (perfect) correlation**: No gain from multiplexing.
- **Simultaneous peaks**: Worst-case.

---

### **Location Independence (Latency Impact)**
- Latency ∝ distance (fiber: ~124 miles/ms)
- Acceptable UX: response < 100ms (e.g., VOIP < 200ms)

---

### **Utility Pricing**
- **CT = A × U × B × T**,  
  where U = utility premium, A = avg demand
- **BT = P × B × T**,  
  where P = peak demand
- Cloud cheaper when: **U < P/A**
- Spiky demand → **cloud preferred**
- **Hybrid model** = own + rent based on use case

---

### **Penalty of Static Provisioning**
- **Penalty = α × ∫|D(t) – R(t)| dt**
- **Exponential demand**: penalty grows exponentially if R(t) lags.

---

### **Assignment 1: Key Formulae**
- **D(t)**:  
  50 sin(t), for 0 ≤ t < π/2  
  20 sin(t), for π/2 ≤ t < π  
- **R(t) = D(t) + δ × dD(t)/dt**,  
  with **δ = π/12**
- **Penalty Cost**:  
  Area under |D(t) – R(t)| × 0.9 (cost per unit)


---

### **Relational Databases (RDBMS)**  
- **Default storage since 1980s**  
  - Efficient for **transaction processing**  
  - Examples: **System R, Ingres**  
  - Replaced **hierarchical** & **network databases**  
- **Components:**  
  - **SQL Interface** → Parses & optimizes queries  
  - **Disk-space Management:**  
    - Data stored on **pages** (contiguous memory blocks)  
    - Uses **pre-fetching** & **page replacement**  
  - **Database File System Layer:**  
    - Independent of OS FS for better memory control  
    - Supports **multi-disk storage** (RAID, clusters)  

---

### **Data Storage Techniques**  
- **Row-Oriented:**  
  - Best for **write-heavy** workloads (e.g., transactions)  
  - Uses indexes (e.g., **B+ tree**)  
- **Column-Oriented:**  
  - Best for **read-heavy** workloads (e.g., data warehouses)  
  - Stores projections sorted by **dimension values**  
  - Requires **join indexes** for different projections  
  - Examples: **Vertica**

---

### **Parallel Database Architectures**  
- **Shared Memory:**  
  - Multiple CPUs, single memory space (SMP OS)  
- **Shared Nothing:**  
  - Independent servers with own disks, connected via network  
  - Tables **partitioned** & distributed  
  - Example: Cluster databases (Oracle, SQL Server, DB2)  
- **Shared Disk:**  
  - Servers share storage (NAS/SAN via Ethernet, Fiber Channel, Infiniband)  

**Advantages over RDBMS:**  
- Parallel SQL execution  
- Distributed joins & two-phase commit  
- Fault tolerance (stand-by systems, recovery mechanisms)  
- Examples: **Oracle, DB2, SQL Server, Netezza, Vertica, Teradata**

---

### **Cloud File Systems**  
- **Google File System (GFS):**  
  - Large distributed clusters (commodity servers)  
  - Chunk size: **64 MB**, replicated (3×) across racks  
  - Single **Master** controls metadata  
  - Fault tolerance: Heartbeat messages, automatic reassignment of primary chunk server  
  - Read/Write handled by **Master/Chunk servers**  

- **Hadoop Distributed File System (HDFS):**  
  - Open-source GFS implementation  
  - Available on **Amazon EC2**  

---

### **BigTable**  
- Built on GFS; **column-oriented**  
- Data model:  
  - **Sparse, multi-dimensional map** → (Row key, Column key, Timestamp)  
  - **Column family:label** format  
  - Multiple versions stored (sorted by timestamp)  
- **Storage Structure:**  
  - Tables split into **tablets** (row ranges)  
  - Tablets managed by **Tablet Servers** using SSTables  
  - Single **Metadata Server** locates tablets  
  - Supports parallel reads/writes  
  - More work than simple appends due to sorted insertion  

---

### **Dynamo (Amazon)**  
- Key-value store for **highly concurrent updates**  
- Not dependent on distributed FS (GFS/HDFS)  
- Data Model: `<Key, Value>`  
  - Uses **MD5 hashing** for key mapping on a **virtual node ring**  
  - Replication across **N** physical nodes  
- **Consistency:**  
  - Quorum-based:  
    - **R** replicas for read  
    - **W** replicas for write  
    - (R + W) > N → quorum consistency  
  - Handles versioning via **vector timestamps**  
  - Conflict resolution using app logic  
- Storage engines: **Berkeley DB**, **MySQL**

---

### **Datastore (Google/Amazon)**  
- Simple transactional key-value DB:  
  - **Google App Engine Datastore**  
  - **Amazon SimpleDB**  
- Uses **BigTable** under the hood:  
  - Stores entities in a single table (column family)  
  - Horizontally **partitioned (sharded)** & sorted lexicographically  
- **Indexes:**  
  - **Single-property indexes** → WHERE clause queries  
  - **Kind indexes** → SELECT ALL queries  
  - **Composite indexes** → complex queries  
- Groups entities for transactions → stored close on disk  
- Efficient **prefix** & **range queries**  

---

### **Other Technologies**  
- **MapReduce:** Parallel programming paradigm for large-scale text processing & analytics  
- **Similar Systems:**  
  - Google App Engine’s Datastore  
  - Amazon SimpleDB  

---

### **Use Cases**  
- **Relational DB:** Transaction processing  
- **BigTable/Column-oriented:** Analytics, large-scale storage  
- **Dynamo:** E-commerce, high concurrency  
- **Datastore:** Scalable web apps requiring simple transactions  
- **GFS/HDFS:** Distributed file storage with high fault tolerance  

---

Here are concise and exam-focused notes based on your content, ideal for NPTEL MCQ-type exams:

---

### **OpenStack Overview**
- **OpenStack**: Cloud OS to control compute, storage, and networking resources in a data center.
- **Access**: Admins use dashboard; users provision resources via web UI.

---

### **OpenStack Cloud Service Models**
- **IaaS**: Compute, Storage, Network provisioning (OpenStack)
- **PaaS**: Built on IaaS (e.g., Cloud Foundry)
- **SaaS**: Software delivered via browser/thin client

---

### **OpenStack Capabilities**
- VM provisioning, snapshotting  
- Network and storage management  
- Multi-tenancy & project/user quotas  
- Users can belong to multiple projects

---

### **OpenStack History**
- Initiated by **NASA and Rackspace**

---

### **Major OpenStack Projects**
| Service         | Project    | Function |
|------------------|------------|----------|
| **Compute**       | Nova       | Manages VM lifecycle (spawn, schedule, destroy) |
| **Networking**    | Neutron    | Network-as-a-Service; API for defining networks |
| **Object Storage**| Swift      | Unstructured object storage, replicated across nodes |
| **Block Storage** | Cinder     | Persistent block storage; attach to instances |
| **Identity**      | Keystone   | Auth/authorization for services; endpoint catalog |
| **Image Service** | Glance     | Stores/retrieves VM disk images |
| **Telemetry**     | Ceilometer | Metering for billing, stats, benchmarking |
| **Dashboard**     | Horizon    | Web-based UI to manage services |

---

### **Storage Types in OpenStack**
- **Ephemeral (Nova)**: Temporary, local to VM, deleted with VM
- **Block (Cinder)**: Persistent, attachable, visible as block device
- **Object (Swift)**: Persistent, accessed via HTTP, used for files/images

---

### **OpenStack Workflow Summary**
1. User logs into **Horizon** and requests VM
2. **Keystone** authenticates and issues token
3. **Nova API** sends VM request using token
4. **Scheduler** selects compute node via MQ
5. **Nova Compute** provisions VM using:
   - **Neutron** (network)
   - **Cinder** (volume)
   - **Glance** (image lookup)
   - **Swift** (image fetch)
   - **Hypervisor** renders VM

---

### **Component Architectures**
- **Nova Scheduler**: Filters and selects host
- **Neutron**: Sets IP, gateway, DNS, L2 connectivity
- **Glance**: Serves VM images
- **Cinder**: Provides volumes
- **Keystone**: Issues auth tokens

---

