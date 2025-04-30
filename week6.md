---
---

## **Security Fundamentals**

### **Basic Components**
- **Confidentiality**: Keep data hidden from unauthorized access.
- **Integrity**: Ensure data is accurate and trustworthy (includes authentication).
- **Availability**: Ensure data and services are accessible when needed.

### **Types of Security Attacks**
1. **Interruption** – Attacks availability.
2. **Interception** – Attacks confidentiality.
3. **Modification** – Attacks integrity.
4. **Fabrication** – Attacks authenticity.

### **Threat Classes**
- **Disclosure** (e.g., snooping)
- **Deception** (e.g., spoofing, modification)
- **Disruption** (e.g., DoS)
- **Usurpation** (e.g., spoofing, unauthorized control)

### **Security Goals**
- **Prevention**: Stop violations of policy.
- **Detection**: Identify when violations occur.
- **Recovery**: Contain and fix breaches.

---

## **Security Mechanisms & Models**
- **Policies** define what is allowed.
- **Mechanisms** enforce those policies.
- **Assurance** is achieved via:
  - Specification → Design → Implementation.

### **Types of Mechanisms**
- **Secure**: All reachable states are secure.
- **Precise**: Matches secure states exactly.
- **Broad**: Covers more than required—less safe.

---

## **Human & Operational Issues**
- **Cost-Benefit & Risk Analysis**: Weigh security cost vs. potential damage.
- **Legal & Cultural Barriers**: Compliance with local laws/customs.
- **Human Factors**: Insiders, social engineering, responsibility allocation.

---

## **Network Security Lifecycle**
1. **Policy Formation**
2. **Policy Implementation** (Firewalls, IDS, Honeypots)
3. **Reconnaissance** (Passive vs. Active)
4. **Vulnerability Scanning** (e.g., Nessus, Metasploit)
5. **Penetration Testing**
6. **Post-Attack Forensics**

---

## **Cloud Security Specifics**

### **Cloud Advantages**
- Elastic scalability, no upfront costs, “pay-as-you-go”.

### **New Threats in Cloud**
- **Co-tenancy risks** (shared infrastructure)
- **Loss of control** over data/applications.
- **Reputation & fate-sharing** across tenants.

### **Cloud Security Stack**
- **IaaS, PaaS, SaaS** — Each shifts responsibility between provider and user.

---

## **Gartner's 7 Cloud Risks**
1. **Privileged User Access**
2. **Regulatory Compliance & Audit**
3. **Data Location**
4. **Data Segregation**
5. **Recovery**
6. **Investigative Support**
7. **Long-Term Viability**

---

## **Other Key Cloud Security Issues**
- **Virtualization** risks: Hypervisor vulnerabilities (e.g., backdoors, ARP poisoning).
- **Identity & Access Management**
- **Application Security**
- **Data Lifecycle Management**

---
---

## **Cloud Security: Key Points from the Paper**

### **1. Research Context**
- **Paper**: “Hey, You, Get Off of My Cloud!” – CCS 2009.
- **First work** on **cloud cartography**.
- **Cloud platform**: Amazon EC2.
- Achieved **40% co-residency success** with victim VM.

---

### **2. Cloud Risks**
- **New trust model** between customers & providers.
- **Multi-tenancy risks**: VMs of different users share hardware.
- **Side-channel attacks** possible due to resource sharing.

---

### **3. Multi-tenancy Threats**
- **Cross-VM info leakage**: via CPU cache, memory, disk I/O.
- **VM escape vulnerabilities**: attacker breaks hypervisor isolation.
- **No control** over co-residence.

---

### **4. Attack & Threat Model**
- **Assumes** trusted provider & no software exploits.
- **Attack steps**:
  1. **Placement** – place attacker VM on same host.
  2. **Extraction** – use side-channels to leak data.
- **Malicious VMs** are regular EC2 instances (max 20/account).
- **Victims**: confidentiality-reliant cloud users.

---

