---

## 🔹 **Dew Computing – Overview**
- **Dew Computing (DC)**: A computing paradigm combining **cloud computing** with capabilities of **end devices** (PCs, mobiles).
- **Goal**: Reduce dependence on continuous internet connection by enabling **offline services** with later **synchronization**.
- First in **IoT–Fog–Cloud** continuum; **close to the user**.

---

## 🔹 **Dew Computing – Features**
- **Independence**: Local device works without internet.
- **Collaboration**: Synchronizes with cloud when online.
- **Microservice-based**, no centralized servers.
- Focused on **user-centric**, **personalized**, and **flexible** applications.
- **Analogy**: Cloud (high), Fog (near), Dew (on ground).

---

## 🔹 **Dew Computing – Architecture**
- **Components**:
  - **Dew Client Program**
  - **Dew DBMS**
  - **Dew Server** (runs inside **Dew Virtual Machine – DVM**)
  - **IoT Devices & Cloud Server**
- **Single-Super-Hybrid-Peer (SSHP) P2P Communication Link**
- **Dew Server Goals**:
  - Data Replication
  - Data Distribution
  - Synchronization

---

## 🔹 **Dew Computing – Service Models & Applications**
| Model            | Description & Example                          |
|------------------|------------------------------------------------|
| **Software-in-Dew** | Apps saved in cloud (e.g., Play Store, App Store) |
| **Platform-in-Dew** | Dev suite locally + synced to cloud (e.g., GitHub) |
| **Infrastructure-as-Dew** | Local system mirrored in cloud (via DVM)       |
| **Web-in-Dew**       | Local copy of web content for offline use         |
| **Storage-in-Dew**   | Local files synced with cloud (e.g., Dropbox)     |
| **Database-in-Dew**  | Local + cloud copies of database for reliability  |

---

## 🔹 **Dew Computing – Application Areas**
- **WiD**: Offline web access + sync later.
- **SiD**: Files accessible offline and synced.
- **DBiD**: Redundant database storage.
- **PiD**: Dev environment with backup in cloud.
- **IaD**: Cloud support for local systems.
  
---

## 🔹 **Dew Computing – Challenges**
- Power & Processor Management  
- Storage Efficiency  
- OS Viability  
- Secure Programming Principles  
- Database Security

---

## 🔹 **Serverless Computing – Overview**
- **Definition**: Backend services on an **as-used** basis.
- Developers write **functions**; no infra management.
- Code runs in **event-triggered, stateless, ephemeral containers**.
- Fully **managed**, **scalable**, and **cost-efficient**.

---

## 🔹 **Serverless Computing – Models**
1. **BaaS (Backend-as-a-Service)**:
   - Ready-made backend (e.g., Firebase).
   - Focus on frontend logic.
2. **FaaS (Function-as-a-Service)**:
   - Stateless functions triggered by events.
   - Functions auto-scale based on demand.

---

## 🔹 **FaaS – Details**
- Functions are:
  - Stateless
  - Event-triggered
  - Isolated
- Cloud manages: lifecycle, scaling, concurrency.
- Example: **ExCamera** – parallel video encoding.

---

## 🔹 **Serverless – Advantages**
- No server management
- Auto-scaling
- Pay-per-use
- Faster deployments

---

## 🔹 **Serverless – Challenges**
- **Asynchronous calls** increase complexity.
- **Chaining functions** → debugging and cost issues.
- **Shared code** issues (size limit, cold starts).
- **Too many libraries/technologies** → complexity.
- **Too many functions** → low maintainability.

---

## 🔹 **Major Serverless Providers**
- AWS Lambda
- Google Cloud Functions
- Azure Functions
- IBM Cloud Functions

---

## 🔹 **Key References (for Further Reading)**
- Yingwei Wang (Dew Computing, 2016)
- IEEE Access (Partha Pratim Ray, 2018)
- USENIX HotCloud (Serverless Design Patterns, 2018)
- IEEE Internet Computing (Serverless Evolution, 2018)

---
---

## 🌐 Serverless Computing (NPTEL)

### ✅ **Definition & Purpose**
- Hides server management; provides abstractions for developers.
- Programmers focus on application logic, not infrastructure.
- Cloud providers manage provisioning, scaling, patching, etc.
- Event-driven, pay-per-use computing model.

---

## 🔰 **Key Features**
- No need to provision/manage servers.
- Backend infrastructure is abstracted away.
- Automatic scaling & stateless execution.
- Executes code in response to events.

---

## 🏢 Major Providers
1. **AWS Lambda**
2. **Google Cloud Functions**
3. **Azure Functions**

