# 💻 Windows 10 Client Setup

This section details how I configured and joined two Windows 10 Pro clients—**AD-WIN10-01** and **AD-WIN10-02**—to my domain `cloud.com`.

---

## 🖥️ 1. Virtual Machine Configuration

I created two new VMs in **VirtualBox** with the following specifications:

- **VM Names:** `AD-WIN10-01` and `AD-WIN10-02`
- **OS:** `Windows 10 Pro`
- **RAM:** `4 GB each`
- **CPU:** `2 cores each`
- **Disk:** `50 GB each`
- **Network Adapter:** `Internal Network (same as Domain Controller)`

📸 **VirtualBox Virtual Machine General Settings for `AD-WIN10-01`**

![VirtualBox VM General Settings for AD-WIN10-01](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/01.png)

📸 **VirtualBox Virtual Machine System Motherboard Settings for `AD-WIN10-01`**

![VirtualBox VM System Motherboard Settings for AD-WIN10-01](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/02.png)

📸 **VirtualBox Virtual Machine System Processor Settings for `AD-WIN10-01`**

![VirtualBox VM System Processor Settings for AD-WIN10-01](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/03.png)

📸 **VirtualBox Virtual Machine Display Screen Settings for `AD-WIN10-01`**

![VirtualBox VM Display Screen Settings for AD-WIN10-01](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/04.png)

📸 **VirtualBox Virtual Machine Storage Settings for `AD-WIN10-01`**

![VirtualBox VM Storage Settings for AD-WIN10-01](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/05.png)

📸 **VirtualBox Virtual Machine Network Settings for `AD-WIN10-01`**

![VirtualBox VM Network Settings for AD-WIN10-01](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/06.png)

---

## 🌐 2. Network & Hostname Setup

After installation, I did the following on both clients:

- Changed host machine names as:
  - `AD-WIN10-01`
  - `AD-WIN10-02`
- Set static IP addresses and DNS:
  - AD-WIN10-01: `10.221.1.11`
  - AD-WIN10-02: `10.221.1.12`
- Set Preferred DNS to point to the Domain Controller: `10.221.1.10`
- Restarted each machine to apply changes

📸 **Network Settings with Static IP and DNS for `AD-WIN10-01`**

![Network Settings With Static IP and DNS For `AD-WIN10-01](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/07.png)

📸 **Windows IP Configuration for `AD-WIN10-01`**

![Windows IP Configuration for AD-WIN10-01](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/08.png)

📸 **System > About > Showing Changed Computer Name for `AD-WIN10-01`**

![System - About - Showing Changed Computer Name 1](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/09.png)

📸 **Network Settings with Static IP and DNS for `AD-WIN10-02`**

![Network Settings With Static IP and DNS for AD-WIN10-02](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/10.png)

📸 **Windows IP Configuration for `AD-WIN10-02`**

![Windows IP Configuration for AD-WIN10-02](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/11.png)

📸 **System > About > Showing Changed Computer Name for `AD-WIN10-02`**

![System - About - Showing Changed Computer Name 2](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/12.png)

---

## 🏢 3. Joining the Domain

On each client:

1. Opened **📂 `Settings > System > About > Rename this PC (Advanced)`**
2. Selected **Domain Join**, entered `cloud.com`
3. Supplied credentials for a domain admin account
4. Restarted the machine when prompted

📸 **Confirmation Screen for Successful Domain Join for `AD-WIN10-01`**

![Confirmation Screen for Successful Domain Join](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/13.png)

📸 **Confirmation Screen for Successful Domain Join for `AD-WIN10-02`**

![Confirmation Screen for Successful Domain Join](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/16.png)

---

## 🧪 4. Verification

After reboot, I:

- Logged in using domain credentials
- Verified domain membership in **System Properties**
- Confirmed connectivity to the Domain Controller via `ping` and `nslookup`

📸 **System Properties Showing Domain Joined for `AD-WIN10-01`**

![System Properties Showing Domain Joined for AD-WIN10-01](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/15.png)

![System Properties Showing Domain Joined for AD-WIN10-01 1](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/14.png)

**PowerShell Showing Successful Ping for `AD-WIN10-01`**

📸 **Login Screen with Domain Name Shown for `AD-WIN10-02`**

![Login Screen with Domain Name Shown for AD-WIN10-02](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/16.png)

📸 **System Properties Showing Domain Joined for `AD-WIN10-02`**

![System Properties Showing Domain Joined for AD-WIN10-02](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/18.png)

![System Properties Showing Domain Joined for `AD-WIN10-02 1](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines/17.png)

**PowerShell Showing Successful Ping for `AD-WIN10-02`**

---

## 📦 7. Summary

| Client Name         | IP Address    | DNS Server     | Domain Joined    |
|---------------------|---------------|----------------|------------------|
| **AD-WIN10-01**     | 10.221.1.11   | 10.221.1.10    | cloud.com        |
| **AD-WIN10-02**     | 10.221.1.12   | 10.221.1.10    | cloud.com        |

---

## 📁 8. Screenshot Storage

All screenshots for this section can be found in:  
📂 [`06-Screenshots/B-Environment Setup/Windows 10 Machines`](../06-Screenshots/B-Environment%20Setup/Windows%2010%20Machines)
