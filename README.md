# Enterprise-AD-Infrastructure-Lab
Step-by-step documentation for deploying and managing an Enterprise Active Directory network on Microsoft Azure & Local Hypervisors.

## 🏢 The Scenario
In this lab environment, we simulated a real-world corporate IT infrastructure for a fictional organization. The objective was to design from scratch a secure, centralized, and automated network environment using Windows Server 2022 and Windows 10/11 clients. 

This repository serves as a comprehensive manual covering everything from initial cloud networking to advanced Group Policy deployments, Role-Based Access Control (RBAC), and File Server security.

## 🛠️ Project Architecture
*   **Domain Name:** `hassan_dev.local`
*   **Domain Controller (AD-Server):** Windows Server 2022 (IP: `10.1.1.4`)
*   **Client Machine (Client-PC1):** Windows 10/11 Pro (IP: `172.16.0.4`)
*   **Network Routing:** Configured Virtual Network (VNet) Peering to allow cross-subnet communication between the Server and Client infrastructure.

## 👥 Organizational Structure & Dummy Data
To replicate a true Enterprise Global Address List (GAL), the Active Directory was structured into distinct Organizational Units (OUs) with specific user hierarchies:

## 🚀 Lab Documentation & Phases
This project is divided into detailed, step-by-step markdown files. Click on any phase below to view the implementation details, configurations, and verification screenshots.

*   **[Phase 1: Architecture & Cloud Networking Setup](./01-Architecture-and-Networking.md)**
    *   Resource Provisioning, Subnetting, and VNet Peering.
*   **[Phase 2: Active Directory & DNS Configuration](./02-Active-Directory-Installation.md)**
    *   AD DS Role Installation, Domain Promotion, Forward/Reverse Lookup Zones, and Client Domain Join.
*   **[Phase 3: User Identity & Organizational Structure](./03-User-Identity-Management.md)**
    *   OU Design, User Provisioning, and Corporate Hierarchy mapping.
*   **[Phase 4: Group Policy Management (GPO)](./04-Group-Policy-Management.md)**
    *   Automated Network Drive Mapping for Development and Desktop Standardization (Wallpaper Lock) for Sales.
*   **[Phase 5: Delegation of Control & RBAC](./05-Delegation-of-Control.md)**
    *   Empowering HR with granular permissions to reset Sales department passwords without granting Domain Admin rights.
*   **[Phase 6: Automated Software Deployment](./06-Automated-Software-Deployment.md)**
    *   Deploying standard applications (7-Zip MSI) silently to targeted OUs using GPO.
*   **[Phase 7: Advanced Security Policies & FSRM](./07-Advanced-Security-Policies.md)**
    *   Blocking Removable Storage (USBs) in Finance, Enforcing 1GB Storage Quotas, and File Screening (Blocking .mp4/.mp3) on corporate shares.
*   **[Phase 8: Active Directory Glossary & Core Concepts](./08-AD-Glossary-and-Concepts.md)**
    *   A beginner-friendly guide to the core terminologies used in this lab.

---
*This repository is designed as a Proof of Concept (PoC) for enterprise systems administration and IT automation.*
