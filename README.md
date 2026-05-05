# 🖥️ Home-Lab-Server | Windows & Linux Administration
[![Status](https://img.shields.io/badge/Status-Active-success.svg)](#) [![Lab](https://img.shields.io/badge/Focus-Infrastructure_&_Troubleshooting-blue.svg)](#)

## 📌 Project Overview
This repository documents my hands-on experience in building and managing a professional IT environment. It covers the transition from a standard Windows setup to a structured, isolated network where I manage **Active Directory**, solve real-world **Networking conflicts**, and develop independent **Linux Server** skills to serve Windows-based users.

---

## 🛠️ Work History

### 1. Advanced Network Routing & Internet Access (NAT)
* Edge Router Implementation: Transformed Windows Server 2022 into a functional software router using the RRAS (Routing and Remote Access) role.
* NAT Configuration: Successfully implemented Network Address Translation (NAT), allowing Windows 11 clients in an isolated "Internal Network" to access the internet securely via the server’s WAN interface.
* DNS Forwarding: Configured DNS Forwarders (8.8.8.8, 1.1.1.1) on the Domain Controller to resolve external queries (YouTube, Google) for domain-joined clients.
* DHCP Gateway Integration: Updated DHCP Scope Option 003 (Router) to automatically assign the server’s IP as the Default Gateway for all clients, ensuring seamless connectivity.

### 2. Network Isolation & Troubleshooting
* DHCP Mitigation: Identified and resolved a conflict where the physical home router (192.168.0.1) was competing with the Windows Server DHCP. 
* Internal Network Migration: Isolated the lab environment using VirtualBox Internal Networking, establishing the Domain Controller as the sole authority for IP assignments.
* DNS Resolution: Fixed ping and host discovery issues (xami.org) by reconfiguring DHCP Scope Option 006 (DNS Servers) and flushing client-side caches.

### 3. Windows Server & Domain Management
* Active Directory (AD DS): Managed the xami.org domain, including User and Organizational Unit (OU) management.
* Group Policy Objects (GPO): Implemented enterprise-level security:
    * USB/Removable Storage Block: Disabled external drive access for security.
    * UI Restrictions: Disabled CMD and Control Panel for standard users.
    * Automation: Set up automated Network Drive mapping (Z: Drive) via Logon Scripts.
* NTFS Permissions: Resolved application errors by adjusting folder-level access instead of granting unnecessary Admin rights (Principle of Least Privilege).

---

## 🗺️ Roadmap

### Phase 1: Independent Linux Mastery (Current Focus)
* Linux Server Deployment: Setting up a dedicated Linux server (Ubuntu/Rocky) to run independently of the Windows GUI.
* Cross-Platform Interoperability: Learning to use the Linux server as a backend to serve Windows users (Samba File Sharing, SSH Management).

### Phase 2: Data Protection & Damage Control (New)
* Windows Backup: Implementing Windows Server Backup (bare-metal vs. file-level) and managing Shadow Copies (VSS) for quick file recovery.
* Linux Data Integrity: Mastering `rsync` for incremental backups and learning `tar` archiving for configuration snapshots.
* Disaster Recovery: Simulating "Damage Control" scenarios (e.g., deleting a critical system file or breaking a bootloader) and performing recovery without data loss.
* Offsite Storage: Testing the 3-2-1 Backup Rule by syncing local lab data to a secondary virtual disk or cloud storage.

### Phase 3: Infrastructure Automation
* Mass Deployment: Implementing WDS (Windows Deployment Services) for network-based OS installations.
* Hybrid Management: Learning to manage both Windows and Linux environments using command-line tools (PowerShell & Bash).

---

## 🧰 Tech Stack
| Component | Technology |
| :--- | :--- |
| Server OS | Windows Server 2022 |
| Client OS | Windows 11 Pro |
| Networking | RRAS, NAT, DHCP, DNS, ICMP |
| Recovery | Windows Backup, VSS, rsync, tar |
| Virtualization | Oracle VirtualBox (Internal & NAT Modes) |
| Target Skills | Linux CLI, Samba, Active Directory, GPO |

---

**Troubleshooting Log Summary:**
The latest milestone was achieving Network Authority & Routing. By transforming the server into a NAT Gateway, I created a stable environment where clients have internet access while remaining completely isolated from the physical home network. This setup perfectly mirrors a corporate "Edge" configuration.
