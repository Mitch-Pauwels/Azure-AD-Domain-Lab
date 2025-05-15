# Project Setup in Azure

### Step 1: Resource Group & Virtual Network

- Created a Resource Group `RG-AD-Lab`
- Created a Virtual Network `VNet-ADLab` with subnet `Subnet-ADLab`

![Resource Group and VNet](./screenshots/rg-vnet.png)

---

### Step 2: Deploy Domain Controller (DC01) VM

- VM Name: `DC01`
- OS: Windows Server 2022 Datacenter
- Static Private IP assigned
- Installed Active Directory Domain Services role and promoted to domain controller

![Screenshot placeholder: DC01 VM settings and static IP]

---

### Step 3: Deploy Client VM (Client01)

- VM Name: `Client01`
- OS: Windows 10 Enterprise
- Configured to use DC01’s IP as DNS server

![Screenshot placeholder: Client01 VM and DNS settings]

---
