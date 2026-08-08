# Phase 1: Architecture & Cloud Networking Setup

## Objective
To provision the base infrastructure on Microsoft Azure, including Virtual Machines and Network Routing, required for an Enterprise Active Directory environment.

## 1. Resource Provisioning
We started by creating an Azure Resource Group to contain all our network components.
* **Server VM:** Windows Server 2022 (Assigned Private IP: 10.1.1.4)
* **Client VM:** Windows 10/11 Pro (Assigned Private IP: 172.16.0.4)
* **Storage:** Standard SSDs attached to both VMs for OS and data.

## 2. Virtual Network (VNet) Configuration
Since the Server and Client are on different subnets, they cannot communicate by default. 
* Created VNet-Server for the `10.x.x.x` network.
* Created VNet-Client for the `172.16.x.x` network.

## 3. VNet Peering
To enable seamless communication between the two distinct networks:
* Configured VNet Peering in the Azure Portal.
* Verified connectivity by successfully pinging the Server's private IP (`10.1.1.4`) from the Client machine.
* Changed the Client VM's Custom DNS setting in Azure to point to `10.1.1.4`.
