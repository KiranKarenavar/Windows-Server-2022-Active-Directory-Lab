# 🔐 GPO Security Policies

## 📘 Overview

This section of the Active Directory Lab focuses on implementing essential security policies through Group Policy Objects (GPOs) to enhance the security posture of the domain environment. It encompasses configurations for password policies, account lockout mechanisms, and audit policies to ensure robust protection against unauthorized access and to maintain compliance with security best practices.

---

## 🔑 1. Password Policy

### 📝 Description

Established stringent password requirements to enforce strong authentication practices across all domain users.

### 🛠️ Group Policy Settings Applied

- **Minimum Password Length:** 12 characters

- **Password Complexity:** Enabled (requires a mix of uppercase, lowercase, numbers, and special characters)

- **Maximum Password Age:** 90 days

- **Minimum Password Age:** 30 day

- **Enforce Password History:** Remember last 24 passwords

- **Store Passwords Using Reversible Encryption:** Disabled

These settings are configured under:
  📂 `Computer Configuration → Windows Settings → Security Settings → Account Policies → Password Policy`

Detailed configurations can be found in the [`I. Password Policy`](../07-GPO-Security-Policies/I.%20Password-Policy.md) file.

---

## 🚫 2. Account Lockout Policy

### 📝 Description

Implemented account lockout settings to deter brute-force attacks and unauthorized access attempts.

### 🛠️ Group Policy Settings Applied

- **Account Lockout Threshold:** 5 invalid login attempts

- **Account Lockout Duration:** 15 minutes

- **Reset Account Lockout Counter After:** 15 minutes

These settings are configured under:
  📂 `Computer Configuration → Windows Settings → Security Settings → Account Policies → Account Lockout Policy`
  
Detailed configurations can be found in the [`II. Account-Lockout-Policy`](../07-GPO-Security-Policies/I.%20Account-Lockout-Policy.md) file.

---

## 🕵️ 3. Audit Policy

### 📝 Description

Configured audit policies to monitor and record critical security-related events, aiding in the detection of potential security breaches and ensuring accountability.

### 🛠️ Group Policy Settings Applied

- **Audit Logon Events:** Success and Failure

- **Audit Account Logon Events:** Success and Failure

- **Audit Account Management:** Success and Failure

- **Audit Directory Service Access:** Success and Failure

- **Audit Policy Change:** Success and Failure

- **Audit Privilege Use:** Success and Failure

- **Audit Process Tracking:** Success

- **Audit System Events:** Success and Failure

These settings are configured under:
  📂 `Computer Configuration → Windows Settings → Security Settings → Local Policies → Audit Policy`
  
Detailed configurations can be found in the [`III. Audit-Policy`](../07-GPO-Security-Policies/I.%20Audit-Policy.md) file.

---

## 📘 4. Group Policy Important Settings Guide

### 🔐 Security Baseline Settings

#### 📝 Description

Core security policies enforcing authentication standards and access controls, including password complexity requirements, account lockout thresholds, and user rights assignments to protect against brute force attacks and unauthorized access.

#### 🔑 Password Policies

These settings are configured under:  
  📂 `Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Password Policy`

| Setting | Value |
|---------|-------|
| Enforce password history | 24 passwords |
| Maximum password age | 90 days |
| Minimum password length | 14 characters |
| Password complexity | Enabled |

#### 🚫 Account Lockout Policies

These settings are configured under:  
  📂 `Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Account Lockout Policy`

| Setting | Value |
|---------|-------|
| Account lockout threshold | 5 attempts |
| Lockout duration | 30 minutes |

### 🛡️ Windows Defender Configuration

#### 📝 Description

Endpoint protection settings enabling real-time threat detection, behavioral monitoring, and network traffic filtering through Microsoft Defender Antivirus and Firewall rules to maintain system integrity and block malicious activity.

#### 🕵️‍♂️ Microsoft Defender Antivirus

These settings are configured under:  
  📂 `Computer Configuration > Policies > Administrative Templates > Windows Components > Microsoft Defender Antivirus`

Key Settings:
- Real-time protection: Enabled
- Behavior monitoring: Enabled
- Scheduled scans: Full scan weekly

#### 🧱 Firewall Settings

These settings are configured under:  
  📂 `Computer Configuration > Policies > Windows Settings > Security Settings > Windows Defender Firewall`

| Profile | Firewall State | Inbound | Outbound |
|---------|---------------|---------|----------|
| Domain | On | Block | Allow |

### 🖥️ User Experience Settings

#### 📝 Description

Standardized interface configurations that enforce corporate branding while limiting user customization options to reduce support overhead and maintain consistent productivity environments across the organization.

#### 💻 Desktop Configuration

These settings are configured under:  
  📂 `User Configuration > Policies > Administrative Templates > Desktop`
  
- Enforced corporate wallpaper
- Controlled desktop icons

#### 🪟 Start Menu Customization

These settings are configured under:  
  📂 `User Configuration > Policies > Administrative Templates > Start Menu and Taskbar`
  
- Removed "Search the Internet" option
- Disabled user tracking

### 🔄 Windows Update Management

#### 📝 Description

Centralized patch management policies that enforce scheduled security updates, feature rollouts, and quality patches while maintaining operational stability through controlled deployment cycles. Configures automatic download/install schedules with enterprise-appropriate deferral periods to balance security responsiveness with business continuity requirements.

These settings are configured under:  
  📂 `Computer Configuration > Policies > Administrative Templates > Windows Components > Windows Update`
  
- Update deployment: Semi-Annual Channel
- Quality updates: 7-day deferral
- Automatic updates: Enabled (3AM daily)

### 📦 Application Control

#### 📝 Description

Whitelisting policies leveraging AppLocker and deployment restrictions to prevent execution of unauthorized scripts, installers, and applications while permitting approved business-critical software.

#### 🔒 AppLocker Policies

These settings are configured under:  
  📂 `Computer Configuration > Policies > Windows Settings > Security Settings > Application Control Policies > AppLocker`
  
- Created default rules for:
  - Executables (.exe)
  - Windows Installers (.msi)
  - Scripts (.ps1, .bat)
  - Packaged Apps (AppX)

#### 🚫 App Deployment Restrictions

These settings are configured under:  
  📂 `Computer Configuration > Policies > Administrative Templates > Windows Components > App Package Deployment`
  
- Blocked user app installations
- Disabled special profile deployments

### 🔧 Device Management

#### 📝 Description

Hardware restriction policies that govern peripheral and storage device usage through device ID and class-based blocking to prevent data exfiltration and unauthorized hardware access.

These settings are configured under:  
  📂 `Computer Configuration > Policies > Administrative Templates > System > Device Installation`
  
- Blocked installation by:
  - Device IDs (specific hardware)
  - Setup classes (disk drives, etc.)

---

## ✅ Outcome

Implemented Group Policy configurations:
- **Enhanced Security Posture**: Reduced attack surface through strict password policies, application whitelisting, and device installation controls
- **Standardized User Environment**: Consistent desktop experience across all domain-joined systems with controlled customization options
- **Improved Compliance**: Meeting organizational security requirements through enforced Windows Defender configurations and update management
- **Reduced Attack Vectors**: Application control policies prevent execution of unauthorized scripts and binaries
- **Controlled Device Ecosystem**: Hardware restrictions prevent installation of unauthorized peripherals and storage devices
  
---

## 📁 Screenshot Storage

All screenshots for this section can be found in:<br />
📂 [`06-Screenshots/XI. Password Policy`](../06-Screenshots/D-Security-Policies)