---

## 🚀 AWS Lambda

### 🔍 Overview
- Event-driven serverless compute service by AWS.
- Supports languages: Python, Java, Go, C#, etc.
- Triggered by AWS events (e.g., S3, API Gateway, SNS).

### 🧱 Concepts
- **Function**: Unit of execution (code).
- **Runtime**: Execution environment matching the language.
- **Event Source**: AWS service/event that triggers Lambda.
- **Lambda Layers**: Distribute dependencies/libraries.
- **Log Streams**: View execution logs via CloudWatch.

### 💰 Pricing
- Charged only when code is executed.

### 🔧 Steps to Run
1. Upload code.
2. Set event trigger.
3. Execute on event trigger.
4. Monitor logs/output.

---

## ☁️ Google Cloud Functions

### 🔍 Overview
- Event-driven compute service from Google Cloud.
- Single-purpose functions triggered by cloud events.
- Managed environment (no infra management).

### 🔁 Working
- Events (e.g., object upload to Cloud Storage) trigger functions.
- Stateless execution; no memory of prior invocations.
- Can invoke APIs, interact with other services, etc.

### 🔗 Events & Triggers
- **Events**: E.g., file upload, HTTP request.
- **Triggers**: Define event + associated data.
- **Event Data**: Passed to the function for processing.

### 📦 Event Providers
- HTTP, Cloud Storage, Cloud Pub/Sub, Firebase, Stackdriver, Firestore, GCE, BigQuery.

---

## 🔷 Azure Functions

### 🔍 Overview
- Microsoft’s serverless offering.
- Focus on writing code; infrastructure managed by Azure.
- Code + `function.json` config file (auto-generated or manual).

### ⚙️ Features
- Supports C#, Java, Python, JavaScript, PowerShell.
- Flexible deployment & monitoring.
- **Pricing**: Consumption (pay-per-execution), Premium, App Service.

### 📑 Use Cases
- Serverless APIs, mobile/web backends.
- IoT data processing, event streaming, ML pipelines.
- Business automation, integration, SaaS.

### 🧩 Scenarios
- Web backends (e.g., retail)
- Mobile app backends (e.g., finance)

---

