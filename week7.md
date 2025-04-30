make short and consie notes based on above notes for nptel mcq exam inlcude all important point

## 📱 **Mobile Cloud Computing (MCC) – Summary Notes**

### ✅ **Motivation**
- **Anywhere, anytime** access to info
- Surge in **smartphone usage**, apps, and capabilities
- **More internet access via mobiles** than PCs
- **Limitations**: Battery, storage, bandwidth
- **Cloud benefits**: On-demand, low-cost access to infrastructure/platforms/software

---

### ☁️ **What is MCC?**
- Integration of **cloud computing**, **mobile computing**, and **wireless networks**
- MCC offloads **heavy computing & storage** to cloud servers
- Enables rich applications on **resource-constrained** mobile devices

---

### 📦 **Mobile Backend as a Service (MBaaS)**
- Offers backend cloud services (storage, processing)
- **Hides infrastructure complexity**
- Useful for **multiple apps**, platforms, developers
- Provides APIs, SDKs, social integration, cloud storage

---

### 🌐 **Examples**
- **Amazon Silk**: Split browser
- **Apple Siri**: Cloud-based speech recognition
- **Apple iCloud**: Sync & unlimited storage
- **AR apps** using cloud image recognition

---

### 🚀 **Why MCC?**
- Fast development across platforms
- Uses shared cloud resources
- Seamless multi-device engagement
- Integrated and secure data access

---

### 🛠️ **Key Features**
- Lightweight mobile clients
- Cloud-supported apps save device resources
- Support multiple devices/platforms
- Reliable with cloud backups

---

### ⚙️ **Typical MCC Workflow**
1. **Profiler**: Monitors execution (time, energy, traffic)
2. **Solver**: Decides which app parts run where
3. **Synchronizer**: Combines cloud/mobile results

---

### 📶 **Architecture**
- Mobile → Network (Base Stations) → Internet → Cloud
- Cloud Controllers handle user requests
- Thin client on mobile interacts with cloud

---

### ✅ **Advantages**
- **Battery saving** via computation offloading
- **Enhanced storage & processing**
- **Improved reliability & availability**
- **Scalable**, multi-tenant, dynamic provisioning
- **Easy integration** of services

---

### ⚠️ **Challenges**
#### 1. **Security & Privacy**
- Mobile threats (malware, GPS tracking)
- Cloud data security, authentication
- Offloading security tasks to cloud

#### 2. **Context-Aware Services**
- Tailor services to user preferences, network, device

#### 3. **Network Access & QoS**
- Reduce **latency** using **CloneCloud**, **Cloudlets**
- Efficient bandwidth and QoS management

#### 4. **Pricing**
- Multiple providers → complex pricing & revenue models

#### 5. **Standard Interface & Convergence**
- Need **interoperability**
- Integrate services across multiple clouds
- **Sky computing**: Use multiple clouds as one

---

### 🧠 **Task Partitioning Problem**
- Partition app methods into mobile/cloud sets
- Inputs: Call graph, energy cost (local/remote)
- Objectives:
  - **Minimize energy**
  - Meet **execution time constraint**
  - Other constraints: Mandatory local execution, cost

---

### 🧪 **Systems**
#### **MAUI**
- Manual method tagging as "remoteable"
- Runtime offloading based on energy/time savings

#### **COMET**
- No source code changes
- Thread migration using Distributed Shared Memory (DSM)
- Transfers only modified data to cloud

---
---

### 🔢 **Mathematical Formulation for Task Partitioning (ILP-based)**

- **Application model:** Directed Acyclic Graph (DAG), nodes = methods/tasks; edges = execution sequence.
- **Native tasks:** Nodes (e.g., `v1`, `v4`, `v9`) that *must* run on the mobile device.
- **Decision variable:**  
  \[
  I_v = 
  \begin{cases} 
  0 & \text{if executed locally} \\
  1 & \text{if offloaded}
  \end{cases}
  \]
- **Objective:** Minimize total energy and latency under constraints.
- **Key parameters:**
  - \( E \): Local execution energy
  - \( C_{u,v} \): Data transfer cost
  - \( T \): Method execution time
  - \( B \): State transfer time
  - \( L \): Total latency

---

### 🧮 **Energy Saving Formula for Offloading**

Let:
- \( C \): Number of instructions
- \( M \): Mobile processing speed
- \( S = F \times M \): Cloud processing speed (F = speed factor)
- \( D \): Data to be transferred
- \( B \): Bandwidth
- \( P_c \): Energy/sec during computation
- \( P_i \): Energy/sec while idle
- \( P_{tr} \): Energy/sec during data transmission

