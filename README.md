# 🏢 Active Directory Lab in Azure

This project simulates a real-world **enterprise IT environment** in **Microsoft Azure**, demonstrating my ability to deploy, configure, and manage a production-style **Active Directory Domain Services (AD DS)** infrastructure from scratch. The lab includes user account management, secure file sharing, Group Policy Objects (GPOs), and domain-joined clients.

---

### 🎯 Objective

Build a cloud-based IT infrastructure that mirrors a corporate environment, featuring:

- Domain Controller (Windows Server 2022) and Client (Windows 10)
- Fully functional **Active Directory** with OUs, users, and security groups
- **Group Policy** for drive mapping, RDP access, and targeted configuration
- Static IP addressing, custom DNS, and VM provisioning in Azure
- File shares with **NTFS permissions** and **access-based enumeration**

---

### 💼 Why It Matters

In enterprise IT, Active Directory and Group Policy are foundational for managing users, devices, and security. This lab simulates the responsibilities of an **IT Support Specialist** or **System Administrator**, showing my readiness to support real-world infrastructure and deliver secure, scalable IT services.

---

### 🧰 Technologies Used

- 🟦 **Microsoft Azure** (IaaS)
- 🖥 **Windows Server 2022** (Domain Controller)
- 💻 **Windows 10 Enterprise** (Client)
- 📁 **Active Directory**, **Group Policy**, **NTFS File Sharing**
- 🔐 **Active Directory Certificate Services (AD CS)**
- 🌐 **Azure Resource Groups**, **Virtual Network**, **Custom DNS**, **Static IPs**

---

### 📂 Project Structure

- [1. Azure Setup (Resource Group, VNet, VMs)](./1-azure-setup.md)
- [2. Domain Controller Configuration (AD DS + AD CS)](./2-dc01-setup.md)
- [3. Organizational Units, Users & Groups](./3-ou-users-groups.md)
- [4. File Shares & NTFS Permissions](./4-file-shares.md)
- [5. Group Policy Drive Mapping](./5-gpo-drive-mapping.md)
- [6. Client Domain Join & RDP Configuration](./6-client-join-domain.md)
- [7. Validation & Functional Testing](./7-validation.md)
