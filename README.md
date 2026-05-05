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

### 2. Gateway, Routing & Internet Access (Completed)
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

## 🛡️ Troubleshooting & Technical Log

This log documents critical technical challenges encountered during the infrastructure build and the systematic logic used to resolve them.

### 1. Network Authority & DHCP Conflicts
* **The Challenge:** The laboratory environment was receiving IP addresses from the physical home router (192.168.0.1), creating a conflict with the Windows Server DHCP role.
* **The Resolution:** Migrated all VirtualBox network adapters to **Internal Networking** mode. This successfully isolated the lab, establishing the Windows Server as the sole authority for IP assignments.

### 2. DNS Resolution & Domain Connectivity
* **The Challenge:** Windows 11 clients were unable to join the `xami.org` domain or resolve the host by name, despite having valid IP configurations.
* **The Resolution:** Identified that **DHCP Scope Option 006 (DNS Servers)** was not pointing to the Domain Controller's static IP. Corrected the scope and executed a DNS flush on the clients to restore resolution.

### 3. Gateway & Internet Routing (NAT/RRAS)
* **The Challenge:** Clients in the isolated internal network required internet access for updates without direct exposure to the physical home network.
* **The Resolution:** Implemented **Routing and Remote Access Services (RRAS)** with **NAT** on a dual-homed Windows Server. This bridged internal traffic to the external network, effectively acting as an enterprise-grade software router.

### 4. Volume Shadow Copy Service (VSS) Implementation
* **The Challenge:** Accidental file deletion or overwrites led to high administrative overhead for manual restores.
* **The Resolution:** Configured **Volume Shadow Copies** on server storage volumes. This enabled "Self-Service" recovery, allowing users to restore previous versions of documents independently via the "Previous Versions" tab.

### 5. The "File in Use" Restoration Error
* **The Challenge:** During VSS testing, the system blocked file restoration because the file was being accessed by a remote network session.
* **The Resolution:** Utilized the **Shared Folders** console (`fsmgmt.msc`) to identify and force-close open sessions, ensuring backup integrity during the restoration process.

### 6. Bare Metal Recovery & Backup Strategy
* **The Challenge:** Lack of a full-system recovery plan left the `xami.org` infrastructure vulnerable to total system failure.
* **The Resolution:** Configured **Windows Server Backup (WSB)** on a dedicated virtual hard drive. Successfully implemented a **Full Server (System State)** backup plan, ensuring the environment is prepared for **Bare Metal Recovery**.

### 7. NTFS Permission Layers & "Least Privilege"
* **The Challenge:** Users added to the `IT_Sektor_FullAccess` group were unable to access folders, and some applications failed due to restricted rights.
* **The Resolution:** I adjusted both **NTFS and Share permissions** rather than granting unnecessary Admin rights. Identified that users must **Sign-out and Sign-in** to refresh their security tokens after group membership changes.

---

**Current Project Status:** The Windows infrastructure is stable, routed, and backed up. I am now moving into **Phase 2**, focusing on **Linux Server deployment** and cross-platform interoperability.
