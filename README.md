# Azure Gateway Load Balancer Deployment (Portal-Based)

# 🚦 Azure Gateway Load Balancer Lab — Multi-Tier Network Stack

This lab demonstrates the creation and configuration of a **Gateway Load Balancer** using the Azure portal. It walks through deploying a segmented virtual network, configuring a public and internal load balancer, creating custom network security rules, and integrating an NVA (Network Virtual Appliance) into the backend pool.

---

## 🎯 Objectives

- Deploy Azure Virtual Network (`whizVNet`) with subnetting for backend tiers
- Enable Azure Bastion for secure access via browser
- Provision Network Security Group (`whizNSG`) with custom inbound/outbound rules
- Create:
  - Standard Load Balancer (`whizLoadBalancer`)
  - Gateway Load Balancer (`whizLoadBalancer-gw`)
- Configure frontend IPs, backend pools, and TCP health probes
- Deploy a Windows Server NVA (`whizNVA`) and associate it with the gateway backend pool
- Validate the environment and resource protection workflows

---

## 🧰 Core Components

| Resource Type        | Name                    | Notes |
|----------------------|-------------------------|-------|
| VNet                 | `whizVNet`              | IP: 10.1.0.0, Subnet: `myBackendSubnet` |
| Azure Bastion        | `myBastionIP`           | Secure browser-based RDP access |
| NSG                  | `whizNSG`               | Custom rules for inbound/outbound traffic |
| Load Balancer        | `whizLoadBalancer`      | Public-facing |
| Gateway LB           | `whizLoadBalancer-gw`   | Internal, ties to backend pool |
| NVA VM               | `whizNVA`               | Windows Server 2019, used in backend pool |
| Health Probe         | `whizHealthProbe`       | TCP-based, default port 80 |

---

## 🔐 Security Highlights

- NSG rules configured:
  - Allow all inbound traffic (`whizNSGRule-AllowAll-All`)
  - Allow outbound TCP traffic (`whizNSGRule-AllowAll-TCP-Out`)
- Azure Bastion used for secure remote access
- Boot diagnostics disabled to minimize exposure

---

## 🔁 Load Balancer Configuration

- **Frontend IPs** for public access and gateway integration
- **Backend Pools** configured for internal/external port mapping:
  - Internal port: `10800`, ID: `800`
  - External port: `10801`, ID: `801`
- **Load Balancing Rule**:
  - Frontend IP: `whizFrontEnd`
  - Backend Pool: `whizBackendPool`
  - Protocol: `TCP`, Session Persistence: `None`

---

## 🧪 Validation Steps

- VM (`whizNVA`) added to the Gateway LB backend pool
- Proper association verified via portal settings
- Resource group cleanup initiated but halted due to lab constraints

---

## 🧠 Key Concepts Demonstrated

- Gateway Load Balancer architecture in Azure
- NSG configuration for traffic control
- Subnet planning and segmentation
- Public vs internal Load Balancer setup
- Health probe and session configuration
- VM attachment and backend pool integration

---

## 🔖 Recommended Tags

`azure-networking` `gateway-load-balancer` `nsg` `virtual-network` `bastion` `windows-nva` `tcp-probe` `frontend-ip` `backend-pool` `cloud-lab`

---

## 🙌 Author

**Joshua Phillis**  
Cloud engineer focused on secure network architectures, Azure governance practices, and multi-cloud deployment labs.

