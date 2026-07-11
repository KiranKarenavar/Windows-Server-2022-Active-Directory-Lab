# 🔥 Disabling Unnecessary Windows Services via GPO

Reducing the attack surface of domain-joined machines is essential for a secure environment. In this section, I created and applied a GPO to **disable unnecessary or high-risk Windows services** that are not required for daily operations.

---

## 🏷️ 1. GPO Name

- **GPO Name:** Disabling Unnecessary Windows Services Policy  
- **Linked To:** cloud.com (domain root)


## 🛠️ 2. Services Disabled

I disabled the following services using Group Policy Preferences:  
  `Computer Configuration > Preferences > Control Panel Settings > Services`

### 🚫 Print Spooler

- **Service Name:** Spooler  
- **Action:** Stop service and set Startup type to **Disabled**  
- **Reason:** Prevents PrintNightmare and remote printing vulnerabilities


### 🚫 Xbox Services

- **Service Names:** XblAuthManager, XblGameSave, XboxNetApiSvc, XboxGipSvc
- **Action:** Stop services and set Startup type to **Disabled**
- **Reason:** Unnecessary in business/server environments, reduces attack surface and improves performance


### 🚫 Windows Media Player Network Sharing Service

- **Service Name:** WMPNetworkSvc
- **Action:** Stop service and set Startup type to **Disabled**
- **Reason:** Eliminates unnecessary network exposure for media streaming functionality


### 🚫 Fax

- **Service Name:** Fax
- **Action:** Stop service and set Startup type to **Disabled**
- **Reason:** Legacy service rarely used in modern environments that presents potential attack vectors


### 🚫 Remote Registry

- **Service Name:** RemoteRegistry  
- **Action:** Stop service and set Startup type to **Disabled**  
- **Reason:** Blocks remote registry modifications that can be exploited


### 🚫 SNMP

- **Service Name:** SNMP  
- **Action:** Stop service and set Startup type to **Disabled**  
- **Reason:** Legacy service with known vulnerabilities


### 🚫 Telnet

- **Service Name:** TlntSvr  
- **Action:** Stop service and set Startup type to **Disabled**  
- **Reason:** Telnet is an insecure protocol and should be replaced by SSH/PowerShell Remoting


### 🚫 Windows Search

- **Service Name:** WSearch
- **Action:** Stop service and set Startup type to **Disabled**
- **Reason:** Reduces unnecessary resource usage on servers where desktop search is not needed


### 🚫 Windows Update

- **Service Name:** wuauserv
- **Action:** Set Startup type to Manual
- **Reason:** Better to control updates through WSUS or central management rather than automatic checks


### 🚫 Windows Error Reporting

- **Service Name:** WerSvc
- **Action:** Stop service and set Startup type to Disabled
- **Reason:** Prevents unnecessary data transmission and improves performance


### 🚫 Secondary Logon

- **Service Name:** seclogon
- **Action:** Stop service and set Startup type to Disabled
- **Reason:** Commonly exploited for privilege escalation attacks

---

## 🗂️ 4. Screenshot Storage

All related screenshots are stored in: <br /> 
📂 [`06-Screenshots/XXIX. Disable-Services`](https://github.com/Hugh-Kumbi/Hugh-Kumbi-Active-Directory-Lab/tree/main/06-Screenshots/XXIX.%20Disable-Services)
