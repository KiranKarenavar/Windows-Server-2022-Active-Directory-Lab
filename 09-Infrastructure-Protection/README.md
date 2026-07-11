# 🛡️ Infrastructure Protection

## 📘 Overview

This section of the Active Directory Lab focuses on enhancing the security posture of the domain environment. It outlines the implementation of firewall rules, network security configurations, and the disabling of unnecessary services through Group Policy Objects (GPOs). These measures aim to reduce the attack surface and enforce best practices within the Active Directory infrastructure.

---

## 🔥 1. Windows Firewall Configuration

### 📝 Description

I enforced strict firewall rules on all domain-joined systems to protect the internal network from unauthorized access and to control inbound and outbound traffic.

### 🛠️ Group Policy Settings Applied

- **Domain Profile:** Enabled, Block Inbound, Allow Outbound
- **Private Profile:** Enabled, Block Inbound, Allow Outbound
- **Public Profile:** Enabled, More restrictive settings (e.g., block RDP and file sharing)

---

## 🌐 2. Network Security Settings

### 📝 Description

I configured LAN Manager authentication and session security to enforce strong encryption and prevent legacy protocol use.

### 🛠️ GPO Settings Applied

- LAN Manager Authentication Level: **Send NTLMv2 response only. Refuse LM & NTLM**
- Minimum session security for NTLM SSP (Clients & Servers): **128-bit encryption**
- Digitally sign communications for Server & Clients (always): **Enabled**

---

## 🧹 3. Disabled Unnecessary Services

### 📝 Description

To reduce the attack surface, I disabled several services not required in this lab environment.

### 🛠️ Services Disabled via GPO

- **Print Spooler** – Disabled on servers not offering print services.
- **Remote Registry** – Prevented remote tampering.
- **Telnet Service** – Obsolete and insecure.
- **SNMP** – Disabled unless explicitly needed for monitoring.

---

## ✅ 4. Verification & Testing

- Verified firewall rules with `Windows Defender Firewall with Advanced Security`.
- Used `telnet` and `nmap` to scan for disabled services.
- Confirmed services were stopped and set to “Disabled” startup type via `services.msc` and `gpresult`.

---

## 📂 5. Files Included

`I. Windows-Firewall.md`: Detailed steps and configurations for implementing Windows Firewall rules via GPO.

`II. Network-Security.md`: Instructions for setting up network security protocols and configurations.

`III. Disable-Services.md`: Guidelines for identifying and disabling unnecessary services to harden the domain environment.

`README.md`: This documentation file summarizing the configurations and their purposes.

---

## ✅ 6. Outcome

By applying these configurations:

Enhanced Security: Strengthened the domain's defense against unauthorized access and potential attacks.

Standardization: Ensured consistent security settings across all domain-joined systems.

Reduced Attack Surface: Minimized potential vulnerabilities by disabling unnecessary services.

---

## 🔁 7. Lessons Learned

- Infrastructure protection must be proactive and layered.
- Group Policy is a powerful tool for enforcing uniform, secure configurations across multiple endpoints.