**Energy saved:**
\[
\frac{C}{M} \left(P_c - \frac{P_i}{F}\right) - \frac{D}{B} \cdot P_{tr}
\]

> **Offload when:** Energy saved > 0  
> **Favorable if:** Large C, small D, high F

---

### 📶 **Challenges in Mobile Cloud Computing**

- **Communication:**
  - Low bandwidth
  - Service availability
  - Heterogeneous networks
- **Computation Offloading:**
  - Deciding *when* and *what* to offload
  - Overhead of data transfer vs compute gain

---

### ☁️ **Code Offloading via Cloudlets**

- **Cloudlet:** Trusted, local mini-clouds with low latency
- **Benefits:** Lower energy usage, fast response (Wi-Fi over 4G), reduced latency
- **Architecture:** Mobile Device ↔ Cloudlet ↔ Public Cloud

---

### 🧠 **Offloading Approaches**

1. **Static Partitioning:** Done at launch via ILP or heuristic
2. **Dynamic Partitioning:** At runtime based on environment/input
3. **Profiling-based:** Use historical data to minimize energy and communication

---

### 📏 **Evaluation Metrics for MCC**

- **Energy consumption**
- **Execution time**
- **Monetary cost**
- **Security/privacy**

---

### 🧭 **MuSIC Framework (Mobility-Aware Offloading)**

- **Goal:** Optimize service allocation as users move
- **Method:**  
  - Use **Location-Time Workflow (LTW)**
  - Optimize based on power, delay, cost
  - Tiered architecture: Local clouds (fine-grain) + Public clouds (scalable)
- **Modules:**
  - MAPCloud: Updates QoS info using user logs
  - Admission Controller: Schedules tasks

---

### 🚘 **Case Study: Cloud-Assisted Parking Services**

- **Problem:** Lack of real-time parking info in urban areas
- **Solution:** Use MCC + WSN to collect data → Cloud processes → Smart terminals show status
- **Features:**
  - Traditional garages: cloud-published availability
  - Dynamic roadside parking: based on traffic/rush hour patterns

---
---

## 🔷 **Mobile Cloud Computing (MCC): Key Concepts**

### 🧠 **Core Idea**
MCC offloads computation from mobile devices to the cloud to:
- Save energy
- Reduce execution time
- Improve performance and scalability

---

## 🧩 **Key Challenges in MCC**
1. **Dynamic Partitioning**
   - Optimize which code runs on mobile vs. cloud
   - Requires middleware or runtime system

2. **Task Partitioning Problem**
   - Given: Application call graph, energy costs, time constraints
   - Goal: Partition tasks between mobile and cloud
   - Approaches: Integer Linear Programming (ILP), heuristics

---

## 🛠️ **MCC Systems**

### **1. MAUI (Mobile Assistance Using Infrastructure)**
- Programmers annotate methods as "remoteable"
- MAUI decides where to run them for energy savings
- Works on source code level

### **2. COMET (Code Offload by Migrating Execution Transparently)**
- No source code required
- Uses Distributed Shared Memory (DSM)
- Allows thread migration across devices
- Only modified heap parts are transferred → reduces data overhead

---

## ⚙️ **Offloading Strategy**
### ➕ When is Offloading Beneficial?
Energy saved =  
\[
\frac{C}{M} \times (P_c - \frac{P_i}{F}) - \frac{D}{B} \times P_{tr}
\]
- Offload when:
  - Large computation (`C`)
  - Low communication data size (`D`)
  - High speedup (`F`)

### 📌 Considerations:
- Not all tasks are worth offloading
- Must consider bandwidth, privacy, security

---

## ☁️ **Cloudlet-Based Offloading**
- Cloudlet = nearby trusted mini-cloud (1-hop from mobile)
- Reduces latency and energy use vs. distant cloud
- Used in real-time or latency-sensitive apps

---

## 🔢 **Partitioning Methods**

### 📌 Static Partitioning
- Decision made once at launch using ILP or heuristics

### 📌 Dynamic Partitioning
- Adaptation at runtime
- Environmental & input-dependent

---

## 📉 **Evaluation Metrics for MCC**
- Energy consumption
- Time to completion
- Cost (network + cloud usage)
- Security (e.g., sensitive data handling)

---

## 📱 **Applications of MCC**
- **Mobile Health**: real-time vitals monitoring, emergency response
- **Mobile Commerce**: secure transactions, shopping
- **Mobile Gaming**: offload heavy graphics/rendering
- **Assistive Tech**: guidance systems for blind, transcription for hearing-impaired
- **Mobile Learning**: collaborative, remote education
- **Vehicular Networks**: context-aware parking, navigation

---

