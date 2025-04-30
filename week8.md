## 🚢 **Docker – Overview**
- **Container management service**, released in **March 2013**.
- Core functions: **Develop, Ship, Run Anywhere**.
- Helps developers create apps, pack into containers, and deploy anywhere (cross-platform).
- Popular in **Agile development**.

---

## ⚙️ **Infrastructure & Software Stack**
- Goal: **Interoperability** across environments.
- Enables seamless collaboration between **dev, QA, ops**.

---

## 📦 **Containers vs. VMs**
| **Containers** | **Virtual Machines** |
|----------------|----------------------|
| Share the **host OS kernel** | Run a full **guest OS** |
| Lightweight, start instantly | Heavy, slow to boot |
| Isolated user space | Isolated full OS |
| Use less disk/memory | Resource intensive |
| Native-like process execution | Virtualized execution |

---

## 🧱 **Docker Components**
- **Docker Engine**: Core service for building & running containers.
- **Docker for Windows/Mac/Linux**: Platform-specific Docker versions.
- **Docker Hub**: Cloud-based image registry (`hub.docker.com`).
- **Docker Compose**: Tool to define & manage multi-container apps.

---

## 🏗️ **Docker Architecture**
- **Server**: Physical host machine.
- **Host OS**: Linux/Windows base OS.
- **Docker Engine**: Runs containers instead of VMs.
- **Apps**: Executed as Docker containers.

---

## 📁 **Terminologies**
### 🔹 Image
- A **snapshot** of the app + dependencies.
- Key commands:
  - `docker images` – List images  
  - `docker pull <img>` – Download image  
  - `docker tag` – Tag an image  
  - `docker rmi` – Delete image  
  - `docker run` – Run container from image  

### 🔹 Container
- **Runnable instance** of an image.
- Key commands:
  - `docker ps` – List running containers  
  - `docker ps -a` – List all containers  
  - `docker start/stop/pause/rm`  
  - `docker commit` – Create image from container  

---

## 🛠️ **Dockerfile**
- Script to build images automatically.
- Version-controllable via Git/SVN.
- Supports **auto-build** via Docker Hub if hosted on GitHub.

---

## ☁️ **Docker Hub**
- Public repo of images.
- Can auto-build images from GitHub Dockerfiles.

---

## 🚀 **Why Docker?**
- Enables **application-level virtualization**.
- Multiple apps can share one host efficiently.
- **Build once, run anywhere**.
- Improves collaboration, testing, and CI/CD.
- Scalable, fast, portable.

---

## 🧰 **Docker – Use Cases**
- Fixes **“works on my machine”** problems.
- Lets **operators** run isolated apps side-by-side.
- **Enterprises** use it for faster, secure software delivery on Linux/Windows/mainframes.

---
---

## ☁️ **Cloud Computing – Overview**
- **Definition**: On-demand, convenient network access to shared configurable computing resources (networks, servers, storage, apps, services).
- **Key Benefits**:
  - Pay-as-you-go, reduced capital & infra cost.
  - Global access & flexibility.
  - Improved process efficiency.
  - Reduced software licensing needs.

---

## 🌱 **Green Cloud Computing**
- **Green Computing**: Eco-friendly use/design/disposal of computing devices.
- **Green Cloud**:
  - Combines cloud computing with green IT.
  - Goals: **Efficient processing** + **reduced energy consumption** + **lower carbon footprint**.

---

## ⚠️ **Challenges in Cloud Computing**
- **Gartner (2007)**: IT causes **2% of global CO₂ emissions**.
- **US EPA (2007)**: **1.5% of US power** used by data centers.
- **High Operational Cost**: Energy = 10–50% of OPEX.
- **Cooling Systems**: Add $2–5M per year.

---

## ⚡ **Data Center (DC) Energy Consumption**
- **Cooling**: 45%  
- **IT Equipment**: 40%  
- **Power Distribution**: 15%
- **Idle Servers** consume **~66% of peak power**.
- **Switch Energy Split**: Linecards (53%), Chassis (36%), Ports (11%).

---

## 🏛️ **DC Architectures**
### Past:
- **2-tier**: Access + Core layers, Full mesh, 1/10 GE links.

### Present:
- **3-tier**: Access, Aggregation, Core; scalable to 10,000+ servers.
- **High-Speed 3-tier**: ECMP load balancing, 100 GE support (IEEE 802.3ba).

---

## 🌍 **Environmental Impact**
- Cloud DCs emit more CO₂ than Argentina/Netherlands.
- Need to **optimize for energy efficiency**, not just performance.

---

## 💰 **CSP Initiatives**
- CSPs (e.g., Amazon) face rising energy costs (42% of total DC budget).
- Google, Microsoft, Yahoo moving DCs to **hydroelectric-rich areas**.

---

## 🧠 **Green Cloud Framework**
### ✅ Green Broker:
- **Layer 1**: Analyze user QoS needs.
- **Layer 2**: Estimate **cost** + **CO₂ emissions**.
- **Layer 3**: Perform **carbon-aware scheduling**.

### ✅ Green Middleware:
- Monitors energy efficiency using **PUE** (Power Usage Effectiveness).

---

## 📊 **Key Metric**
- **PUE**: Ratio of total facility energy to IT equipment energy.
  - Ideal PUE ≈ 1.0 (most efficient).

---

## 🧾 **Conclusion**
- Cloud = Powerful but energy-intensive.
- **Green Cloud** = Eco-friendly, cost-effective future of computing.
- Ongoing research needed in:
  - **Energy-efficient DCs**
  - **Sustainable computing for developing regions**

---
---

## **Sensor Cloud Computing - Lecture 1: Introduction to Sensor Cloud Computing**  
**Instructor:** Prof. Soumya K Ghosh, IIT Kharagpur  
**Topics Covered:** Introduction to Sensor Cloud Computing, Sensor Networks, and Cloud Computing  

