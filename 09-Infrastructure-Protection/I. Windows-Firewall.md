# 🔥 Windows Firewall Group Policy Configuration

This document outlines how I configured **inbound and outbound firewall rules via Group Policy** to ensure that essential Active Directory services are permitted while blocking insecure or unnecessary protocols.

---

## 🏷️ 1. GPO Name

- **GPO Name:** Windows Firewall Settings Policy  
- **Linked To:** hughdomain.local (domain root)

---

## 🔧 2. Inbound Firewall Rule Configuration

I created multiple **inbound rules** for Active Directory communication services using:

📂 `Computer Configuration > Policies > Windows Settings > Security Settings > Windows Defender Firewall with Advanced Security > Inbound Rules`

### 🌐 Allow DNS Rules

   * __Rule Type:__ Port
   * __Protocols:__ TCP and UDP (separate rules)
   * __Ports:__ 53
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Names:__ Allow DNS TCP, Allow DNS UDP
   * __Description:__ Permits Domain Name System (DNS) resolution traffic over TCP to support name resolution services critical for Active Directory functionality. Port 53 TCP & Port 53 UDP.

### 🔐 Allow LDAP Rule

   * __Rule Type:__ Port
   * __Protocol:__ TCP
   * __Port:__ 389
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Name:__ Allow LDAP TCP
   * __Description:__ Allows LDAP authentication for Active Directory

### 🛡️ Allow LDAP SSL Rule

   * __Rule Type:__ Port
   * __Protocol:__ TCP
   * __Port:__ 636
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Name:__ Allow LDAP SSL TCP
   * __Description:__ Allows secure LDAP authentication

### 🌍 Allow Global Catalog Rule

   * __Rule Type:__ Port
   * __Protocol:__ TCP
   * __Port:__ 3268
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Name:__ Allow Global Catalog TCP
   * __Description:__ Allows Global Catalog queries


### ⚙️ Allow Global Catalog SSL Rule

   * __Rule Type:__ Port
   * __Protocol:__ TCP
   * __Port:__ 3269
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Name:__ Allow Global Catalog SSL TCP
   * __Description:__ Allows secure Global Catalog queries


### 🔑 Allow Kerberos Authentication Rules

   * __Rule Type:__ Port
   * __Protocols:__ TCP and UDP (separate rules)
   * __Ports:__ 88
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Names:__ Allow Kerberos TCP, Allow Kerberos UDP
   * __Description:__ Allows Kerberos authentication over TCP and UDP. Port 88 TCP & Port 88 UDP.


### 🔄 Allow Kerberos Password Change

   * __Rule Type:__ Port
   * __Protocols:__ TCP
   * __Ports:__ 464
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Names:__ Allow Kerberos Password Change TCP
   * __Description:__ Allows Kerberos password changes.


### 📁 Allow SMB (File Sharing) Rule

   * __Rule Type:__ Port
   * __Protocols:__ TCP
   * __Port:__ 445
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Name:__ Allow SMB TCP
   * __Description:__ Allows SMB (File Sharing).

### 🗄️ Allow RPC Endpoint Mapper Rule

   * __Rule Type:__ Port
   * __Protocols:__ TCP
   * __Port:__ 135
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Name:__ Allow RPC Endpoint Mapper TCP
   * __Description:__ Allows RPC endpoint mapping for Windows Services.


### 🚀 Allow RPC Dynamic Ports Rule

   * __Rule Type:__ Port
   * __Protocols:__ TCP
   * __Port:__ 1024-5000
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Name:__ Allow RPC Dynamic Ports TCP
   * __Description:__ Allows RPC dynamic port range for Windows services.


### 🕒 Allow Windows Time Service Rule

   * __Rule Type:__ Port
   * __Protocols:__ UDP
   * __Port:__ 123
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Name:__ Allow Windows Time Service UDP
   * __Description:__ Allows NTP time synchronization.

### ⚡ Allow ICMP Echo Request (Ping) Rule

   * __Rule Type:__ Custom
   * __Protocols:__ ICMPv4
   * __Programs:__ All programs
   * __ICMP settings:__ Specific ICMP types — Echo Request
   * __Scope:__ Any IP address 
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Name:__ Allow ICMP Echo Request (Ping)
   * __Description:__ Allows ping requests for network troubleshooting.


