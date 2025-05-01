---

## **VM Migration Overview**
VM Migration is the process of moving a running virtual machine (VM) from one physical host to another without disrupting its operation. It involves transferring CPU state, memory, storage, and network connections.

### **Why Migrate VMs?**
- **Load Balancing:** Efficient distribution of VM workloads.
- **System Maintenance:** Perform updates without affecting services.
- **Power Management:** Consolidate VMs to save energy.
- **Quality-of-Service (QoS):** Meet service level agreements.
- **Fault Tolerance:** Avoid downtime in case of failures.
- **Resource Sharing:** Optimize under-utilized resources.

---

## **Types of VM Migration**
1. **Cold (Non-Live) Migration**
   - VM is paused or shut down.
   - Simpler but causes high downtime.
   
2. **Hot (Live) Migration**
   - VM keeps running during migration.
   - Minimal service disruption.

---

## **Live Migration Approaches**

### 1. **Pre-Copy Approach**
- **Phases:**
  - *Pre-Copy:* VM continues to run, memory pages copied iteratively.
  - *Termination:* Based on iteration count, memory copied, or dirty pages threshold.
  - *Stop-and-Copy:* VM paused, remaining dirty pages and CPU state copied.
  - *Restart:* VM resumes on the destination.
- **Used by:** Xen, KVM, VMware.

### 2. **Post-Copy Approach**
- **Steps:**
  - *Stop:* VM paused and CPU state copied.
  - *Restart:* VM starts on destination with empty memory.
  - *On-Demand Copy:* Pages are pulled as needed (demand paging).
- Reduces total data transfer but sensitive to faults during migration.

---

## **Memory Migration Techniques**
- **Push:** Copy pages while VM runs; resend dirtied pages.
- **Stop-and-Copy:** Pause VM, copy all pages, then resume.
- **Pull:** Resume VM on destination; fetch pages on-demand.

---

## **When to Migrate**
- To decommission a server.
- To reduce load on congested servers.

---

## **Migration Considerations**
- **Downtime:** Total unavailability time of services.
- **Migration Time:** Duration to complete VM transfer.
- **Avoid Resource Contention:** During migration, prevent service degradation.

---

## **What Gets Migrated?**
- **CPU Context**
- **Memory**
- **Disk (if not shared via NAS)**
- **Network Config (MAC/IP)**
- **I/O Devices (virtual devices easier)**

---

## **Analysis (Formulas)**

### **Non-Live Migration**
- `Tmig = Vm / R`
- `Tdown = Tmig`

### **Pre-Copy Migration**
- `Ti,mig = (Vm / R) * (1 - r^(n+1)) / (1 - r) + Tres`
- `Ti,down = (r^n) * (Vm / R) + Tres`

Where:
- `Vm`: Memory size of VM  
- `R`: Transmission rate  
- `r`: (P × D)/R; P = page size, D = dirty rate  
- `n`: Iterations  
- `Tres`: Restart time  
- `Vth`: Threshold to stop copying  

---

## **Multiple VM Migrations**

### **Serial Migration**
- VMs migrated one after another.
- Downtime increases due to cascading wait.
- Downtime: `Tsdown = (Vm / R) * r^n + (m - 1) * (Vm / R) * ((1 - r^(n+1)) / (1 - r)) + Tres`

### **Parallel Migration**
- All VMs migrate simultaneously.
- Transmission rate is divided: each gets `R/m`.
- Synchronized stop-and-copy phase.

---
---

## ✅ **Container-Based Virtualization (CBV)**  
- **Virtualization**: Sharing of physical resources among multiple users/applications.
- **Containers**: Lightweight, OS-level virtualization; package code + dependencies.
- **Benefit**: Portable, efficient, and fast compared to traditional VMs.

---

## ✅ **Containers – Key Concepts**
- **Virtualize at OS level** (not hardware level like VMs).
- Share **OS kernel**, making them **lightweight and fast**.
- Run anywhere: on-premises, cloud, personal laptops.
- Each container has its **own filesystem, CPU, memory share**, etc.
- Isolated from other apps, yet uses shared host OS.

---

## ✅ **Container Advantages**
- **Portability**: Same behavior across dev, test, and prod environments.
- **Efficiency**: Low overhead, fast startup, optimized resource usage.
- **Isolation**: Clean, secure execution environment.
- **Agility**: Easier deployment, scaling, and testing.
- **DevOps-friendly**: Supports CI/CD pipelines and microservices.

---

## ✅ **Containers vs. Virtual Machines**
| Feature | Containers | Virtual Machines |
|--------|------------|------------------|
| Virtualize | OS-level | Hardware-level |
| Speed | Fast | Slow (boots full OS) |
| Overhead | Low | High |
| Size | MBs | GBs |
| Isolation | Less than VMs | Strong |

---

