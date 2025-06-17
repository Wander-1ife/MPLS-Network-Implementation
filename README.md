# MPLS Network Implementation

## 📘 Project Title
**Implementation of Multiprotocol Label Switching (MPLS)**

## 📝 Abstract

This project demonstrates the practical differences between traditional IP routing and Multiprotocol Label Switching (MPLS) using GNS3. Through a simulated network, we implemented MPLS with key components like VRFs, OSPF, and BGP to showcase MPLS's advantages in traffic engineering, efficient forwarding, and improved scalability.

---

## 📂 Table of Contents
1. [Introduction](#1-introduction)  
2. [Network Topology](#2-network-topology)  
3. [Policy Implementation](#3-policy-implementation)  
4. [MPLS Configuration](#4-mpls-configuration)  
5. [Verification and Testing](#5-verification-and-testing)  
6. [Conclusion](#6-conclusion)  
7. [References](#7-references)

---

## 1. Introduction

Multiprotocol Label Switching (MPLS) is a network protocol designed to increase the performance and efficiency of packet-forwarding by using labels rather than traditional IP lookups. This project focuses on demonstrating how MPLS, combined with protocols like OSPF and BGP, can enhance traffic engineering and network scalability.

---

## 2. Network Topology

The network topology consists of:

- **Provider (P) Routers**
- **Provider Edge (PE) Routers**
- **Customer Edge (CE) Routers**

These devices are interconnected to simulate a real-world MPLS environment. Each PE router connects to distinct customer banks (Bank A, Bank B, Bank C) to simulate inter-organizational traffic flow.

---

## 3. Policy Implementation

Custom communication policies were defined to simulate real-world access control between clients:

- **Bank B cannot communicate with Bank C**
- Other communications were routed using MPLS labels and policies defined via VRFs

---

## 4. MPLS Configuration

### 4.1 OSPF Setup

OSPF was used for establishing internal connectivity between P and PE routers. Loopback addresses on PE routers represent unique customer sites for routing purposes.

### 4.2 MPLS Neighbor Discovery

Label-Switched Paths (LSPs) were validated through discovery of MPLS neighbors to ensure successful MPLS forwarding.

### 4.3 Virtual Routing and Forwarding (VRF)

Each customer network was isolated using VRFs configured on the PE routers. Interfaces were assigned to respective VRFs to maintain traffic separation.

---

## 5. Verification and Testing

### 5.1 Static Routes

Static routes were configured on CE routers to guide traffic through MPLS paths.

### 5.2 BGP Redistribution

BGP was implemented on PE routers, with route redistribution from static routes, to ensure dynamic propagation of customer routes.

### 5.3 Ping Tests

Connectivity was verified using ICMP ping tests:

- **Bank A to All**: Successful  
- **Bank C to Bank C**: Successful  
- **Bank B to Bank A**: Successful  
- **Bank B to Bank C**: Blocked as per policy

---

## 6. Conclusion

The MPLS network implementation successfully demonstrated significant benefits over traditional IP routing. Using OSPF for backbone connectivity, VRFs for customer isolation, and BGP for route distribution, the project illustrated how MPLS improves network efficiency and flexibility in managing complex routing policies.

---

## 7. References

- **RFC 3031** - MPLS Architecture  
- Figures and configuration screenshots from GNS3 simulations in the report