### 🖥️ Remote Desktop Protocol (RDP) Rule

   * __Rule Type:__ Predefined
   * __Remote Desktop Rules:__ Remote Desktop - Shadow (TCP-In), Remote Desktop - User Mode (TCP-In), Remote Desktop - User Mode (UDP-In)
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Description:__ 
     - Inbound rule for the Remote Desktop service to allow shadowing of an existing Remote Desktop session. (TCP-In)
     - Inbound rule for the Remote Desktop service to allow RDP traffic. [TCP 3389]
     - Inbound rule for the Remote Desktop service to allow RDP traffic. [UDP 3389]


### 🛠️ Windows Remote Management (WinRM) Rule

   * __Rule Type:__ Predefined
   * __Windows Remote Management Rules:__ Windows Remote Management (HTTP-In), Windows Remote Management (HTTP-In)
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Description:__ 
     - Inbound rule for Windows Remote Management via WS-Management. [TCP 5985]
     - Inbound rule for Windows Remote Management via WS-Management. [TCP 5985]


### 📤 File and Printer Sharing Rule

   * __Rule Type:__ Predefined
   * __File and Printer Sharing Rule Rules:__ File and Printer Sharing (NB-Name-In), File and Printer Sharing (NB-Session-In), File and Printer Sharing (SMB-In)
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Description:__ 
     - Inbound rule for File and Printer Sharing to allow NetBIOS Name Resolution. [UDP 137]
     - Inbound rule for File and Printer Sharing to allow NetBIOS Session Service connections. [TCP 139]
     - Inbound rule for File and Printer Sharing to allow Server Message Block transmission and reception via Named Pipes. [TCP 445]


**Overview of all Newly Added Inbound Rules**

---

## 🔧 3. Outbound Firewall Rule Configuration

I created multiple **inbound rules** for Active Directory communication services using:

📂 `Computer Configuration > Policies > Windows Settings > Security Settings > Windows Defender Firewall with Advanced Security > Outbound Rules`

### 🌐 Allow DNS Queries Rules

   * __Rule Type:__ Port
   * __Protocols:__ TCP and UDP (separate rules)
   * __Ports:__ 53
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Names:__ Allow DNS Queries TCP, Allow DNS Queries UDP
   * __Description:__ Allows outbound DNS queries over TCP and UDP.

### 💻 Allow LDAP Queries Rules

   * __Rule Type:__ Port
   * __Protocols:__ TCP
   * __Ports:__ 389
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Names:__ Allow LDAP Queries TCP
   * __Description:__ Allows outbound LDAP queries.

### 🔐 Allow Kerberos Authentication Rules

   * __Rule Type:__ Port
   * __Protocols:__ TCP and UDP (separate rules)
   * __Ports:__ 88
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Names:__ Allow Kerberos Auth TCP
   * __Description:__ Allows outbound Kerberos authentication over TCP.

### 🕒 Allow Windows Time Sync Rules

   * __Rule Type:__ Port
   * __Protocols:__ UDP
   * __Ports:__ 123
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Names:__ Allow Windows Time Sync UDP
   * __Description:__ Allows outbound NTP time synchronization.

### 📡 Allow HTTP/HTTPS for Updates Rules

   * __Rule Type:__ Port
   * __Protocols:__ TCP
   * __Ports:__ 80,443
   * __Action:__ Allow the connection
   * __Profile:__ Domain only
   * __Names:__ Allow HTTP/HTTPS TCP
   * __Description:__ Allows outbound HTTP/HTTPS for updates and web access.

---

### ⛔ 4. Custom Firewall Outbound Firewall Blocking Rules

To enhance security, I created outbound rules to block potentially unsafe or legacy protocols.
  
  📂 `Computer Configuration > Policies > Windows Settings > Security Settings > Windows Defender Firewall with Advanced Security > Outbound Rules`

### 🚫 Block TFTP

   * __Rule Type:__ Port
   * __Protocol:__ UDP
   * __Remote Port:__ 69
   * __Action:__ Block the connection
   * __Profiles:__ All (Domain, Private, Public)
   * __Name:__ Block TFTP UDP
   * __Description:__ Blocks insecure TFTP connections.

### 🚫 Block Telnet

   * __Rule Type:__ Port
   * __Protocol:__ TCP
   * __Remote Port:__ 23
   * __Action:__ Block the connection
   * __Profiles:__ All (Domain, Private, Public)
   * __Name:__ Block Telnet TCP
   * __Description:__ Blocks insecure Telnet connections.

