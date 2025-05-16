# File Share Configuration and Permissions

## 📝 Description

This section covers the creation and configuration of network file shares on the domain controller, including share and NTFS permissions. The file shares are designed for department-specific access, with permissions enforced via security groups.

## 🧰 Tools and Utilities Used

- Windows Server 2022
- Server Manager (File and Storage Services)
- Active Directory Users and Computers
- File Explorer (for access testing)

## 💻 Environment Used

- Domain Controller: `DC01`
- Share Location: `C:\DepartmentShares\EngineeringShare`
- Shared to: `\\DC01\EngineeringShare`
- Security Group: `EngineeringShare`

## 📁 File Share Setup

1. Created folder: `C:\DepartmentShares\EngineeringShare`
2. In **Server Manager > File and Storage Services > Shares**:
   - Created a new SMB share
   - Enabled **Access-Based Enumeration**
   - Disabled **Offline Caching**
   - Removed default "Everyone" from share permissions
   - Added `EngineeringShare` security group with **Full Control** at the share level

## 🔒 NTFS Permissions

- Removed:
  - `Users`
- Added:
  - `EngineeringShare` group with:
    - Modify
    - Read & Execute
    - List Folder Contents
    - Read
    - Write

## 🛠️ Inheritance

- Disabled inheritance on the folder to allow clean permission management
- Removed inherited entries to prevent unintended access

## 👥 Group Membership

- `EngineeringShare` group contains:
  - John Doe
  - Jane Doe
  - Clark Kent

## 🖼️ Screenshots

> ![File Share Wizard](./screenshots/File-Share-Wizard.png)  
> *Creating the file share in Server Manager*

> ![NTFS Permissions](./screenshots/NTFS-Permissions.png)  
> *EngineeringShare NTFS permission configuration*

> ![Access-Based Enumeration](./screenshots/ABE.png)  
> *Access-Based Enumeration settings*
