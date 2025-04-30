## 📘 **Service Level Agreement (SLA)**

### What is SLA?
- A **formal contract** between a Service Provider (SP) and a Service Consumer (SC)
- Defines **performance and availability** guarantees
- Includes **Service Level Objectives (SLOs)** – measurable metrics like uptime, response time, etc.

---

### 📌 **Problem 1: SLA Violation Check**
**Given:**
- SLA Availability = 99%
- Uptime required = 12 hrs/day for 30 days = 360 hrs/month
- Total downtime = 10.75 hrs

**Allowed downtime =**  
= (1% of 360) = **3.6 hrs**  
**Since 10.75 > 3.6**, SLA **is violated**

---

### 📌 **Problem 2: Cost with SLA Compensation**

**SLA:**  
- Availability: 99.95%  
- Service Time: 12 hrs/day × 30 = 360 hrs  
- Downtime occurrences: 5 hrs, 30 min, 1.5 hrs, 15 min, 2.42 hrs  
- Total downtime = 5 + 0.5 + 1.5 + 0.25 + 2.42 = **9.67 hrs**  
- Actual Uptime = 360 - 9.67 = **350.33 hrs**  
- Uptime % = (350.33 / 360) × 100 = **97.3%**

**Based on SLA:**
- 97.3% < 99% → 25% credit  
- Cost = $50 × 30 = **$1500**  
- Credit = 25% of 1500 = **$375**  
- **Effective cost = $1125**

---

## 💡 Cloud Economics & Utility Pricing

### Key Concepts:
- **Utility Pricing**: Pay-per-use model.
- **On-Demand Resource**: Scalable resources allocated based on demand.
- **When is Cloud Cheaper than Owning?**

#### Conditions:
- Utility premium (U) < Peak Demand / Average Demand  
- Cost formulas:
  - **Baseline cost**: `BT = P × B × T`
  - **Cloud cost**: `CT = A × U × B × T`

---

### 📌 Assignment 1: Penalty Calculation

Given:
- D(t): demand function
- R(t) = D(t) + δ (dD(t)/dt), where δ = π/12
- Cost/unit resource/unit time = 0.9  
- Penalty = ∫ |D(t) - R(t)| dt = ∫ |− δ dD(t)/dt| dt = δ ∫ |dD(t)/dt| dt

(Use calculus to compute the definite integral over the time period and multiply by 0.9)

---

### 📌 Assignment 2: Cloud vs. Owning Cost

Given:
- D(t) = 50(1 + e^(−t)), T = 100
- B = 120, C = 200 → U = 1.66

Compute:
- Avg Demand (A): average of D(t) over [0,100]
- Compare: A × U < P → Cloud is cheaper if true

---

### 📌 Assignment 3: In-house vs Cloud Cost

#### Given:
| Factor | In-house | Cloud |
|--------|----------|-------|
| Cores | 12 | 8 |
| Cost/hour | - | ₹42 |
| Power & Cooling | ₹22/hr | - |
| Management | ₹6/hr | ₹1/hr |
| Efficiency | 40% | 80% |

#### Steps:
- In-house core-hour cost = Total hourly cost / (Efficiency × cores)
- Cloud core-hour cost = ₹42 / (0.8 × 8)
- Compare both for cost-effectiveness

---

## 🗂️ MapReduce

### MapReduce Model:
- **Map**: Transform input key-value pairs
- **Reduce**: Aggregate values based on keys
- Fault-tolerant, scalable computation model

---

### 📌 Problem 1: Block Calculation in HDFS
- HDFS block size = 64MB  
- Files: 64KB (1 block), 65MB (2 blocks), 127MB (2 blocks)  
→ **Total blocks = 5**

---

### 📌 Problem 2: Avg of Integers

#### Input: A = (10, 20, 30, 40, 50)

**Map (key, value):**  
Each value → emit (key, (value, 1))

**Reduce:**  
Sum all values and counts → emit (key, sum/count)

**Output:**  
(1, (150, 5)) → Avg = 150 / 5 = 30

---

### 📌 Problem 3: Salary by Gender

Input:
```
John, M, 10000
Martha, F, 15000
...
```

**Map:** emit (Gender, (Salary, 1))  
**Reduce:** sum salaries and counts, then compute avg

