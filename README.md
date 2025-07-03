# Azure Gateway Load Balancer Deployment (Portal-Based)

## 🧠 Overview
This project demonstrates the creation of a Gateway Load Balancer in Microsoft Azure using the Azure Portal. It includes the setup of a virtual network, network security group, virtual machine, and load balancer with backend pools and health probes.

## ☁️ Technologies Used
- Azure Portal
- Azure Virtual Network (VNet)
- Network Security Groups (NSG)
- Azure Load Balancer (Gateway SKU)
- Azure Bastion
- Windows Server 2019 VM

## 🚀 Implementation Steps

### 1. Virtual Network & Subnet
- Created a VNet named `whizVNet` with address space `10.1.0.0/16`.
- Added a subnet `myBackendSubnet` with range `10.1.0.0/24`.

### 2. Network Security Group
- Created NSG `whizNSG` and added inbound/outbound rules to allow all traffic.
- Associated NSG with the VM NIC.

### 3. Azure Bastion
- Enabled Azure Bastion for secure VM access without public IP exposure.

### 4. Load Balancer (Gateway SKU)
- Created `whizLoadBalancer-gw` with:
  - Internal frontend IP
  - Backend pool `whizBackendPool`
  - Load balancing rule `whizLBRule`
  - Health probe `whizHealthProbe` (TCP:80)

### 5. Virtual Machine
- Deployed `whizNVA` (Windows Server 2019) in `myBackendSubnet`.
- Attached to backend pool and NSG.

### 6. Validation
- Used Great Learning Lab validation tool to confirm successful deployment.

## 📸 Screenshots
Include screenshots of:
- VNet and subnet configuration
- NSG rule setup
- Load balancer frontend/backend config
- VM deployment
- Validation success

## 🧠 Lessons Learned
- Gained experience configuring Azure networking and load balancing.
- Understood the role of Gateway Load Balancer in traffic redirection.
- Practiced secure access using Azure Bastion.

## 🧹 Resource Cleanup
All resources were deleted after validation to avoid unnecessary charges.

---

## 📌 Notes
- This lab was completed as part of the Great Learning Azure certification program.
- All credentials and sensitive data were rotated or removed post-lab.
