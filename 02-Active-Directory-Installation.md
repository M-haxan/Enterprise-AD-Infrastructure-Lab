# Phase 2: Active Directory & DNS Configuration

## Objective
To install Active Directory Domain Services (AD DS), promote the server to a Domain Controller (DC), configure DNS zones, and successfully join a client machine to the newly created domain (`hassan_dev.local`).

## 1. Network Preparation (Cloud vs. Local)
Before installing AD DS, proper network routing is required so the Client can locate the Server.

* **For Cloud (Azure) Deployments:** 
  Ensure VNet Peering is established. Update the Client VNet's "Custom DNS" setting in the Azure Portal to point to the Server's Private IP (e.g., `10.1.1.4`).
* **For Local (VirtualBox / Hyper-V) Deployments:**
  Ensure both Server and Client VMs are on the same Internal Network or NAT Network. On the Client PC, open Network Connections (`ncpa.cpl`), go to IPv4 properties, and manually set the Preferred DNS server to the AD Server's IP.

## 2. Installing AD DS Role
1. Opened **Server Manager** on the Windows Server.
2. Clicked on **Add roles and features**.
3. Proceeded with Role-based installation and selected **Active Directory Domain Services** and **DNS Server**.
4. Completed the installation wizard.

> 📸 **Screenshot Placeholder:** *(Add an image showing Server Manager with AD DS role installed)*
> `![AD DS Role Installed](Screenshots/adds_installed.png)`

## 3. Promoting to Domain Controller
1. Clicked the notification flag in Server Manager and selected **"Promote this server to a domain controller"**.
2. Selected **"Add a new forest"** and specified the Root domain name as `hassan_dev.local`.
3. Set the Directory Services Restore Mode (DSRM) password.
4. Left the NetBIOS domain name as default (`HASSAN_DEV`) and completed the promotion process, which automatically restarted the server.

> 📸 **Screenshot Placeholder:** *(Add an image of the Deployment Configuration screen showing the domain name)*
> `![Domain Promotion](Screenshots/domain_promotion.png)`

## 4. DNS Configuration (Forward & Reverse Lookup Zones)
To ensure proper name resolution across the network:
1. Opened **DNS Manager** from Server Manager tools.
2. Verified the **Forward Lookup Zone** (`hassan_dev.local`) automatically generated Host (A) records for the server.
3. Manually created **Reverse Lookup Zones** for both the Server subnet (`10.1.1.x`) and Client subnet (`172.16.0.x`).
4. Updated the Pointer (PTR) records for both machines.

> 📸 **Screenshot Placeholder:** *(Add the screenshot you saved earlier showing the DNS Forward/Reverse zones)*
> `![DNS Zones Configuration](Screenshots/dns_zones.png)`

## 5. Joining the Client PC to the Domain
1. Logged into the Client PC.
2. Opened System Properties (`sysdm.cpl`).
3. Clicked **Change** to rename the computer (e.g., `Client-PC1`) and selected **Domain**.
4. Entered `hassan_dev.local` and authenticated with the Domain Admin credentials.
5. Restarted the Client PC to apply changes.

> 📸 **Screenshot Placeholder:** *(Add an image showing the "Welcome to the hassan_dev.local domain" success message)*
> `![Domain Join Success](Screenshots/domain_join.png)`

## 6. Verification
Ran `nslookup` on both Server and Client Command Prompts to verify that both Forward (Name to IP) and Reverse (IP to Name) DNS resolutions were functioning correctly.
