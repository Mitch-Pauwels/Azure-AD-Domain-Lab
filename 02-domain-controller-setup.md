## 📘 Description
This section describes promoting `DC01` to a domain controller and configuring the foundational Active Directory Domain Services environment.

---

## 🧰 Tools and Technologies Used
- **OS:** Windows Server 2022
- **Role:** Active Directory Domain Services (AD DS)
- **Utilities:** Server Manager, PowerShell

---

## 🌐 Environment Overview
- **Server:** `DC01`
- **Domain:** `lognpacific.local`

---

## 🚀 Implementation Steps
### 1. Install AD DS Role on DC01
- Open Server Manager > Add Roles and Features > Select AD DS

### 2. Promote DC01 to Domain Controller
- After installation, click "Promote this server to a domain controller"
- Select "Add a new forest": `lognpacific.local`
- Set DSRM password
- Accept defaults, review, and complete installation

### 3. Set Static IP and DNS
- Set private IP of DC01 to static (from Azure networking settings)
- Set DNS to localhost (`127.0.0.1`) or its static IP (e.g., `10.0.0.4`)

---

## 📸 Screenshots
- `![ADDS Installation](./screenshots/ADDS_Installed.png)`
- `![Promote DC](./screenshots/PromoteDC.png)`
- `![Domain Created](./screenshots/DomainSetupComplete.png)`

---

## 📌 Notes & Considerations
- Reboot is required after domain promotion.
- Server Manager showing AD DS in "Roles and Server Groups" confirms success.
- Use `dsa.msc` to launch Active Directory Users and Computers.