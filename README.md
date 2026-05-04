# 🖥️ Home-Lab-Server | Windows & Linux Administration
[![Status](https://img.shields.io/badge/Status-Active-success.svg)](#) [![Lab](https://img.shields.io/badge/Focus-Infrastructure_&_Troubleshooting-blue.svg)](#)

## 📌 Project Overview
This repository documents my hands-on experience in building and managing a professional IT environment. It covers the transition from a standard Windows setup to a structured, isolated network where I manage **Active Directory**, solve real-world **Networking conflicts**, and develop independent **Linux Server** skills to serve Windows-based users.

---

## 🛠️ Work History

### 1. Network Isolation & Troubleshooting
*   **DHCP Mitigation:** Identified a conflict where the physical home router (`192.168.0.1`) was competing with the Windows Server DHCP. 
*   **Internal Network Migration:** Successfully isolated the laboratory environment using **VirtualBox Internal Networking** to ensure the Domain Controller is the sole authority for IP assignments.
*   **DNS Resolution:** Fixed `ping` and host discovery issues (`xami.org`) by reconfiguring DHCP Scope Option **006 (DNS Servers)** and flushing client-side DNS caches.

### 2. Windows Server & Domain Management
*   **Active Directory (AD DS):** Managed the `xami.org` domain, including User and Organizational Unit (OU) management.
*   **Group Policy Objects (GPO):** Implemented enterprise-level security:
    *   **USB/Removable Storage Block:** Disabled external drive access for security.
    *   **UI Restrictions:** Disabled CMD and Control Panel for standard users.
    *   **Automation:** Set up automated Network Drive mapping (Z: Drive) via Logon Scripts.
*   **NTFS Permissions:** Resolved application errors by adjusting folder-level access instead of granting unnecessary Admin rights (Principle of Least Privilege).

---

## 🗺️ Roadmap

### Phase 1: Advanced Network Routing (Next Up)
*   **Gateway Configuration:** Transforming the Windows Server into a router using **RRAS (Routing and Remote Access)** to provide controlled internet access to the isolated Windows 11 clients.

### Phase 2: Independent Linux Mastery
*   **Linux Server Deployment:** Setting up a dedicated Linux server (Ubuntu/Rocky) to run independently of the Windows GUI.
*   **Cross-Platform Interoperability:** Learning to use the Linux server as a backend to serve Windows users (Samba File Sharing, SSH Management).

### Phase 3: Infrastructure Automation
*   **Mass Deployment:** Implementing **WDS (Windows Deployment Services)** for network-based OS installations.
*   **Hybrid Management:** Learning to manage both Windows and Linux environments using command-line tools.

---

## 🧰 Tech Stack
| Component | Technology |
| :--- | :--- |
| **Server OS** | Windows Server 2022 |
| **Client OS** | Windows 11 Pro |
| **Network Tools** | DHCP, DNS, ICMP, IPConfig, NSLookup |
| **Virtualization** | Oracle VirtualBox (Internal Network mode) |
| **Target Skills** | Linux CLI, Samba, Active Directory, GPO |

---

**Troubleshooting Log Summary:**
Today's focus was on **Network Authority**. By isolating the lab from the physical router and forcing DNS resolution through the Domain Controller, I achieved a stable environment where all services (DHCP, GPO, and Name Resolution) work as they would in a real company.