---

### 📌 Problem 4: Word Length Categorization

**Categories:**
- Tiny: 1–2 letters
- Small: 3–5 letters
- Medium: 6–9 letters
- Big: ≥10 letters

**Map:**  
Emit (Category, 1)

**Reduce:**  
Sum counts per category

---

## 🌱 Green Computing & Resource Management

### Key Points:
- Minimize power with smart **VM scheduling**
- Use **dynamic migration** & **node shutdown**
- Efficient **rack and data center design**
- **Penalty cost** ∝ |D(t) – R(t)|

---
---

## 📘 Types of Cloud Resources

- **Physical Resources**: Computers, Disks, Networks, Databases, Scientific Instruments  
- **Logical Resources**: Execution, Monitoring, Communication tools  

---

## ⚙️ Resource Management in Cloud

- **Definition**: Efficient control of cloud resources/services to users, apps, or other services.

---

## ☁️ IaaS (Infrastructure as a Service)

- Provides: **VMs, Storage, Firewalls, Load Balancers, Networks**
- Major challenge: **Efficient Resource Management**

---

## 🎯 Resource Management Objectives

- Scalability  
- QoS (Quality of Service)  
- Optimal utility  
- Reduced latency/overhead  
- Improved throughput  
- Cost-effectiveness  
- Simplified interfaces  
- Specialized environment  

---

## ❗ Resource Management Challenges

### **Hardware-level**
- CPU, Memory, Storage  
- Workstations, Networks  
- Sensors, Actuators  
- Power, OS, Security  
- Bandwidth, Delays  

### **Logical-level**
- APIs, Protocols, Load Balancing  

---

## 🔑 Resource Management Aspects

| Aspect | Description |
|--------|-------------|
| Provisioning | Allocating resources to users |
| Allocation | Distributing resources economically |
| Adaptation | Dynamically adjusting resources |
| Mapping | Matching user needs to provider resources |
| Modeling | Predict future resource needs |
| Estimation | Guess actual resources needed |
| Discovery | Identify available resources |
| Brokering | Agent-based negotiation of resources |
| Scheduling | Timing of resource usage & allocation |

---

## 🔄 Resource Provisioning Approaches

- **Game Theory** (Nash Equilibrium): Runtime VM allocation  
- **Network Queuing Model**: App-tier performance modeling  
- **K-means + Queuing**: Prototype provisioning  
- **SEDF Scheduler**: VM CPU share management  
- **Adaptive**: Bottleneck detection  
- **SLA-Oriented**: Provision based on SLA needs  
- **Dynamic Framework**: Near-optimal allocation under change  
- **OCRP**: Handles demand/price uncertainty

---

## 🔁 Resource Allocation Approaches

- **Market-oriented**: Maximize revenue and user satisfaction  
- **Intelligent Multi-agent**: Learns user context  
- **Energy-aware**: Ant-colony mimic  
- **Performance-based**: Co-location impact analysis  
- **Dynamic**: Auto-scaling VMs  
- **Real-time**: For small IaaS providers  
- **Scheduling + DAGs**: Efficient co-location

---

## 🗺️ Resource Mapping Approaches

- **Symmetric pattern**: User-resource matching  
- **Load-aware**: Multicast + cache reuse  
- **Min. Congestion**: Graph-based optimization  
- **Iterated Local Search**: Split user requests  
- **SOA API**: QoS-aware mapping  
- **Impatient Task Mapping**: Genetic algorithms  
- **DEVA**: Behavior-driven modeling  
- **Virtual to Substrate Mapping**: Traffic-capable mapping

---

## 🔄 Resource Adaptation Approaches

- **Reinforcement Learning**: Optimal adaptive policy  
- **Web-Service Framework**: Evaluates adaptation  
- **OnTimeMeasure**: Thin-client cloud adaptation  
- **Virtual Networks**: Traffic isolation and security  
- **DNS Load Balancing**: Auto-scale with load balancers  
- **Hybrid**: Bin packing + gradient search (multi-tier apps)

---

## 📏 Performance Metrics

- **Reliability**  
- **QoS**  
- **Ease of Deployment**  
- **Delay**  
- **Control Overhead**

