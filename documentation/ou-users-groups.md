# 🗂️ Active Directory Organizational Unit (OU) Structure

This document explains the purpose and design logic behind the Organizational Unit (OU) structure created in the `lognpacific.local` domain.

## 🌐 Domain Overview

- **Domain Name:** `lognpacific.local`
- **Purpose:** Simulate a real-world enterprise structure for user, group, and policy management.

## 🧱 Top-Level OUs

| OU Name      | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| **Groups**   | Contains all security groups, centralized for easier management.            |
| **IT**       | Contains IT department users and sub-OUs. Used for GPO scoping and security.|
| **Engineering** | Departmental OU for engineers. Includes users and the EngineeringShare group. |
| **Management**  | Contains higher-level users (e.g., executives, leads). Has specific GPOs applied. |

---

## 🧱 Nested OUs and Entities

### 🔹 `Groups`

> **Purpose:** All domain security groups are stored here to avoid clutter in the default "Users" container and allow clean delegation and management.

- `EngineeringShare` – Used to grant access to the shared folder for engineers.
- `IT_Staff` – Used for IT-specific privileges and RDP access.
- `ManagementShare` (optional) – Could be used for any future management-specific access.

---

### 🔹 `IT`

> **Purpose:** Holds IT staff and administrators. This OU is used to apply policies specific to IT personnel.

#### Sub-OUs:
- **Administrators**
  - Contains the user `azureadmin`
  - Can be used to apply stricter policies or elevated permissions.

---

### 🔹 `Engineering`

> **Purpose:** Contains engineers and their departmental group used for drive mapping and folder access.

#### Users:
- `jdoe` (John Doe)
- `janedoe` (Jane Doe)

#### Groups:
- `EngineeringShare` (group located in `Groups` OU, but members are from here)

---

### 🔹 `Management`

> **Purpose:** Hosts upper-level staff such as leads and executives. Policies can be scoped separately from regular users.

#### Users:
- `ckent` (Clark Kent)
- `bwayne` (Bruce Wayne)

---

## ✅ Design Principles Followed

- **Delegation of Control:** Easier to delegate admin rights by scoping to OUs.
- **Policy Targeting:** OUs allow Group Policy Objects (GPOs) to be targeted by department.
- **Clean Separation:** Users, computers, and groups are separated logically to match enterprise best practices.

---

## 🛠️ Future Recommendations

- Create a `Computers` OU and move all domain-joined client machines there.
- Create `Service Accounts` or `Non-Human Accounts` OU for automation and integrations.
- Apply GPOs only to OUs where needed to follow the principle of least privilege.

