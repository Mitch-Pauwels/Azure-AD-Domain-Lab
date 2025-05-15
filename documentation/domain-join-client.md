# Domain Join and Client Configuration

### Step 1: Configure Client DNS

- On `Client01` VM, set primary DNS server to DC01 private IP address

![Screenshot placeholder: Client DNS IP settings]

---

### Step 2: Join Domain

- On `Client01`:
  - System Properties > Change settings > Domain > enter `lognpacific.local`
  - Provide credentials of domain admin (e.g. `azureadmin`)
  - Restart client VM

![Screenshot placeholder: Domain join wizard]

---

### Step 3: Log in as Domain User

- Log in to `Client01` using domain user credentials (e.g., `lognpacific\jdoe`)

![Screenshot placeholder: Domain user login]

---

### Step 4: Enable Remote Desktop Access for Domain Users

- Add domain user or group to `Remote Desktop Users` group on the client VM to allow RDP access

![Screenshot placeholder: Remote Desktop Users group]

---
