# 🏦 Secure Bank Branch Network

A simulated secure network for a small bank branch, featuring **VLAN segmentation**, **Inter-VLAN routing (ROAS)**, **centralized DHCP**, **Port Security**, and **Access Control Lists (ACLs)**. Designed to separate department traffic, enforce security policies, and ensure controlled communication between internal systems.

---

## 📋 Project Overview
This project simulates a **real-world bank branch network**, focusing on:
- Logical segmentation between departments
- Secure and controlled inter-department communication
- Automated IP address distribution
- Network-level access restrictions

It implements **core CCNA concepts** in a realistic, business-oriented scenario, with configurations and policies that reflect actual enterprise security practices.

---

## 🔧 Features

### VLAN Segmentation
Six VLANs separating bank departments and security systems:
- VLAN 10 – Regular Customers  
- VLAN 20 – Accounting Department  
- VLAN 30 – Big Customers  
- VLAN 40 – Management  
- VLAN 50 – Technical Support  
- VLAN 60 – Security Equipment (reserved for cameras & monitoring)

### Router-on-a-Stick (ROAS)
Inter-VLAN routing configured via subinterfaces on a single Cisco 2911 router.

### DHCP Server on Router
Centralized IP management with individual DHCP scopes for each VLAN.

### Port Security
Access port restrictions with sticky MAC addresses to prevent unauthorized device connections.

### Access Control Lists (ACLs)
Traffic filtering rules controlling exactly which VLANs can communicate with each other, based on real-world banking policies.

### Ping Tests & Verification
Connectivity tests between VLANs to confirm routing works according to ACL rules.

---

## 🛠️ Tools & Technologies
- **Cisco Packet Tracer**
- **VLANs**
- **DHCP**
- **ROAS (Router-on-a-Stick)**
- **Port Security**
- **ACLs**
- Cisco Switch & Router CLI Configuration

---

## 📂 Files Included
- `.pkt` file – complete Packet Tracer network topology
- Full configuration scripts for all devices
- Documentation with explanations for each stage

---

## 🔐 Use Case
This type of network is suitable for **small-to-medium financial institutions** or **secure office environments** where:
- Department traffic must be isolated
- Inter-department communication must be strictly controlled
- Network access must be restricted to authorized devices
- IP management needs to be centralized and automated

---
