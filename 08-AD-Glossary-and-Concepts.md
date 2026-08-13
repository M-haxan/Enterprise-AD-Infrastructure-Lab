# Phase 8: Active Directory Glossary & Core Concepts

## Objective
To provide a clear, beginner-friendly reference guide for the technical terms and concepts utilized throughout this enterprise infrastructure deployment. 

## 1. Core Infrastructure
* **Active Directory (AD):** Think of it as a massive, highly secure digital phonebook for a company. It stores information about every user, computer, and printer on the network, and verifies who is allowed to access what.
* **Domain Controller (DC):** The main server that runs Active Directory. It is the "bouncer" of the network—it checks your username and password when you log in and decides if you are allowed inside.
* **DNS (Domain Name System):** The internet's GPS. Computers talk in IP addresses (like `10.1.1.4`), but humans remember names (like `hassan_dev.local`). DNS translates the name into the IP address so machines can communicate.

## 2. Organization & Identity
* **Organizational Unit (OU):** These are logical folders inside Active Directory (e.g., HR, Sales, Development). They are used to group users and computers together so that specific rules (Policies) can be applied to them easily.
* **Delegation of Control:** Giving limited, specific powers to a normal user. For example, allowing an HR manager to reset passwords for their department without making them a full Domain Admin. This ensures security while reducing the IT department's workload.

## 3. Automation & Security
* **Group Policy Object (GPO):** A set of rules pushed from the server to client computers. GPOs automate tasks (like installing software or mapping drives) and enforce security (like blocking USBs or locking desktop wallpapers) without IT having to visit each PC manually.
* **FSRM (File Server Resource Manager):** A server tool used to manage and secure shared data. It allows administrators to set **Quotas** (e.g., maximum 1GB per folder) and **File Screens** (e.g., blocking .mp4 or .mp3 files) to prevent storage waste and secure corporate data.
