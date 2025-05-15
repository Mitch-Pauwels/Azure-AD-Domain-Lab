# File Shares Configuration

### Step 1: Create Shared Folder on DC01

- Using Server Manager > File and Storage Services > Shares
- Created share `EngineeringShare`
- Share permissions: Removed `Everyone`, added `EngineeringShare` group with full access
- Enabled access-based enumeration and disabled caching

![Screenshot placeholder: Creating shared folder and setting share permissions]

---

### Step 2: Configure NTFS Permissions

- NTFS permissions on share folder to allow appropriate access for `EngineeringShare` group

![Screenshot placeholder: NTFS permissions tab]

---