## 📍 **MuSIC: Mobility-Aware Optimal Service Allocation**
- Uses **Location-Time Workflow (LTW)** model to map user movement + app logic
- Considers **QoS (Quality of Service)**: delay, power, cost
- Uses a **2-tier architecture**:
  - Tier 1: Public clouds (EC2, Azure)
  - Tier 2: Local clouds (e.g., WiFi APs, campus servers)

---

## 📈 **Mobile Application Modeling (MuSIC)**
- Models user movement, service usage, cloud capacity
- Uses logs and context (location, service delays) to update decisions dynamically

---
---

### **1. Cloud Computing - Challenges**
- Large-scale data processing.
- Data centers: Private (owned) or Public (rented).
- All data needs to be uploaded to cloud → latency, bandwidth.

---

### **2. Cloud Computing - Characteristics**
- **Dynamic scalability**
- **No infrastructure management by user**
- **Metered service** (pay-as-you-go)

---

### **3. Limitations of Cloud-Only Computing**
- High latency in real-time applications (e.g. accident detection).
- Core network congestion due to centralized data centers.
- Unsuitable for low-latency tasks.

---

### **4. Fog Computing – Introduction**
- Also called **Edge Computing**.
- Introduced by **Cisco Systems** for IoT.
- **Processing, storage, and apps near the network edge**.
- Cisco enables running apps on routers, switches using Linux.

---

### **5. Fog Computing – Features**
- Intelligence near end-user (ground level).
- Applications run on: base stations, routers, gateways.
- Sensors do basic data processing.
- Reduces response time → suitable for **real-time apps**.

---

### **6. Advantages of Fog Computing**
- Reduces **bandwidth** use (preprocessing at edge).
- Less **data movement** → lower network congestion.
- Enhanced **QoS**, **real-time response**, **location awareness**.
- Better **security** (data stays local).
- **Scalable**, **mobile**, **geo-distributed**.
- Complements cloud, not a replacement.

---

### **7. Fog Computing – Motivations & Use-Cases**
- Extends cloud to the network edge.
- Used in: **Smart Grids**, **Traffic Lights**, **Connected Vehicles**, **IoT**, **SDN**.
- Use Cases:
  - **Emergency Evacuation**
  - **Disaster Management**
  - **Smart Cities**
  - **Wireless Sensor Networks**
  - **Infotainment in Vehicles**

---

### **8. Enabling Technologies**
- **Virtualization** (VMs)
- **Containers** (e.g. Docker)
- **Service-Oriented Architecture (SOA)**
- **Software Defined Networking (SDN)**

---

### **9. Fog vs Cloud**
| Fog Computing                 | Cloud Computing                |
|-----------------------------|--------------------------------|
| Close to user (edge devices) | Centralized (data centers)     |
| Low latency                  | Higher latency                 |
| Local data processing        | Remote data processing         |
| Mobility support             | Less suited for mobile nodes   |

---

### **10. Security Issues in Fog**
- Authentication at gateways and fog nodes.
- **Man-in-the-middle attacks**
- **Privacy issues** (e.g., IP spoofing in smart meters)

---
---

### ✅ **1. Why Fog Computing?**
- Cloud helps IoT with **scalability**, **resource provisioning**, and **data intelligence**.
- But **high latency** in real-time applications is a problem.
- **Fog Computing** offers **low-latency**, **faster response** by processing near the data source (fog nodes).

---

### ✅ **2. Key Use-Cases of Fog Computing**
- **Emergency Evacuation Systems** – Exit route planning using real-time data.
- **Natural Disaster Management** – Flash flood, landslide alerts.
- **IoT & Big Data** – Pre-process and summarize sensor data before sending to cloud.

---

### ✅ **3. Applicability Domains**
- Smart Traffic Lights  
- Connected Vehicles  
- Smart Grids  
- Wireless Sensors  
- IoT  
- Software Defined Networks (SDNs)

---

### ✅ **4. Connected Vehicle (CV) & Fog**
- Supports **car-to-car**, **car-to-access point**, and **access point-to-access point** communication.
- Fog enables **infotainment**, **traffic analytics**, and **safety features** through:
  - **Geo-distribution**, **mobility**, **real-time**, **heterogeneity**

---

### ✅ **5. Smart Traffic & Smart Grid**
- Fog processes data **closer to source**, enabling:
  - Faster traffic light responses.
  - Smarter energy decisions in smart grids.

---

### ✅ **6. Fog Challenges**
- **Resource Allocation** for end-to-end latency guarantees.
- Ensuring **availability**, **scalability**, and **fault tolerance**.
- **Security** of data and applications.

---

