# 🔐 BitLocker Drive Encryption Policies for Windows Server 2025 Active Directory

In this section, I enforced BitLocker drive encryption policies to protect data at rest on all Windows 11 client devices. This policy ensures that all operating system drives are encrypted using secure standards and recovery mechanisms, providing resilience against data breaches caused by device loss or theft.

---

## 🏷️ 1. GPO Names

- **GPO Name:** BitLocker Drive Encryption Policy  
- **Linked To:** MeiVaultComputers

- **GPO Name:** BitLocker DRA Deployment Policy   
- **Linked To:** hughdomain.local (domain root)

---

## ⚙️ 2. Policy Configuration

### ✅ Operating System Drives

In the GPO, I navigated to:

  📂 `Computer Configuration > Policies > Administrative Templates > Windows Components > BitLocker Drive Encryption > Operating System Drives`

- **Require additional authentication at startup:** Enabled  
- **Checked** "Requires a password or startup key on a USB flash drive"
- **Configure TPM startup key settings:** Enabled  
  - **Allow TPM:** Yes  
  - **Do not allow PIN + TPM:** Yes  
  - **Do not allow Startup Key + TPM:** Yes  
  - **Do not allow TPM + PIN + Startup Key:** Yes

- **Enable use of BitLocker authentication requiring preboot keyboard input on slates:** Enabled
- **Configure minimum PIN length for startup:** Enabled
- **Choose how BitLocker-protected operating system drives can be recovered:** Enabled  
- **Configure use of hardware-based encryption for operating system drives:** Disabled
- **Allow enhanced PINs for startup:** Enabled
- **Choose drive encryption method and cipher strength:** Enabled  
  - **Setting:** XTS-AES 256-bit  

### 3. 🧩 Configure Fixed Data Drive Encryption

In the GPO, I navigated to:

  📂 `Computer Configuration → Administrative Templates → Windows Components → BitLocker Drive Encryption → Fixed Data Drives`

I enabled:

- **Allow access to BitLocker-protected fixed data drives from earlier versions of Windows:** Enabled
- **Choose how BitLocker-protected fixed drives can be recovered:** Enabled
- **Configure use of hardware-based encryption for fixed data drives:** Enable
- **Configure use of passwords for fixed data drives:** Enabled
- **Configure use of smart cards on fixed data drives:** Enabled
- **Deny write access to removable drives not protected by BitLocker:** Enabled
- **Enforce drive encryption type on fixed data drives:** Enabled


### 4. 🔑 Configure Removable Drive Encryption

In the GPO, I navigated to:

  📂 `Computer Configuration → Administrative Templates → Windows Components → BitLocker Drive Encryption → Removable Data Drives`

I enabled:

- **Configure use of password for removable data drives:** Enabled
- **Control use of BitLocker on removable drives** Enabled 
- **Deny write access to removable drives not protected by BitLocker:** Enabled

---

### 5. 🌐 Enable Network Unlock

To allow systems to automatically unlock BitLocker-protected OS drives on domain-joined systems with TPM, I enabled:

- **Store BitLocker recovery information in Active Directory Domain Services(Windows Server 2008 and Windows Vista):** Enabled
- **Choose default folder for recovery password:** Enabled
- **Choose how users can recover BitLocker-protected drives(Windows & Windows Server2012, Windows 8.1, Windows Server 2012 R2, Windows 10 )(Version 1507):** Enabled
- **Choose drive encryption method and cipher strength(Windows 8, Windows Server2012, Windows 8.1, Windows Server 2012 R2, Windows 10 (Version 1507)):** Enabled
- **Disable new DMA devices when this computer is locked (Windows 10 (Version 1511)):** Enabled
- **Provide the unique identifiers for your organization:** Enabled
- **Prevent memory overwrite on restart:** Enabled
- **Validate smart card certificate usage rule compliance:** Enabled

---

### 6. 🗄️ Configure Data Recovery Agents (DRA)

To manage data recovery securely, I:

1. Created a DRA certificate using the `manage-bde -protectors` command.
2. Exported the certificate and added it to the GPO under:

  📂 `Computer Configuration → Policies → Windows Settings → Security Settings → Public Key Policies → BitLocker Drive Encryption`

---

## Summary

This section demonstrated how to manage full-disk encryption across different drive types using Group Policy. It reflects a practical understanding of enterprise-grade BitLocker deployment, compliance enforcement, and data recovery preparedness in an Active Directory environment.

### ✅ BitLocker Recovery

**Path:** 📂 `BitLocker Drive Encryption > Operating System Drives > BitLocker Recovery`

- **Save BitLocker recovery information to Active Directory Domain Services:** Enabled  
  - ✅ Store recovery passwords and key packages  
- **Do not enable BitLocker until recovery information is stored to AD DS:** Enabled  

## 🧪 3. Verification and Testing

- Ran `gpupdate /force` on a Windows 11 domain-joined client.  
- Used `manage-bde -status` and `Get-BitLockerVolume` in PowerShell to verify BitLocker encryption status.  
- Confirmed recovery keys were stored in Active Directory via the **Active Directory Users and Computers (ADUC)** console.  
- Rebooted to test TPM + PIN prompt on startup.

---

## 🗂️ 4. Screenshot Storage

All images related to this section are stored in:  
📂 [`06-Screenshots/XXXI. BitLocker-Encryption`](https://github.com/Hugh-Kumbi/Hugh-Kumbi-Active-Directory-Lab/blob/main/06-Screenshots/XXXI.%20BitLocker-Encryption/README.md)
