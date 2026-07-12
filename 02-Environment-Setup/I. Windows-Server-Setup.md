# 🛠️ Windows Server 2022 Setup

In this stage, I installed and configured **Windows Server 2022** as the Domain Controller (DC) for my lab environment. The process included setting a static IP, changing the computer name, installing Active Directory Domain Services, and promoting the server to a DC.

---

## 💾 1. Installation

- Created a new virtual machine in **VirtualBox** with the following specs:
  - 8 GB RAM
  - 2 CPUs
  - 50 GB virtual hard drive
- Mounted the **Windows Server 2022 ISO** and completed the installation.
- Selected the **Datacenter Evaluation (Desktop Experience)** during setup.

📸 **Installation Setup Screen with Edition Selection**

![Windows Server Setup 3](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/01.png)

📸 **First Boot Desktop After Installation**

![First Boot Desktop After Installation](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/02.png)

---

## 💻 2. Initial Configuration

After installation, I performed the following:

- Changed the machine name to `WinServer2022`
- Set a **static IP address**: `10.221.1.10`
- Configured DNS to point to itself (`10.221.1.10`)
- Set the computer’s **time zone**

📸 **Network Settings Showing Static IP and DNS Config**

![Network Settings Showing Static IP and DNS Config 1](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/03.png)

📸 **System > About > Showing Changed Computer Name**

![System - About - Showing Changed Computer Name](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/04.png)

---

## 🧱 3. Installing AD DS Role

- Opened **Server Manager**
- Selected **Add Roles and Features**
- Installed the **Active Directory Domain Services (AD DS)** role

📸 **"Add Roles and Features Wizard" with AD DS Selected**

![Add Roles and Features Wizard With AD DS Selected 3](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/05.png)

---

## 🏰 4. Promoting to Domain Controller

- Promoted the server to a DC using the post-installation wizard
- Created a **new forest** named `cloud.com`
- Accepted the default NetBIOS name: `WinServer2022`
- Rebooted the machine after setup completed

📸 **Confirmation of Successful Promotion**

![Confirmation of Successful Promotion](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/06.png)

---

## 🧪 5. Post-Installation Checks

- Logged in using the domain admin account
- Verified domain controller health using `dcdiag` in PowerShell
- Ensured DNS was properly installed and functioning
- Confirmed that AD-related services were running

📸 **PowerShell with `dcdiag` Results**

![PowerShell With dcdiag Results](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/07.png)

![PowerShell With dcdiag Results 1](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/08.png)

![PowerShell With dcdiag Results 2](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/09.png)

![PowerShell With dcdiag Results 3](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/10.png)

![PowerShell With dcdiag Results 4](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/11.png)

![PowerShell With dcdiag Results 5](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/12.png)

![PowerShell With dcdiag Results 6](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/13.png)


📸 **DNS Manager Showing Forward Lookup Zone for `cloud.com`**
  
![DNS Manager Showing Forward Lookup Zone for cloud](../06-Screenshots/B-Environment%20Setup/Windows%20Server%202022/14.png)

---

## 📦 6. Summary

| Configuration Item         | Value                            |
|----------------------------|----------------------------------|
| **Server Name**            | WinServer2022                    |
| **Static IP**              | 10.221.1.10                      |
| **Domain Name**            | cloud.com                        |
| **DNS Server**             | 10.221.1.10 (local)              |
| **AD Role Installed**      | Active Directory Domain Services |
| **Domain Controller Type** | New Forest                       |

---

## 📁 7. Screenshot Storage

All screenshots for this section can be found in:  
📂 [`06-Screenshots/II. Windows-Server-Setup`](https://github.com/Hugh-Kumbi/Hugh-Kumbi-Active-Directory-Lab/blob/main/06-Screenshots/II.%20Windows-Server-Setup/README.md)  