## ✅ **Docker – Overview**
- Platform to **build, ship, run** applications in containers.
- Solves issues of **software deployment and dependency management**.
- Uses **images** (templates) to create **containers** (instances).

---

## ✅ **Docker Key Concepts**
- **Image**: Read-only template with code + dependencies.
- **Container**: Running instance of an image.
- **Docker Engine**: Core runtime to build and run containers.
- CLI/API used for managing containers.

---

## ✅ **Docker Benefits**
- **Replaces VMs**: More lightweight and faster.
- **Prototyping**: Quick, disposable dev environments.
- **Packaging**: No need to manage external dependencies.
- **Supports Microservices**: Run services independently.
- **Debugging**: Easier environment replication.
- **Offline Productivity**: Local development possible.

---

## ✅ **Kubernetes – Overview**
- **Open-source** container orchestration platform.
- Automates **deployment, scaling, load balancing**, and **management** of containers.
- Originally from **Google**, now under **CNCF**.

---

## ✅ **Kubernetes Key Concepts**
- **Cluster**: Group of machines (nodes) managed together.
- **Node**: A machine (physical/virtual) running containerized apps.
- **Pod**: Smallest deployable unit in Kubernetes, holds one/more containers.
- **Control Plane**: Manages nodes and workloads (includes scheduler, API server).
- **Worker Nodes**: Run the application containers (in Pods).

---

## ✅ **Container Deployment Models**
| Model | Description |
|-------|-------------|
| **Traditional** | Apps on physical servers, no resource boundaries. |
| **Virtualized** | Multiple VMs on one server, OS per VM. |
| **Containerized** | Apps share OS kernel, lightweight, portable. |

---

## ✅ **Common MCQ Focus Areas**
- Difference: VM vs Container  
- OS-level vs Hardware-level virtualization  
- Docker: image vs container  
- Kubernetes: Pod, Node, Control Plane  
- Container advantages: portability, efficiency  
- Use cases: Microservices, CI/CD, cross-platform deployment  

---
---

## 🔹 **Introduction to Containers and Docker**
- **Container**: Standard unit of software packaging code + dependencies to run reliably in any environment.
- **Docker**: A platform to develop, ship, and run applications in containers.
- **Docker Container Image**: Lightweight, standalone, executable software package.

---

## 🔹 **Benefits of Containers**
1. **Separation of Responsibility** – Devs focus on code; Ops on deployment.
2. **Workload Portability** – Runs on Linux, Windows, Mac, VM, cloud, etc.
3. **Application Isolation** – Virtualizes OS-level resources (CPU, memory, network).
4. **Efficiency** – Shares OS kernel, uses less memory compared to VMs.
5. **Security** – Strong isolation and consistency across environments.

---

## 🔹 **Containers vs VMs**
| Feature            | Containers                         | VMs                                |
|--------------------|------------------------------------|-------------------------------------|
| Virtualization     | OS-level                           | Hardware-level                      |
| OS Requirements    | Share host OS kernel               | Full OS per VM                      |
| Resource Usage     | Lightweight                        | Heavy (more memory & storage)       |
| Isolation          | Less strict                        | Stronger                            |

---

## 🔹 **Standalone vs Containerized Deployment**
- **Standalone**: Manual install of MySQL, PHP, Apache, PHPMyAdmin; hard to move.
- **Containerized**: Encapsulated services; portable; easy to replicate & deploy.

---

## 🔹 **Demo Objective**
- Deploy **MySQL + PHPMyAdmin** using Docker.
  - **MySQL** – Open-source relational DB.
  - **PHPMyAdmin** – Web-based GUI for managing MySQL.

---

## 🔹 **Docker Engine**
- **Docker Engine** runs Docker containers.
- **Key Properties**:
  - *Standardized*
  - *Lightweight*: No OS per app
  - *Secure*: Strong isolation by default

---

## 🔹 **Key Docker Concepts**
- **Image**: Blueprint for a container.
- **Container**: Runnable instance of an image.
- **CLI/API**: Used to manage containers.

---

## 🔹 **Kubernetes Overview**
- Open-source platform to manage **containerized workloads/services**.
- Provides:
  - **Deployment**
  - **Scaling**
  - **Load Balancing**
  - **Monitoring/Logging**
- Not monolithic – optional & pluggable components.

---

## 🔹 **Kubernetes Components**
- **Cluster**: Comprises Control Plane + Worker Nodes.
- **Worker Nodes**: Run application workloads in **Pods**.
- **Control Plane**: Manages the cluster (scheduling, scaling, updates).
- Ensures **high availability & fault-tolerance**.

---

## 🔹 **Deployment Models**
| Model              | Description                                      |
|--------------------|--------------------------------------------------|
| Traditional        | Apps on physical servers (no resource isolation) |
| Virtualized        | Multiple VMs on a physical server                |
| Containerized      | Lightweight, share OS, better portability        |

---
