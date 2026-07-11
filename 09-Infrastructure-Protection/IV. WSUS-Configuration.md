# 🔧 WSUS-Configuration

  ## 🔍 Overview

In this section of my Active Directory lab, I configured **Windows Server Update Services (WSUS)** on **Windows Server 2022** to centrally manage updates for domain-joined Windows 11 clients. This setup ensures that updates are controlled, approved, and deployed consistently across the network, which is crucial for system stability, compliance, and security.

---

## 🛠️ Configuration Steps

### 1. 📥 Install WSUS Role and Features

Using **Server Manager**, I installed the **WSUS role** with the required components:

- Launched **Add Roles and Features Wizard**
- Selected:
  - Role: `Windows Server Update Services`
  - Role Services: `WSUS Services`, `WID Database`, and `WSUS Console`
- Chose to store updates locally in:  
  `D:\WSUS\Updates`

📸 **WSUS Role Installation Summary**

---

### 2. ⚙️ Configure WSUS Post-Installation

After installation, I completed the **WSUS Post-Installation Tasks**:

- Opened **WSUS Configuration Wizard**
- Specified upstream server: `Microsoft Update`
- Selected products: `Windows 10`, `Windows Server 2022`
- Chose classifications: `Critical Updates`, `Security Updates`, and `Feature Packs`
- Scheduled synchronization daily at 3:00 AM

📸 **WSUS Configuration Wizard – Products and Classifications**

---

### 3. ✅ Approve Updates

Once synchronization completed:

- In the **WSUS Console**, I navigated to:
  - `Updates` > `All Updates` > `Unapproved`
- Approved selected updates for the `Test Group`

📸 **Approved Updates in WSUS Console**

---

### 4. 🖥️ Configure Group Policy for WSUS Clients

Using **Group Policy Management**, I created and linked a GPO to apply WSUS settings to my domain-joined Windows 11 clients:

- GPO Name: `WSUS Client Configuration`
- Edited the following settings under:  
  `Computer Configuration > Administrative Templates > Windows Components > Windows Update`

**Settings:**
- **Specify intranet Microsoft update service location:**  
  `http://10.221.1.10:8530`
- **Configure Automatic Updates:**  
  Enabled with option `4 – Auto download and schedule the install`
- **Scheduled install day/time:**  
  Every day at 4:00 AM

📸 **Group Policy Settings for WSUS**

---

### 5. 🔄 Force Group Policy Update and Confirm Client Detection

On both Windows 10 clients:

- Ran `gpupdate /force` from Command Prompt
- Checked Windows Update registry entries using `regedit` to confirm WSUS configuration
- Used the following PowerShell command to confirm the client was detected by WSUS:

```powershell
Get-WindowsUpdateLog
```

Verified clients appeared under Computers in WSUS Console

📸 **Windows 11 Clients Appearing in WSUS Console**

---

## ✍️ Summary

This lab demonstrates my ability to deploy and configure WSUS on Windows Server 2025 to manage patching for domain-joined Windows clients. Centralizing updates ensures better control, reduces internet bandwidth usage, and enforces consistent update policies across the organization.

Key skills showcased:
- Installing WSUS with local content storage
- Synchronizing and approving Microsoft updates
- Configuring GPO to point clients to WSUS
- Validating WSUS client connectivity and update compliance

📸 **Final WSUS Dashboard with Synced Updates and Connected Clients**
