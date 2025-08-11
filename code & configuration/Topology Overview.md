# 🏦 Bank Branch Network – Topology Overview

## 📋 Physical & Logical Layout
The network topology represents a **two-floor bank branch** with distinct departments, each mapped to a dedicated VLAN. The design separates traffic by function, improves security, and mirrors a realistic branch layout.

---

## 🏢 Floor Plan & Department Zones

### **Level 1 – Customer Service & Public Area**
This floor is dedicated to day-to-day customer interactions and public access.

- **Regular Customer Zone (VLAN 10)**  
  Area where regular customers are assisted by bank employees.  
  **Devices:**  
  - 6 PCs for bank tellers handling regular customers  
  - Connected to a dedicated switch (`2960-24TT regular`)  
  - All access ports configured for VLAN 10  

- **Customer Waiting Area**  
  A passive zone for clients waiting for service. No active network devices here, but part of the same floor.

---

### **Level 2 – Management & Back-Office Operations**
This floor hosts departments that require restricted access and inter-department collaboration.

- **Bank Manager Zone (VLAN 40)**  
  Office of the branch manager with 1 dedicated PC (`manager-pc`).  
  Connected through the management switch.

- **Tech Support Zone (VLAN 50)**  
  Technical support desk with 1 PC for IT/admin tasks.  
  Manages network troubleshooting and assists all departments.

- **Big Client Zone (VLAN 30)**  
  Two dedicated PCs (`big-client-01` and `big-client-02`) for handling high-value or corporate clients.  
  This zone often interacts with accounting and management.

- **Accounting Zone (VLAN 20)**  
  Four PCs (`acc-01` to `acc-04`) used by the accounting team for financial processing and client account management.

---

## 🔄 Interconnection & Core Network Devices
- **Cisco 2911 Router**  
  Central device providing **Inter-VLAN Routing (ROAS)** and acting as a **DHCP server** for all VLANs.
  
- **Layer 2 Switches (Cisco 2960)**  
  - One dedicated switch per floor/zone cluster  
  - Trunk links between switches and router carry multiple VLANs  
  - Access ports mapped to VLANs based on department location  

---

## 🔒 VLAN Assignment Summary
| VLAN ID | Department              | Floor | Device Count |
|---------|------------------------|-------|--------------|
| 10      | Regular Customers      | 1     | 6 PCs        |
| 20      | Accounting             | 2     | 4 PCs        |
| 30      | Big Customers          | 2     | 2 PCs        |
| 40      | Management             | 2     | 1 PC         |
| 50      | Technical Support      | 2     | 1 PC         |
| 60      | Security Equipment     | —     | Reserved     |

---

## 🛠 Logical Segmentation
- All VLANs are routed via the 2911 router using subinterfaces.
- DHCP pools are defined per VLAN for automatic IP assignment.
- Port Security is applied to all access ports to prevent unauthorized devices.
- ACLs enforce communication rules between departments, based on operational needs.

---

## 📌 Design Goals
- **Segmentation:** Isolate departments to limit broadcast domains and improve security.  
- **Controlled Communication:** Allow only necessary inter-department connections.  
- **Centralized Management:** Router-based DHCP and VLAN routing for simplified control.  
- **Security First:** Port Security and ACLs to enforce strict device and traffic policies.

---
