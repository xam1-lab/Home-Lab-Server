# 🖥️ Home-Lab-Server | Cross-Platform Enterprise Simulation
[![Status](https://img.shields.io/badge/Status-Active-success.svg)](#) [![OS](https://img.shields.io/badge/OS-Windows_/_Linux-blue.svg)](#) [![Environment](https://img.shields.io/badge/Environment-Isolated_Lab-orange.svg)](#)

## 📌 Project Overview
This repository documents my **Home-Lab-Server**, a hybrid enterprise environment designed to master System Administration. This project simulates a corporate infrastructure where **Windows Server 2022** and **Linux** coexist, focusing on Identity Management, Network Governance, and Cross-Platform Interoperability.

---

## 🚀 Technical Core (Windows Stack)

### 🔑 Identity & Access Management (AD DS)
*   **Domain Controller:** Deployed the `xami.org` forest root.
*   **Active Directory Design:** Structured Organizational Units (OUs) to manage Users, Computers, and Security Groups.
*   **RBAC Policy:** Implemented Role-Based Access Control to enforce the **Principle of Least Privilege (PoLP)**.

### 🌐 Network Infrastructure
*   **Authoritative DHCP/DNS:** Managed automated IP assignment and local name resolution.
*   **Conflict Resolution:** Identified and mitigated **Rogue DHCP** issues by implementing isolated **Internal Networking** in VirtualBox, ensuring the DC remains the primary network authority.
*   **File Services:** Configured automated Network Drive mapping (Z: Drive) via Logon Scripts.

### 🛡️ Security & Group Policy (GPO)
*   **DLP (Data Loss Prevention):** Enforced a global block on Removable Storage (USB) to prevent unauthorized data transfer.
*   **System Hardening:** Restricted access to **CMD**, **PowerShell**, and **Control Panel** for standard user accounts.
*   **NTFS Security:** Fine-tuned folder-level permissions (ACLs) to support legacy applications without granting local admin rights.

---

## 🗺️ Roadmap

### Phase 1: Windows Foundations (Completed ✅)
*   AD DS Deployment & Domain Join (Windows 11).
*   GPO Security Hardening & Network Drive Mapping.
*   DHCP/DNS Troubleshooting in isolated environments.

### Phase 2: Advanced Deployment & Routing (In Progress 🚧)
*   **WDS & MDT:** Implementing PXE-boot network installations for automated OS deployment.
*   **RRAS Gateway:** Configuring the server as a router to provide firewalled internet access to the lab.
*   **WSUS:** Centralized patch management for enterprise-wide updates.

### Phase 3: Linux Integration & Interoperability (Upcoming 🐧)
*   **Linux Server Deployment:** Integrating **Ubuntu/Rocky Linux** for specialized workloads.
*   **AD-Linux Join:** Using **SSSD/LDAP** to allow Linux servers to recognize `xami.org` domain credentials.
*   **Cross-Platform Shares:** Using **Samba** to bridge Windows and Linux file systems with consistent permissions.

### Phase 4: DevOps & Hybrid Cloud (Future 🚀)
*   **Microsoft Entra ID:** Syncing local identities with **Azure AD**.
*   **Ansible Automation:** Using Linux-based automation to manage both Windows and Linux nodes.
*   **Monitoring Stack:** Deploying **Zabbix/Grafana** for real-time health and uptime tracking.

---

## 🛠️ Tech Stack
| Component | Technology |
| :--- | :--- |
| **Hypervisor** | Oracle VirtualBox |
| **Server OS** | Windows Server 2022 |
| **Client OS** | Windows 11 Pro |
| **Future OS** | Ubuntu Server / Rocky Linux |
| **Tools** | AD DS, GPO, DNS, DHCP, Samba, SSH |

---

> **Note:** This lab is a reflection of my journey toward becoming a Cross-Platform Systems Administrator. Every issue resolved here is documented to build a deep understanding of Enterprise IT.