### **5. Research Questions (Q1–Q4)**
- **Q1**: Can instance location be discovered? → **Yes** (cloud cartography).
- **Q2**: Can co-residency be detected? → **Yes**, via network & IP analysis.
- **Q3**: Can attacker get co-resident? → **Yes**, via placement techniques.
- **Q4**: Can cross-VM leakage happen? → **Yes**, via covert side-channels.

---

### **6. Amazon EC2 Internals**
- **Uses Xen hypervisor** with Dom0 VM.
- **Placement variables**: instance type, region, availability zone.
- Each instance has **internal** (private) & **external** IP.

---

### **7. Cloud Cartography (Q1)**
- Map EC2 using **IP address ranges**.
- Use tools: **nmap**, **hping**, **wget**.
- Match **internal IPs** to identify placement patterns.

---

### **8. Co-residency Detection (Q2)**
- Signs of co-residency:
  - **Same Dom0 IP**
  - **Low ping latency**
  - **Close internal IPs**
- Verified via **disk-based covert channel** (sender modulates disk usage, receiver measures read time).

---

### **9. Causing Co-residence (Q3)**
- **Brute-force approach**: launch many probe VMs → ~8.4% co-residency success.
- **Placement locality**: EC2 often places recently started VMs together.
- **Flooding**: launch 20 VMs quickly → **40% co-residency** success.

---

### **10. Exploiting Co-residence (Q4)**
- **Cache-based leakage**:
  - Detect computation load.
  - **Traffic analysis**: estimate web traffic via load variation.
  - **Keystroke timing**: infer password typing intervals.

---

### **11. Countermeasures**
- **Mapping**:
  - Randomize IP allocations.
  - Block tools (nmap, traceroute).
- **Co-residency**:
  - Hide Dom0 details.
  - Avoid co-location (hurts cost efficiency).
- **Side-channels**: **No effective solution** currently.

---

### **12. Key Takeaways**
- **Cloud security is weakened** by shared infrastructure.
- **Co-residence is possible** and dangerous.
- **Real-world cloud** (Amazon EC2) was vulnerable.
- **Side-channel attacks** can leak **sensitive data**, even without software bugs.

---
---

### 🔐 **Security Issues in Cloud Computing**
- **Unique challenges**: Co-tenancy, outsourced data/application control loss.
- **Common concerns**: Inadequate policies, insufficient security controls.
- Need for **trust relationships** between customers and cloud vendors.

---

### 🌐 **SaaS Cloud-based Collaboration**
- **Entities**: Service Consumers (users/apps/orgs), Service Providers (SaaS vendors).
- **Collaboration Types**:
  - **Tightly-coupled** (federated)
  - **Loosely-coupled** (focus area)
- **Issues**:
  - Data integrity risks in shared environments.
  - Existing security/auth mechanisms are limited for loose coupling.

---

### ⚠️ **Motivations & Challenges**
- SaaS cloud = **Maximum lack of control**, limited audit/reporting.
- Cloud SLAs are **inconsistent**; not always trustworthy.
- **Dynamic data sharing** poses **security risks**.
- Main focus: **Select ideal SaaS provider** and **secure loosely-coupled collaborations**.

---

### 🎯 **Objectives**
1. **SelCSP**: Framework to select **trustworthy, competent** SaaS providers.
2. Minimize **access risk & uncertainty** when accepting anonymous access requests.
3. Heuristic for **IDRM (Inter-Domain Role Mapping)**: minimize excess permissions.
4. **Distributed secure collaboration framework**: detect/remove access conflicts **locally**.

---

### ⭐ **Trust Models in Cloud**
- Most lack **mathematical validation**.
- Based on **QoS + Trust** [Liu’04, Garg’13].
- Goal: Model **trust, reputation, competence** of SPs.

---

### 📜 **Service Level Agreements (SLA)**
- Mostly guarantee **availability only**.
- Lack standardization in clauses & compensations [Habib’11].
- **Goal**: Standardize SLA parameters to **reduce risk perception**.

---

### 🛡️ **Risk-based Access Control (RAC)**
- Grants access even without proper permissions if **risk is acceptable**.
- Better than binary access models.
- **Challenges**:
  - Security uncertainty is **not well-addressed**.
  - Many valid requests **rejected** due to lack of quantified operational need.

