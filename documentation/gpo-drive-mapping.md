# Group Policy Objects (GPO) for Drive Mapping

### Step 1: Create GPO "Map Network Drive GPO"

- Created in `Group Policy Objects` container (not linked globally)
- Edited User Configuration > Preferences > Windows Settings > Drive Maps
- New Mapped Drive:
  - Location: `\\DC01\EngineeringShare`
  - Drive letter: `E:`
  - Label: `EngineeringShare`
  - Reconnect: Yes
- Common tab: "Run in logged-on user's security context" enabled
- Item-level targeting: Targeted `EngineeringShare` security group

![Screenshot placeholder: GPO drive mapping configuration]

---

### Step 2: Link GPO to Engineering OU

- Linked GPO to `Engineering` OU so only users in this OU receive the policy

![Screenshot placeholder: Linking GPO to OU]

---

### Step 3: Verify Group Policy Application on Client

- Logged in as user `jdoe` on `Client01`
- Drive `E:` mapped automatically to `EngineeringShare` folder

![Screenshot placeholder: Client drive mapping confirmation]

---
