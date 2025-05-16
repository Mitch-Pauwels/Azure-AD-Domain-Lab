# Active Directory OU and User/Group Structure

## 📝 Description

In this section, we configure the logical structure of our Active Directory (AD) environment. This includes creating Organizational Units (OUs), user accounts, and security groups following a real-world enterprise design. We also relocate default user and group objects into structured OUs to maintain a clean and scalable environment.

## 🧰 Tools and Utilities Used

- Windows Server 2022
- Active Directory Users and Computers (dsa.msc)

## 💻 Environment Used

- Azure-based domain controller (DC01)
- Resource group: `lognpacific-RG`
- Domain: `lognpacific.local`

## 📂 Structure Overview

We created the following OU structure:

> ![OU Structure](./screenshots/OU%20&%20Group%20Structure/OU%20Structure.png)  
> *Organizational Unit layout in Active Directory*


## 👥 Users and Groups

### 👨‍💼 Engineering OU

- **Users**:
  - John Doe (`jdoe`)
  - Jane Doe (`janedoe`)
- **Group**:
  - `EngineeringShare` — includes John Doe, Jane Doe, and Clark Kent

### 👨‍💼 Management OU

- **Users**:
  - Clark Kent (`ckent`)
  - Bruce Wayne (`bwayne`)

### 👩‍💻 IT OU > Administrators

- **User**:
  - AzureAdmin (`azureadmin`) moved from default Users container

## 🔄 Object Cleanup

- Default user and group objects were moved from the default `Users` container into the relevant new OUs.
- Groups were moved under the `Groups` OU.

![OU Structure](./screenshots/OU%20&%20Group%20Structure/Step-05.png)
