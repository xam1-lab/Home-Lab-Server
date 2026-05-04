# Home-Lab-Win-Server
My personal project on learning System Administration using Windows Server 2022 and Linux

--------------

Project Overview

This repository documents the implementation of a professional IT infrastructure laboratory. The goal of this project is to simulate a real-world corporate environment, focusing on Active Directory Domain Services (AD DS), Network Administration, and Security Governance using Windows Server 2022 and Windows 11 Pro.

--------------------------

Technical Implementations

1. Identity & Access Management (AD DS):
   Domain Configuration: Successfully deployed a Domain Controller for the xami.org forest.

Organizational Unit: Designed a logical structure to manage Users, Computers, and Groups, mirroring a standard corporate department layout.

RBAC (Role-Based Access Control): Implemented the principle of least privilege by separating standard user tasks from administrative duties.

--------------------------

2. Network Services (DHCP & DNS):

Authoritative DNS: Configured local DNS for seamless name resolution across the domain.

DHCP Scope Management: Established automated IP addressing with specific exclusion ranges and reservations.

Advanced Troubleshooting:

Identified and mitigated a DHCP conflict where the physical router (192.168.0.1) interfered with the lab environment.
Resolved the conflict by migrating the lab to an Isolated Internal Network within the virtualization layer (Oracle VirtualBox).

--------------------------

3. Group Policy & Security Governance (GPO):
   
Implemented several Group Policy Objects (GPOs) to enforce security and automation

Data Loss Prevention (DLP): Restricted access to Removable Storage Devices (USB) to prevent unauthorized data exfiltration and malware entry.

System Hardening: Disabled access to the Control Panel and Command Prompt (CMD) for non-admin users to ensure environment stability.

Automation: Configured Logon Scripts for automatic mapping of network drives (Z: Drive) for departmental file sharing.

--------------------------

4. File System Security
NTFS Permissions: Managed complex folder permissions (Read, Modify, Full Control) based on Active Directory security groups.
Legacy App Support: Resolved application-level permission issues by modifying specific folder ACLs (Access Control Lists) instead of granting unnecessary local administrative rights to users.

--------------------------

Tools & Technologies Used

Hypervisor: Oracle VirtualBox (Networking: Internal Network & NAT)

Server OS: Windows Server 2022

Client OS: Windows 11 Pro

Networking: IPv4, DHCP, DNS, ICMP (Firewall management)

--------------------------

Key Troubleshooting Skills Demonstrated

Network Diagnostics: Proficient use of ipconfig /all, nslookup, ping, and gpupdate /force.

System Analysis: Identifying why clients fail to join the domain or receive IP addresses, and implementing structural fixes (e.g., DNS Bindings, Firewall rules)

-------------------------

Project Roadmap & Future Goals:

This laboratory is a dynamic project. I am continuously scaling the infrastructure to transition from a basic setup to a complex, hybrid enterprise environment.

--------------------------

Phase 1: Core Windows Infrastructure (Completed)

Domain Services: Deploy Domain Controller (xami.org) and join Windows 11 workstations.

Networking: Configure authoritative DHCP and DNS services with custom Scope Options.

Security Baseline: Implement GPOs for USB blocking, Control Panel restriction, and automated Network Drive mapping.

--------------------------

Phase 2: Advanced Deployment & Management (In Progress)

Automated Deployment: Set up WDS (Windows Deployment Services) to simulate PXE-boot network installations for mass-rollouts.

Routing & Gateway: Configure RRAS (Routing and Remote Access) to transform the server into a gateway, providing firewalled internet access to the isolated lab.

Update Management: Deploy WSUS to centrally manage and approve security patches for all client machines.

--------------------------

Phase 3: Linux Integration & Cross-Platform Interoperability (Upcoming)

Linux Server Integration: Deploy Ubuntu or Rocky Linux servers to handle specific network workloads (Web/Database).

Active Directory for Linux: Implement SSSD/LDAP to allow Linux servers to authenticate users using Windows Domain credentials.

Cross-Platform File Sharing: Configure Samba to enable seamless file exchange between Linux servers and Windows clients using NTFS-level permissions.

--------------------------

Phase 4: Hybrid Cloud & DevOps Automation (Future)

Cloud Identity: Integrate the local lab with Microsoft Entra ID (formerly Azure AD) for a hybrid identity experience.

Infrastructure as Code (IaC): Use PowerShell and Ansible to automate user onboarding and server configuration across both Windows and Linux.

Centralized Monitoring: Deploy a Linux-based monitoring stack (Zabbix/Grafana) to track hardware health and network uptime for the entire lab.