### ✅ **7. Resource Management in Fog**
- Use **idle fog nodes** for **parallel processing**.
- **Load balancing** and **latency control**.
- **Fault tolerance** for real-time apps.

---

### ✅ **8. Resource Management – Key Challenges**
- Required **data may not be on executing fog node**.
- Node might become **unresponsive** under load.
- Need to **migrate execution and state** to another node.
- Ensure **data isolation** between apps to maintain **security** and **integrity**.

---

### ✅ **9. Resource Management – Approaches**
- **Execution migration** to nearest node.
- **Carbon footprint minimization** (e.g., video streaming).
- **Docker-based deployment** → fast, elastic, efficient.
- **Resource prediction**, **reservation**, and **pricing** models.
- **Mixed Integer Linear Programming (MILP)** for VM placement and task distribution (e.g., medical cyber-physical systems).

---

### ✅ **10. Security Issues in Fog**
- **Authentication** at gateways and nodes.
- **Man-in-the-Middle attacks**
- **Privacy issues**:
  - Smart meters can be **spoofed** or **tampered**.
  - Each device has an **IP**, creating vulnerability.

---
---

### 🔹 **Cloud Computing Basics**
- **Definition (NIST):** On-demand, network-accessible, shared pool of configurable computing resources.
- **Key Features:**
  - On-demand self-service
  - Ubiquitous network access
  - Resource pooling (location-independent)
  - Rapid elasticity
  - Measured service (pay-as-you-use)

---

### 🔹 **Geospatial Information**
- **Definition:** Data explicitly linked to Earth’s surface.
- **Types:**
  - Static: city, lake
  - Dynamic: population, migration
- **Scales:** From local (meters) to global

---

### 🔹 **Geospatial Data Categories**
- Legal, political, cultural, climatic, topographic, biotic, medical, economic, infrastructure, social

---

### 🔹 **Data Sources**
- Social/natural surveys
- Remote sensing (satellite imagery)
- Reporting networks (weather stations)
- Field data (GPS)

---

### 🔹 **Geographic Information System (GIS)**
- **Definition:** A system for capturing, storing, analyzing, and displaying geospatial data.
- **Components:**
  - Hardware
  - Software
  - Data procedures
  - Spatial data
  - Skilled personnel

---

### 🔹 **Challenges in GIS**
- Data- & computation-intensive
- Variable load → need dynamic scaling
- Requires high performance, network-intensive services

---

### 🔹 **Geospatial Layers & Data Issues**
- Developed by different departments → **heterogeneity**
- **Need for Homogeneity:**
  - Standard encoding
  - Standard data sharing mechanisms

---

### 🔹 **Spatial Data Infrastructure (SDI)**
- Enables spatial data **discovery, evaluation, application**
- Used by government, commercial, academic, and public sectors

---

### 🔹 **Geospatial Cloud – Motivation**
- Huge spatial data volume
- Need for services + orchestration
- Sharing across orgs (private/public)
- Less infrastructure expertise required
- Supports multi-tenancy, scalability, cost-efficiency

---

### 🔹 **Advantages of Cloud**
- Scalability, efficient resource use
- Minimized IT management
- Reduced startup costs (CAPEX)
- Consumption-based billing
- Green computing (less carbon footprint)

---

### 🔹 **Cloud Actors**
- **CSP/Broker:** Provides infra/services
- **Customer:** End user or organization
- **Negotiator (optional):** Arranges services
- **SLA Manager/Security Auditor:** Future need

---

### 🔹 **Geospatial Cloud Architecture**
- **eGIS instances:** Resource, Data & Interface services
- **Web Services:** Key for integration
- **Back-end Services:** Inside (via PaaS) & outside cloud (WMS/WFS)

---

### 🔹 **Use Cases – Service Integration**
- Road & water network merging
- Shortest path calculation
- Buffer zones in water networks

---

### 🔹 **Challenges in Geospatial Cloud**
- Spatial database implementation & scaling
- Multi-tenancy & policy enforcement
- Geo-distributed backups
- Data security & performance

---

### 🔹 **Interoperability Levels**
- **Data Level:** Reading & using data
- **Service Level:** Exchanging data/services
- **Security Level:** Trustworthy operations
- **Standards:** Use OGC and similar bodies

---

### 🔹 **Security Concerns**
- Multi-tenancy
- Lack of direct control (data/apps/services)
- Potential threats:
  - Unauthorized access (internal/external)
  - Data tampering or unavailability

---

### 🔹 **Asset Evaluation for Cloud Deployment**
- Identify valuable data/apps/processes
- Risk of exposure, manipulation, unavailability
- Importance of classifying asset value

---







