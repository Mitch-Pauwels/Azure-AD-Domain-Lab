# Active Directory Domain Services Configuration

### Step 1: Install AD DS Role

- Open Server Manager on DC01
- Add Roles and Features > Active Directory Domain Services

![Screenshot placeholder: Installing AD DS Role]

---

### Step 2: Promote Server to Domain Controller

- Promote to a new forest
- Domain Name: `lognpacific.local`

![Screenshot placeholder: Domain Controller promotion wizard]

---

### Step 3: Install Active Directory Certificate Services (Optional but recommended)

- Add AD CS role for certificate management within the domain

![Screenshot placeholder: Installing AD CS role]

---

### Step 4: Configure DNS Server

- DNS zone `lognpacific.local` created automatically
- Verified presence of `_msdcs.lognpacific.local` zone

![Screenshot placeholder: DNS Manager zones]

---