### 🚫 Block Unencrypted FTP

   * __Rule Type:__ Port
   * __Protocol:__ TCP
   * __Remote Port:__ 21
   * __Action:__ Block the connection
   * __Profiles:__ All (Domain, Private, Public)
   * __Name:__ Block Unencrypted FTP TCP
   * __Description:__ Blocks standard File Transfer Protocol (FTP) connections that transmit credentials and data without encryption, posing significant security risks. Port 21 TCP.

### 🚫 Block NetBIOS

   * __Rule Type:__ Port
   * __Protocol:__ TCP and UDP (separate rules)
   * __Remote Port:__ 137,138,139
   * __Action:__ Block the connection
   * __Profiles:__ All (Domain, Private, Public)
   * __Name:__ Block NetBIOS TCP, Block NetBIOS UDP
   * __Description:__ 
     - Blocks insecure NetBIOS over TCP
     - Blocks insecure NetBIOS over UDP

### 🚫 Block LLMNR

   * __Rule Type:__ Port
   * __Protocol:__ UDP
   * __Remote Port:__ 5355
   * __Action:__ Block the connection
   * __Profile:__ All (Domain, Private, Public)
   * __Name:__ Block LLMNR UDP
   * __Description:__ Blocks Link-Local Multicast Name Resolution.

---

## 4. Configured the following profiles:

### 🌐 Domain Profile
- Firewall state: **On**
- Inbound connections: **Block**
- Outbound connections: **Allow**
- Logging: Enabled with custom path

### 🏠 Private Profile
- Firewall state: **On**
- Inbound connections: **Block**
- Outbound connections: **Allow**
- Logging: Enabled with custom path

### 🌍 Public Profile
- Firewall state: **On**
- Inbound connections: **Block all**
- Outbound: **Allow** (with stricter rules)
- Prevent local exceptions

---

## 🚀 4. Applying and Testing the Policy

I closed the Group Policy Management Editor
- On each client computer, I ran the following command:

  `gpupdate /force`
  
- Then I restarted the clients to ensure the policy was fully applied
- I tested connectivity between the domain controller and the clients

---

### 🧪 5. Testing Firewall Behavior

- On client computers, I opened Command Prompt as administrator and ran:

  `gpresult /r`
  
  `netsh advfirewall show allprofiles` to verify firewall rules were active

  `ping 192.168.1.10` to check basic connectivity
  
  `nslookup hughdomain.local` to check basic connectivit

- On client computers, I made sure to check that domain controller discovery works, group policy updates successfully as well as group policy results show firewall policy applied by opening Command Prompt as administrator and running:

  `nltest /dsgetdc:cloud.com`

  `gpupdate /force`

  `gpresult /r`

- On client computers, I made sure to check that access to SYSVOL share, NETLOGON share is available as well as authentication to domain is possible by opening Command Prompt as administrator and running:

  `net use \\domain-controller\sysvol`
  
  `net use \\domain-controller\netlogon`

- On client computers, I made sure to check that RDP connection was successful, WinRM commands execute successfully, as well as No firewall blocking messages appeared by opening Command Prompt as administrator and running:

  `mstsc /v:10.221.1.10`
  
  `winrs -r:10.221.1.10 ipconfig

- On client computers, I made sure to check that Time services showed valid sync source, as well as Manual resync works without errors by opening Command Prompt as administrator and running:

  `w32tm /query /status`
  
  `w32tm /resync`

- On a domain controller, I opened Command Prompt as administrator and ran:

   `ping 10.221.1.11` to check basic connectivity

  `ping 10.221.1.12` to check basic connectivity
  
   `nslookup AD-WIN10-01`  to check basic connectivity

   `nslookup AD-WIN10-02`  to check basic connectivity

---

## 🛠️ 6. Troubleshooting Tips

- Temporarily disabled the firewall to determine if it was blocking connectivity
- Used `rsop.msc` to confirm policy inheritance on client machines
- Checked **Event Viewer** for related errors
- Ran:
  `netsh advfirewall monitor show firewall rule name=all`
- To see all applied firewall rules and check for any misconfiguration

---

## 🗂️ 7. Screenshot Storage

All screenshots for this section can be found in:<br />
📂 [`06-Screenshots/XXVII. Windows-Firewall`](https://github.com/Hugh-Kumbi/Hugh-Kumbi-Active-Directory-Lab/tree/main/06-Screenshots/XXVII.%20Windows-Firewall)
