# Group Policy Configuration for Drive Mapping

## 📝 Description

This section outlines how to use Group Policy to map the `EngineeringShare` network drive to eligible users based on their group membership. Drive mapping is handled using Item-Level Targeting to ensure that only specific users see the drive.

## 🧰 Tools and Utilities Used

- Group Policy Management Console (GPMC)
- Active Directory Users and Computers
- Windows Server 2022

## 💻 Environment Used

- Domain Controller: `DC01`
- OU: `Engineering`
- Group: `EngineeringShare`
- GPO Name: `Map Network Drive GPO`
- Share Path: `\\DC01\EngineeringShare`

## 📂 GPO Creation and Drive Mapping

1. In **Group Policy Management**, create a new GPO:  
   - Name: `Map Network Drive GPO`
   - Location: **Group Policy Objects** (linked later to specific OU)

2. Edit the GPO:
   - Go to: `User Configuration > Preferences > Windows Settings > Drive Maps`
   - Right-click > New > Mapped Drive
     - Location: `\\DC01\EngineeringShare`
     - Label as: `EngineeringShare`
     - Drive Letter: `E:`
     - Reconnect: Enabled
   - Common Tab:
     - ✅ Run in logged-on user's security context
     - ✅ Item-level targeting
     - Targeting: `Security Group is EngineeringShare`

3. Link the GPO:
   - Right-click on the `Engineering` OU > Link an Existing GPO > select `Map Network Drive GPO`
   - Also link to other OUs (e.g., `Management`) if users outside `Engineering` belong to the `EngineeringShare` group

## 🔒 GPO Security Filtering

- Optional:
  - Remove `Authenticated Users` from **Security Filtering**
  - Add the `EngineeringShare` group instead
  - Under Delegation, make sure:
    - `EngineeringShare` has **Read** and **Apply Group Policy**
    - `Authenticated Users` only have **Read** (not Apply)

## 🧪 Testing

- Log in as a user (e.g., `jdoe`) who is a member of `EngineeringShare`
- Confirm that Drive E: appears with label `EngineeringShare`
- Check access to contents and ensure correct permissions

## 🖼️ Screenshots

> ![Drive Mapping GPO](./screenshots/GPO-DriveMap.png)  
> *GPO Configuration for Drive Mapping*

> ![Item Level Targeting](./screenshots/Item-Level-Targeting.png)  
> *Targeting the EngineeringShare security group*

> ![Linked GPO](./screenshots/Linked-GPO.png)  
> *GPO linked to the Engineering OU*

## [Continue to 6. Client Domain Join & RDP Configuration](./06-client-setup.md)