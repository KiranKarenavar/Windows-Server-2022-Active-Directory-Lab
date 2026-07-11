# 🌐 Network Security Configuration via GPO

In this section, I implemented secure network communication policies across all domain-joined systems to ensure data confidentiality and integrity. These settings help defend against man-in-the-middle (MITM) attacks and enforce strong authentication protocols.

---

## 🏷️ 1. GPO Name

- **GPO Name:** Network Security Policy  
- **Linked To:** cloud.com (domain root)

---

## 🔐 2. Security Settings Applied

The following settings were configured under:  
 📂 `Computer Configuration > Policies > Windows Settings > Security Settings > Local Policies > Security Options`

### ✅ LAN Manager Authentication Level
- **Policy:** Network Security: LAN Manager authentication level  
- **Setting:** **Send NTLMv2 response only. Refuse LM & NTLM**

### ✅ Minimum Session Security for NTLM SSP
- **Policy:** Network Security: Minimum session security for NTLM SSP based (including secure RPC) clients  
- **Setting:** **Require NTLMv2 session security and 128-bit encryption**

- **Policy:** Network Security: Minimum session security for NTLM SSP based servers  
- **Setting:** **Require NTLMv2 session security and 128-bit encryption**

### ✅ Digitally Sign Communications
- **Policy:** Microsoft Network Client: Digitally sign communications (always)  
- **Setting:** **Enabled**

- **Policy:** Microsoft Network Server: Digitally sign communications (always)  
- **Setting:** **Enabled**

---

## 🧪 3. Verification and Testing

- Ran `gpupdate /force` on client machines to apply policies immediately.
- Used `secpol.msc` and `gpresult /h` to verify effective policy settings.
- Attempted legacy connections to confirm they were blocked or upgraded to NTLMv2.

---

## 🗂️ 4. Screenshot Storage

All images related to this section are stored in:<br />
📂 [`06-Screenshots/XXVIII. Network-Security`](https://github.com/Hugh-Kumbi/Hugh-Kumbi-Active-Directory-Lab/tree/main/06-Screenshots/XXVIII.%20Network-Security)
