# 🖥️ Computer GPO Report

## 🏷️ 1. Applied Group Policy Objects

- **Default Domain Policy**
- **Windows Defender Configuration**
- **Block VLC - Policy**
- **Browser Security Settings Policy**
- **Control Panel Restrictions**
- **Default Domain Controller Policy**
- **Default Domain Policy**
- **Desktop Wallpaper Policy**
- **Disabling Unnecessary Windows Services Policy**
- **Drive Mappings Policy**
- **IPsec Authentication Policy**
- **Logon-Logoff Scripts Policy**
- **Map Network Drives Policy**
- **Network Security Settings Policy**
- **Restricted Groups Policy**
- **Service Configuration Policy**
- **Software Deployment Google Chrome Policy**
- **Start Menu and Taskbar Settings Policy**
- **Startup/Shutdown Scripts Policy**
- **USB Restriction Policy**
- **User Folder Redirection Policy**
- **Win11 Security Policy**
- **Windows Defender Settings Policy**
- **Windows Firewall Settings Policy**

📸 **Applied GPOs - Computer Scope**

![Summary of Computer-Specific Group Policy Settings](https://github.com/user-attachments/assets/c38a8bc4-657c-4934-beab-e68bee09f42c)

---

## 🚫 2. GPOs Not Applied

- **Local Group Policy**: Not applied (empty).
- **Logon-Logoff Scripts Policy Group Policy**: Not applied (Unknown Reason).

📸 **Filtered GPOs - Computer Scope**

![Summary of Computer-Specific Group Policy Settings 1](https://github.com/user-attachments/assets/fa82c4ce-4c6a-42cd-a6fe-73d9ca0fe518)

---

## 🛂 3. Security Group Memberships

- `BUILTIN\Administrators`
- `Everyone`
- `BUILTIN\Users`
- `NT AUTHORITY\NETWORK`
- `NT AUTHORITY\Authenticated Users`
- `This Organization`
- `DESKTOP-2N3JERQ$`
- `Domain Computers`
- `Authenticated authority asserted identity`
- `System Mandatory Level`

📸 **Security Groups - Computer Scope**

![Security Groups - Computer Scope](https://github.com/user-attachments/assets/94717468-94f5-465e-b48f-6c471450c184)

📸 **Last GP Update - Computer Scope**

![Last GP Update - Computer Scope](https://github.com/user-attachments/assets/7f70da7c-e28a-4029-a255-406d76fd4752)

---

## 🖌️ 4. Additional Screenshots

### A. Command Prompt Output: `gpresult /r /scope:computer`

#### 📝 Description

Displays a summary of computer-specific Group Policy settings.

#### 🎯 Purpose

Provides a quick overview of applied GPOs and system information.
   - `Capture Location`: Client Machine
     
📸 **Command Prompt Output: `gpresult /r /scope:computer`**
   
![Summary of Computer-Specific Group Policy Settings](https://github.com/user-attachments/assets/49fa90da-59d7-4aac-9582-d757dc90b429)

![Summary of Computer-Specific Group Policy Settings 1](https://github.com/user-attachments/assets/86001b69-b575-48fb-b5fe-16e85a0fc011)

### B. Command Prompt Output: `gpresult /v /scope:computer`

#### 📝 Description 

Shows verbose details of computer policies.

#### 🎯 Purpose
Offers in-depth information on each policy setting applied to the computer.
   - `Capture Location`: Client Machine

📸 **Command Prompt Output: `gpresult /v /scope:computer`**
   
![gpresult /v /scope:computer](https://github.com/user-attachments/assets/7ce50106-a21f-407b-9d95-775d71970248)

![gpresult /v /scope:computer 1](https://github.com/user-attachments/assets/9ecf51b9-1397-4637-a32e-53f2e4ad74e3)

![gpresult /v /scope:computer 2](https://github.com/user-attachments/assets/d5207a5b-8978-4c36-823a-5befddac76c5)

![gpresult /v /scope:computer 3](https://github.com/user-attachments/assets/111fb30d-508d-42ec-8e48-695ae0445a13)

![gpresult /v /scope:computer 4](https://github.com/user-attachments/assets/fdc31f66-eed9-4700-b596-e8ba3cfd1eb7)

![gpresult /v /scope:computer 5](https://github.com/user-attachments/assets/978ca0e4-78c1-4ac2-86e3-23292ecb101e)

![gpresult /v /scope:computer 6](https://github.com/user-attachments/assets/9f94d82d-0e93-4820-aa59-a52159eaafab)

![gpresult /v /scope:computer 7](https://github.com/user-attachments/assets/4c5e6173-ceb2-4286-9894-143d39cb52a8)

![gpresult /v /scope:computer 8](https://github.com/user-attachments/assets/153510f4-4a89-45a4-aa83-a1cb4f26888d)

![gpresult /v /scope:computer 9](https://github.com/user-attachments/assets/70b46c7c-f7a9-492d-be03-92ebf955a5a2)

![gpresult /v /scope:computer 10](https://github.com/user-attachments/assets/4369ac68-a1be-41e9-acd7-0fe92b778489)

![gpresult /v /scope:computer 11](https://github.com/user-attachments/assets/a3308e0a-e5fd-4777-b6be-d1a0d4af0d2b)

![gpresult /v /scope:computer 12](https://github.com/user-attachments/assets/b20dae67-b09c-42e3-80d7-ae329619877b)

![gpresult /v /scope:computer 13](https://github.com/user-attachments/assets/6103f3d2-0461-4945-b9a6-bf4e85128144)

![gpresult /v /scope:computer 14](https://github.com/user-attachments/assets/730cbaaf-4134-4bf2-8a10-c0ffcea4f9ed)   

![gpresult /v /scope:computer 15](https://github.com/user-attachments/assets/c69870ee-aeef-42e1-8ed9-55fe0632487c)

### C. **Group Policy Results Wizard in GPMC (Computer Configuration)**
   
#### 📝 Description 

Screenshot of the Group Policy Results Wizard displaying computer configuration results.

#### 🎯 Purpose

Visual representation of GPOs applied to the computer, aiding in analysis and troubleshooting.
   - `Capture Location`: Domain Controller
   
---

### D. HTML Report Generated by `gpresult /h`

#### 📝 Description 

Snapshot of the HTML report focusing on the computer configuration section.

#### 🎯 Purpose

Provides a formatted and comprehensive view of applied policies.
   - `Capture Location`: Client Machine

---

## 🔄 5. Last Group Policy Application

- **Date**: 2025-05-02
- **Time**: 4:46 PM
- **Domain Controller**: WIN-D2PQBCI88JQ.hughkumbi.local