---

### **1. Introduction to Sensor Cloud Computing**
Sensor cloud computing is the integration of sensor networks and cloud computing to enhance data collection, processing, and sharing.

---

### **2. Sensor Networks**

#### **Definition:**
A sensor network consists of distributed sensor nodes used for monitoring environmental conditions like temperature, humidity, pressure, etc.

#### **Characteristics:**
- Resource-constrained (battery, processing power, memory)
- Limited communication capabilities
- Often deployed in remote or inaccessible locations

#### **Challenges:**
- **Data Collection:** Manual data retrieval is not scalable.
- **Resource Limitation:** Nodes can't handle heavy computation or large storage needs.
- **Communication:** Wireless transmission is power-consuming and unreliable over long distances.

---

### **3. Cloud Computing**

#### **Definition:**
Cloud computing provides scalable computing resources and services (storage, processing, networking) over the internet.

#### **Advantages:**
- On-demand access
- Scalability
- High availability
- Reduced infrastructure cost

---

### **4. Sensor Cloud Computing**

#### **Definition:**
Sensor cloud computing bridges sensor networks and cloud computing to overcome the limitations of individual sensor nodes.

#### **Architecture:**

##### **a. Data Collection Layer (Sensors):**
- Sensor nodes collect raw data from the environment.

##### **b. Sensor Network Gateway:**
- Aggregates and preprocesses sensor data.
- Transmits data to the cloud.
- Acts as a bridge between the sensor network and the cloud.

##### **c. Cloud Layer:**
- Stores and analyzes data.
- Provides APIs for accessing processed data.
- Supports applications (e.g., healthcare, agriculture, disaster management).

#### **Advantages:**
- **Scalability:** Easily integrates additional sensors and storage.
- **Accessibility:** Sensor data can be accessed anytime, from anywhere.
- **Data Analysis:** Supports real-time and historical data analysis.
- **Resource Optimization:** Offloads computation from sensors to the cloud.

---

### **5. Applications of Sensor Cloud Computing**
- **Healthcare Monitoring**
- **Environmental Monitoring**
- **Agriculture (Precision Farming)**
- **Smart Cities**
- **Disaster Management**
- **Industrial IoT**

---

### **6. Limitations and Challenges**
- **Security & Privacy:** Sensitive data may be exposed during transmission or cloud storage.
- **Network Latency:** Real-time applications may be affected by delays.
- **Energy Consumption:** Sensor-to-cloud communication can drain battery quickly.
- **Data Management:** Huge volumes of data require efficient storage, retrieval, and processing mechanisms.

---
---

## ✅ **Course Summary: Important Points for MCQs**

### **1. Basics of Cloud Computing**
- **NIST Model:** On-demand access, broad network access, resource pooling, rapid elasticity, measured service.
- **Cloud Characteristics:** Scalable, cost-effective, resource pooling.
- **Disadvantages:** Security concerns, vendor lock-in, data privacy.

### **2. Cloud Architecture & Stack**
- **Layers:** Infrastructure (IaaS), Platform (PaaS), Software (SaaS)
- **Cloud Stack:** Physical layer → Virtualization layer → Cloud services.

### **3. Service Models (XaaS)**
- **IaaS:** Virtual machines, storage.
- **PaaS:** Development platforms.
- **SaaS:** End-user applications (e.g., Gmail).
- **Others:** Storage-as-a-Service, Network-as-a-Service, Information-as-a-Service.

### **4. Deployment Models**
- **Public Cloud**
- **Private Cloud**
- **Hybrid Cloud**
- **Community Cloud**

### **5. Cloud Management & SLAs**
- **Service Management:** Provisioning, monitoring, de-provisioning.
- **SLA (Service Level Agreement):** Defines QoS, uptime, penalties.

### **6. Cloud Economics**
- **Pay-as-you-go model**
- **CAPEX → OPEX**
- Resource optimization through virtualization.

---

## ✅ **Advanced Cloud Topics**

### **7. Data Management & Big Data**
- **Scalability:** Key for handling large volumes of cloud data.
- **Technologies:** GFS (Google File System), HDFS (Hadoop), MapReduce.

### **8. Cloud Security**
- **Key Issues:** Data privacy, access control, identity management.
- **Threats:** Side-channel attacks.
- **Security-as-a-Service**
- **Trust & Reputation systems**

### **9. Virtualization & System Software**
- **Enables multi-tenancy**
- **Service Composition & Orchestration**
- **Virtual Machines (VMs)** and **Containers**

---

## ✅ **Research Areas in Cloud Computing**

### **1. Cloud Infrastructure & Services**
- Architectures, distributed networking, storage architecture.
- Cloud delivery models (IaaS, PaaS, SaaS, etc.).

### **2. Cloud Operations & Monitoring**
- **Cloud Federation & Bursting**
- **Hybrid Cloud Integration**
- **Green Computing**
- **Cloud Metering & Auditing**

### **3. Performance & Reliability**
- **Cloud availability**
- **Scalability & fault tolerance**
- **Microservices-based architecture**

### **4. Data Analytics in Cloud**
- Scientific computing, big data analysis.
- **Analytics-as-a-Service**

### **5. Service Management**
- **Service Discovery, Composition, QoS**
- **Security & Privacy in services**
- **Semantic & SOA-based services**

---

## ✅ **Emerging Technologies**
- **Fog Computing:** Extends cloud to the edge (low latency).
- **IoT Cloud:** Integration of IoT and cloud services.
- **Container Technology:** Lightweight alternative to VMs (e.g., Docker).
- **Green Cloud Computing:** Energy-efficient cloud operations.

---
