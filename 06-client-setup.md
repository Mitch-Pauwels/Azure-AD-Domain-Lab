# Domain-Joining and Client Configuration

## 📝 Description

This section documents how to join a Windows 10 client machine to the Active Directory domain (`lognpacific.local`) and prepare it for domain user login and mapped drive access.

## 🧰 Tools and Utilities Used

- Windows 10 (Client VM)
- Windows Server 2022 (Domain Controller)
- Active Directory Domain Services (AD DS)
- Remote Desktop Protocol (RDP)

## 💻 Environment Used

- Domain Controller: `DC01`
- Client Machine: `Client01`
- Domain: `lognpacific.local`

## 🧩 Steps to Join Domain

1. **Set DNS to Point to DC01**
   - On `Client01`, go to:  
     `Network Settings > Adapter Options > IPv4 Properties`
   - Set **Preferred DNS Server** to the private IP of `DC01`
   - This may temporarily disconnect RDP — use Azure Serial Console or reconfigure once DNS is set

2. **Join the Domain**
   - Right-click `This PC > Properties > Advanced System Settings > Computer Name`
   - Click **Change** and enter:
     - Domain: `lognpacific.local`
   - Use domain admin credentials (e.g., `azureadmin`) when prompted
   - Restart when prompted

3. **Enable Domain User RDP Access**
   - Log in as `azureadmin` on `Client01`
   - Add desired domain users or groups to the **Remote Desktop Users** local group:
     ```powershell
     net localgroup "Remote Desktop Users" "lognpacific\Domain Users" /add
     ```
   - Or manually via:  
     `Computer Management > Local Users and Groups > Groups > Remote Desktop Users`

## 🔐 Best Practice for RDP Access

> 🔒 In production, RDP access should be restricted:
- Only grant access to specific users or groups
- Avoid using `Domain Users` for RDP unless necessary

## 🧪 Testing

- Attempt RDP login as a domain user (e.g., `jdoe`, `ckent`)
- Ensure the correct drive mappings appear (e.g., `EngineeringShare`)
- Confirm user can browse shared folders with correct permissions

## 🖼️ Screenshots

> ![DNS Change](./screenshots/Client-DNS-Settings.png)  
> *Setting the DC IP as DNS on Client01*

> ![Domain Join](./screenshots/Client-Domain-Join.png)  
> *Joining the domain `lognpacific.local`*

> ![RDP Group](./screenshots/Remote-Desktop-Users.png)  
> *Adding domain users to Remote Desktop Users group*

## [Continue to 7. Summary](./07-summary.md)
