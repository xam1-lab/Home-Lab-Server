# 🖥️ Home-Lab-Server | Windows & Linux Administration
[![Status](https://img.shields.io/badge/Status-Active-success.svg)](#) [![Lab](https://img.shields.io/badge/Focus-Infrastructure_&_Troubleshooting-blue.svg)](#)

## 📌 Project Overview
This repository documents my hands-on experience in building and managing a professional IT environment. It covers the transition from a standard Windows setup to a structured, isolated network where I manage **Active Directory**, solve real-world **Networking conflicts**, and develop independent **Linux Server** skills to serve Windows-based users.

---

## 🛠️ Work History & Completed Milestones

### 1. Network Isolation & Authority
* **DHCP Mitigation:** Identified and resolved a conflict where the physical home router was competing with the Windows Server DHCP service.
* **Internal Network Migration:** Isolated the lab environment using **VirtualBox Internal Networking** (it-lab) to ensure the Domain Controller is the sole authority for IP assignments.
* **DNS Resolution:** Fixed `ping` and host discovery issues for `xami.org` by reconfiguring DHCP Scope Option **006 (DNS Servers)**.

### 2. Gateway, Routing & Internet Access
* **RRAS Implementation:** Configured **Routing and Remote Access Services (RRAS)** on the Windows Server to act as a software router.
* **NAT (Network Address Translation):** Set up a NAT interface to bridge the isolated internal network with the physical network adapter. This provided controlled internet access to the Windows 11 clients while maintaining their isolation from the physical home network.
* **Dual-Homing:** Managed a dual-NIC setup on the server (NAT adapter for internet and Internal adapter for the lab).

### 3. Windows Server & Domain Management (xami.org)
* **Active Directory (AD DS):** Implemented a domain structure with hierarchical Organizational Units (OUs).
* **Group Policy Objects (GPO):**
    * **Security:** Disabled USB storage access and restricted CMD/Control Panel for standard users.
    * **Automation:** Configured automated network drive mapping (Z: Drive) via Logon Scripts.
* **NTFS Permissions:** Applied the **Principle of Least Privilege** by fine-tuning folder-level permissions instead of granting unnecessary admin rights.

### 4. Data Protection & Disaster Recovery
* **Volume Shadow Copy Service (VSS):** Configured "Self-Service" file recovery, allowing users to restore previous versions of documents (Shadow Copies) without admin help.
* **Windows Server Backup (WSB):**
    * Implemented a **Bare Metal Recovery** plan using a dedicated virtual hard drive.
    * Mastered **File Locking Management** via *Computer Management* to resolve "file in use" errors during restoration.

---

## 🗺️ Roadmap

### Phase 1: Independent Linux Mastery (Next Up)
* **Ubuntu Desktop Deployment:** Installing a Linux server with a GUI as a standalone unit within the network.
* **Cross-Platform Interoperability:** Configuring **Samba (SMB)** services to enable seamless file sharing between Linux and Windows users within the `xami.org` domain.

### Phase 2: Infrastructure Automation & Deployment
* **Mass Deployment:** Implementing **WDS (Windows Deployment Services)** for network-based automated OS installations.
* **Hybrid Management:** Mastering mixed-environment administration using PowerShell (Windows) and Bash (Linux) side-by-side.

---

## 🧰 Tech Stack & Tools
| Component | Technology |
| :--- | :--- |
| **Server OS** | Windows Server 2022 |
| **Client OS** | Windows 11 Pro, Ubuntu Desktop 24.04 LTS |
| **Network Services** | DHCP, DNS, RRAS (NAT), VSS, SMB/Samba |
| **Backup** | Windows Server Backup (WSB), Shadow Copies |
| **Virtualization** | Oracle VirtualBox (Internal Network mode) |
| **Tools** | PowerShell, CMD, Netplan, Nano, WBAdmin |

---

## 📝 Troubleshooting Log Summary
* **Routing Success:** Achieving internet access within an isolated subnet was a success. By correctly configuring RRAS and NAT, I successfully simulated a real-world enterprise gateway.
* **Data Integrity:** The addition of VSS and WSB ensures the lab is resilient against data loss. The environment is now robust and ready for the integration of the Linux ecosystem.
