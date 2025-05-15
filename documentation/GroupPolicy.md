# 🛡️ Group Policy Implementation

This document outlines how Group Policy Objects (GPOs) were configured and applied in the `lognpacific.local` domain to simulate real-world IT practices.

---

## 🧠 GPO Strategy Overview

| GPO Name                  | Target OU       | Purpose                                      | Features Implemented                         |
|--------------------------|------------------|----------------------------------------------|----------------------------------------------|
| `Map Network Drive GPO`  | Engineering, Management | Maps Engineering shared folder to E: drive | Drive mapping, security filtering            |

---

## 🗂️ Map Network Drive GPO

### 📍 Location:
- Stored in **Group Policy Objects** container
- Linked to:
  - `Engineering` OU
  - `Management` OU

### 🛠️ Configuration:
- **User Configuration → Preferences → Windows Settings → Drive Maps**
  - **Action:** Create
  - **Location:** `\\DC01\EngineeringShare`
  - **Drive Letter:** E:
  - **Label as:** `EngineeringShare`
  - **Reconnect:** Yes

### ⚙️ Common Tab Settings:
- ✅ Run in logged-on user's security context (user policy option)
- ✅ Item-level targeting enabled

### 🎯 Item-Level Targeting:
- **Target Group:** `EngineeringShare` (Security Group located in `Groups` OU)

### 🔐 Security Filtering:
- Removed `Authenticated Users` from Security Filtering
- Added `EngineeringShare` group with **Read** and **Apply group policy** permissions

### 📎 Delegation:
| Principal        | Permissions         |
|------------------|---------------------|
| `EngineeringShare` | Read, Apply GPO     |
| `Authenticated Users` | Read (no apply) |

## 📌 Notes

- All GPOs were kept **at the OU level** to avoid global domain-wide application.
- The use of item-level targeting allows a single GPO to apply to users across different OUs if they belong to the correct group.
- Future enhancements could include:
  - Folder redirection
  - Login scripts
  - Security hardening baselines (e.g., CIS or Microsoft baselines)

---

