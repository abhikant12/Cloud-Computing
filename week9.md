### 🌩️ **Fog Computing Overview**
- **Definition**: Extends cloud to edge devices for low latency.
- **Introduced by**: Cisco Systems.
- **Goal**: Real-time applications by processing data closer to end-users.

---

### 🔄 **Cloud vs Fog vs Edge Computing**
| Feature              | Cloud                      | Fog                        | Edge                        |
|----------------------|----------------------------|----------------------------|-----------------------------|
| Location             | Centralized                | Intermediate layer         | Very close to source        |
| Latency              | High                       | Medium                     | Very Low                    |
| Data Processing      | In Data Centers            | Near Edge (Gateways)       | On Device (Sensors)         |
| Cost                 | High (Execution cost)      | Moderate                   | Low                         |
| Application Suitability | Non-real-time tasks    | Real-time tasks            | Ultra-low latency needs     |

---

### 📊 **Health Cloud–Fog–Edge Case Study (iFogSim Simulations)**
- **Levels**: Cloud → ISP → AreaGW → Mobile → IoT.
- **Latency**: Lower in Fog as modules are at Area Gateway.
- **Network Usage**: Fog uses less bandwidth.
- **Execution Cost**: Higher in Cloud (uses public resources).
- **Energy Consumption**: Fog is more energy-efficient.

---

### 🧠 **Cloud–Fog Integration**
- **Three Layers**: Client (Edge) → Fog → Cloud.
- **Service Flow**:
  - Fog Server Manager allocates tasks to VMs.
  - If fog lacks resources → offload to Cloud.
- **Goal**: Decentralized computing for responsiveness & efficiency.

---

### ⚙️ **Resource Management Challenges in Cloud-Only IoT**
- High latency & bandwidth needs.
- Not ideal for time-sensitive applications.
- Fog/Edge complements Cloud – not replaces it.

---

### 🛠️ **Resource Management Approaches**

#### 1. **Architectures**
- **Data Flow**: Cloud → Edge or vice versa.
- **Control**: Centralized or distributed.
- **Tenancy**: Single/multi-application support on nodes.

#### 2. **Infrastructure**
- **Hardware**: Routers, gateways, Raspberry Pi, etc.
- **System Software**: OS, virtualization.
- **Middleware**: Manages VMs/containers.

#### 3. **Algorithms**
- **Discovery**: Identify nearby edge resources.
- **Benchmarking**: Measure CPU, memory, network.
- **Load Balancing**: Optimize task distribution.
- **Placement**: Allocate tasks based on resource availability & environment.

---

### 📚 **Important References**
- **iFogSim**: Toolkit for modeling fog/edge environments.
- **Cheol-Ho Hong & Blesson Varghese**: Key survey on fog/edge resource management.
- **Mahmud & Buyya**: Modeling/simulation of Fog/Edge computing.

---
---

### 🔸 **Fog Computing Basics**
- **Fog**: A virtualized platform between users and cloud servers.
- **Features**: Location-aware, low latency, scalable, mobile support, better bandwidth utilization.
- **Layers**: IoT Devices (End), Fog Nodes, Cloud Data Center.

---

### 🔸 **Service Placement Problem**
- **Definition**: Mapping of app components and links to computing devices (nodes) & physical network (edges).
- **Goals**: Meet app requirements, optimize objectives (latency, energy, cost), and respect constraints.

---

### 🔸 **Constraints in Placement**
1. **Resource**: Limited CPU, RAM, bandwidth, storage.
2. **Network**: Latency, bandwidth.
3. **Application**:
   - *Locality*: Specific service-location requirement.
   - *Delay sensitivity*: Deadline-based deployment or processing.

---

### 🔸 **Optimization Objectives**
- **Minimize**: Latency, cost, energy.
- **Maximize**: Resource utilization, QoS.

---

### 🔸 **Offloading**
- **From User to Edge**:
  - Uses edge nodes to reduce device load.
  - Techniques: App partitioning, caching.
- **From Cloud to Edge**:
  - Moves workload closer to user.
  - Techniques: Server offloading, caching.

---

### 🔸 **Control Models**
- **Centralized**: Single controller manages placement.
- **Distributed**: Multiple controllers; more scalable.

---

### 🔸 **Hardware in Fog/Edge**
- Low-power devices: Routers, mobile phones, gateways, home systems.
- Forms a distributed computing environment for IoT/CPS.

---

### 🔸 **System Software**
- Manages fog/edge device resources.
- Supports **multi-tenancy** and **isolation**.
- Types:
  - *System Virtualization*
  - *Network Virtualization*

---

### 🔸 **Middleware Functions**
- Performance monitoring, orchestration, communication protocols.

---

### 🔸 **Key Algorithms**
1. **Discovery**: Identify usable edge resources.
2. **Benchmarking**: Measure performance for placement.
3. **Load Balancing**: Fair resource distribution.
4. **Placement**: Optimal deployment of applications/services.

---

## 🌐 **Cloud Federation**

### 🔸 **Definition**
- Integration of multiple cloud providers (CSPs) to share resources.
- Supports capacity use, interoperability, service catalogs, and SLA awareness.

---

### 🔸 **Federation Motivation & Benefits**
- **Maximize** resource usage, **minimize** power, **load balance**, expand CSP reach, ensure **global utility**.

---

### 🔸 **Federation Characteristics**
- Voluntary inter-cloud collaboration.
- Geographic separation.
- Regulated federal agreement.

---

### 🔸 **Federation Architectures**
1. **Loosely Coupled**:
   - Minimal control & monitoring over remote resources.
   - E.g., cloud bursting for peak demand.
2. **Partially Coupled**:
   - CSP contracts allow some control (e.g., VM placement, monitoring).
   - Allows virtual networks across sites.
3. **Tightly Coupled**:
   - Same admin; full control & monitoring.
   - Supports advanced features (e.g., VM migration, HA, cross-site storage).

---

### 🔸 **Specific Architectures**
- **Hybrid / Bursting**:
  - Private cloud + public cloud during peak load.
  - Loosely coupled.
- **Broker**:
  - Deploys resources based on cost, performance, energy.
  - Loosely coupled.
- **Aggregated**:
  - Partner clouds aggregate resources.
  - Partially coupled.
- **Multitier**:
  - Hierarchical cloud OS over multiple sites.
  - Tightly coupled, full resource control.

---

### 🔸 **Important References**
- Farah Aït Salaht et al., ACM Computing Surveys, 2020.
- Cheol‐Ho Hong et al., ACM Computing Surveys, 2019.
- Moreno‐Vozmediano et al., IEEE Computer, 2012.

---