---

### 🤖 **Distributed RAC using Fuzzy Inference**
- Uses **local info** to estimate risk and make access decisions.

---

### 🧩 **Inter-Domain Role Mapping (IDRM)**
- **Objective**: Map requested permissions to **minimum local roles**.
- **Challenges**:
  - No polynomial solution.
  - Multiple minimal sets may exist.
  - **Variants**: IDRM-safety, IDRM-availability.

---

### 🔁 **Access Policy Conflicts**
- **Types**:
  - **Cyclic Inheritance Conflict**
  - **Separation of Duty (SoD) Constraint Violation**

#### Detection
- **Inheritance Conflict**:
  - Entry role senior to exit role.
- **SoD Violation**:
  - Conflicting permissions between entry/exit roles.

#### Removal
- **Exactly Matched Role**:
  - Use RBAC hybrid hierarchies: I-hierarchy, A-hierarchy, IA-hierarchy.
- **No Match**:
  - Introduce **virtual roles**.
- **SoD Conflict**: Remove conflicting permission if:
  - Same object.
  - Hierarchical access mode relation.

---

### 🧠 **Summary of Secure SaaS Collaboration**
1. **SelCSP**: Select SaaS provider.
2. **Access Request Recommendation**: Risk-aware, anonymous users.
3. **Permission Mapping**: IDRM.
4. **Conflict Detection & Removal**: Ensure policy consistency across domains.

---
---

## ☁️ **Introduction**
- Rapid growth in cloud services.
- Many providers offer varying **Quality of Service (QoS)**.
- Customers have different **requirements** based on use cases.
- Need for an **Intelligent Broker** to:
  - Recommend the best provider.
  - Protect customer interests.

---

## 🎯 **Motivation**
- Flexible provider selection.
- Evaluate **trustworthiness** of providers.
- Monitor ongoing service quality.
- Avoid **vendor lock-in** (provider dependency).

---

## ✅ **Objectives**
- Select the **best-fit provider** as per customer QoS.
- Calculate **SLA satisfaction** & **trust level** of provider.
- Enable **dynamic migration** if QoS deteriorates.

---

## 🛠️ **Existing Approaches**
- **CloudCmp**: Compares cloud providers by QoS.
- **Fuzzy logic-based** provider selection.
- Frameworks that measure:
  - **User satisfaction** (handling fuzzy requirements).
  - **Trust + Competence** of providers.

---

## 📊 **QoS Parameters (User-defined & Provider-promised)**
- Parameters are customizable.
- **QoS and Trust** are **independent inputs**.

---

## 🏗️ **Marketplace Architecture**
- Users submit requests.
- Broker suggests providers based on suitability (QoS + Trust).
- Requests sent to provider with **highest suitability**.

---

## 🧠 **Provider Selection (Fuzzy Inference Engine)**
- **Inputs**: QoS values, Trust values.
- **Output**: Suitability Score.
- **Membership functions** reflect user preferences.
- Selection = Provider with **maximum suitability score**.

---

## 🧪 **Monitoring Module**
- Collects performance data (provider/third-party).
- Analyzes SLA satisfaction levels over time.

---

## 🔄 **Migration Decider**
- **Fuzzy Inference Engine** checks if current provider underperforms.
- **Input**: Monitored QoS.
- **Output**: SLA satisfaction score.
- If score < threshold ⇒ **Trigger migration**.

---

## 🚚 **Migration Module**
- Chooses **new target provider** (similar fuzzy logic as selection).
- Ensures smooth transition to maintain QoS.

---

## 🧪 **Case Studies (IaaS & SaaS)**
- 10 providers, 500 requests, 1-year simulation.
- Some providers show **performance degradation** (Gaussian pattern).
- Comparison with **crisp (cost-only) broker** shows:
  - Fuzzy broker offers **better performance + adaptability**.

---

## 🔮 **Future Scope**
- Allow **flexible QoS specification**.
- Validate approach with **production workloads**.
- Define **customer service classes**.

---