## 📚 Reference Paper
- **“What serverless computing is and should become”**  
  Authors: Schleier-Smith, Sreekanti, Khandelwal, et al.  
  **Commun. ACM (2021)** – DOI: [10.1145/3406011](https://doi.org/10.1145/3406011)
---
---

## 🌿 **Sustainable Cloud Computing – Key Concepts**

### ✅ **Basics**
- **Goal**: Reduce energy consumption, carbon footprint, and improve reliability of **Cloud Data Centers (CDCs)**.
- **CSPs** rely heavily on CDCs to meet demand; but high energy use = high cost + environmental impact.
- Cloud services must become **energy-efficient, cost-effective, and reliable**.

---

## ⚡ **Energy Management in CDCs**
- Energy consumption is growing; expected to reach **8000 TWh by 2030**.
- Major energy consumers in CDCs:
  - **Processor** – 45%
  - **Cooling Systems** – 20%
  - **Memory** – 15%
  - **Storage & Network** – 10% each
- **Inefficient resource usage** (idle state) increases energy cost.

---

## 🔋 **Sustainability Strategies**
- Use **renewable energy** (solar, wind) to power CDCs.
- **Relocate CDCs** to:
  - Areas with free cooling
  - Green energy access
  - Waste heat recovery opportunity
- Implement **energy-aware resource management** and **load balancing**.

---

## 🧠 **Sustainable Cloud Architecture – Conceptual Model**
- **Cloud Architecture**: SaaS, PaaS, IaaS
- **Cooling Manager**: Monitors thermal alerts; triggers heat control
- **Power Manager**:
  - Manages **renewables + grid** via ATS (Automatic Transfer Switch)
  - Uses **Power Distribution Unit (PDU)**
- **Remote CDCs**: For **VM migration** & load balancing

---

## 🛡️ **Reliability and Its Impact**
- **Reliability issues** include:
  - SLA violations
  - Security risks
  - Delays in service
  - Data loss during VM migration
- Trade-off between **energy saving vs reliability** (e.g., DVFS increases delay).
- Excessive **power cycling harms hardware reliability**.

---

## 🧩 **Important Components of Sustainable Cloud Computing**

### 1. **Application Model**
- Efficient models: **Data Parallel**, **Function Parallel**, **Message Passing**
  
### 2. **Thermal-Aware Scheduling**
- Minimizes hotspots, thermal gradients, cooling costs
- Types: **Reactive** and **Proactive**

### 3. **Virtualization**
- Enables **VM migration** to balance load and use renewable energy
- Reduces physical server usage

### 4. **Capacity Planning**
- Optimize resources per application
- Focus on ROI, merging similar workloads

### 5. **Renewable Energy**
- Factors: Type (solar/wind), location (on/off-site), energy storage
- Challenge: **Unpredictable supply + high initial cost**
- Use **energy-aware workload migration**

### 6. **Waste Heat Utilization**
- Use **vapor-absorption cooling** to recycle heat
- Reduces cooling energy expense

---

## 📉 **Implications**
- **Improving energy efficiency** lowers costs, but may increase service delay.
- **DVFS** reduces energy but increases response time.
- **Sustainable designs** must maintain a **balance between energy, cost, and service reliability**.

---

## 📚 **Key References**
1. Rajkumar Buyya & Sukhpal Singh Gill – Sustainable Cloud Computing, Cutter Consortium, 2018.
2. Anders SG Andrae – Trends to 2030, *Challenges*, 2015.
3. Zhenhua Liu et al. – Renewable-aware workload management, *SIGMETRICS*, 2012.
4. ACM Survey 2018 – A 360° View on Sustainable Cloud Computing.

---
---

## 🌱 **Sustainable Cloud Computing – Overview**
- **Goal**: Reduce energy consumption, carbon footprint, and improve reliability of Cloud Data Centers (CDCs).
- **CSPs** rely on CDCs which are energy-intensive.
- Must adopt energy-efficient, reliable, and eco-friendly methods.

---

## 🧩 **Components of Sustainable Cloud Computing**
1. **Application Model**
   - Efficient application structure improves energy efficiency.
   - Models: Data Parallel, Function Parallel, Message Passing.

2. **Energy Management**
   - Resource energy share: Processor 45%, Memory 15%, Storage 10%, Network 10%, Cooling 20%.
   - **DVFS**: Saves energy but increases latency.
   - Power regulation and sleep mode impact reliability and SLA.
   - Essential: Optimal software, air ventilation, temperature monitoring.

3. **Thermal-aware Scheduling**
   - Types: Single-core, Multi-core; Mechanisms: Reactive, Proactive.
   - Reduces **hotspots**, **thermal gradients**, and cooling cost.
   - Focus: Power Usage Effectiveness (PUE), but may not reduce TCO.

4. **Virtualization**
   - VM migration for load balancing and renewable energy use.
   - VM-based consolidation reduces physical server usage.
   - Supports: Load balancing, elasticity, fault tolerance, scheduling.

5. **Capacity Planning**
   - For power, IT resources, and workloads.
   - Merge applications for better resource utilization.
   - Analyse workloads for deadline-sensitive tasks.

6. **Renewable Energy**
   - Use: Solar, Wind, Water.
   - Reduces **Carbon Usage Efficiency (CUE)**.
   - Challenges: Unpredictability, high capital cost.
   - Needs: Workload migration, energy-aware load balancing, proximity to RE sources.

7. **Waste Heat Utilization**
   - Vapor absorption cooling reuses heat.
   - Reduces cooling expenses.
   - Improves energy efficiency and makes PUE ideal.

8. **Cooling Management**
   - Due to heat generation from high computation density.
   - Need: Effective cooling systems to manage temperature and reduce energy.

---

## 🔍 **Taxonomy of Sustainable Cloud Computing**
- Categories of research:
  - Application design
  - Sustainability metrics
  - Capacity planning
  - Energy management
  - Virtualization
  - Thermal-aware scheduling
  - Cooling management
  - Renewable energy
  - Waste heat utilization

---

## 📐 **Sustainability Metrics**
- Track carbon emissions, energy use, and efficiency.
- Help assess and improve CDC sustainability.

---

## ⚙️ **Application Design**
- Green ICT-based apps reduce energy use.
- Efficient designs enhance sustainability.

---

## 💡 **Key Points**
- High power usage of CDCs → High operational & carbon cost.
- Future CDCs must use **renewable energy**.
- Balance **performance**, **reliability**, and **sustainability**.
- Use innovative tech like **DVFS**, **thermal-aware scheduling**, **VM migration**, **waste heat utilization**.

---

## 📚 **Important References**
1. Buyya & Gill (2018): Foundations & future directions.
2. Gill & Buyya (2018): Taxonomy and 360° view (ACM).
3. Andrae & Edler (2015): Global electricity trends.
4. Liu et al. (2012): Renewable & cooling-aware workload management.
5. Gill et al. (2018): RADAR – self-configuring resource management.

---
