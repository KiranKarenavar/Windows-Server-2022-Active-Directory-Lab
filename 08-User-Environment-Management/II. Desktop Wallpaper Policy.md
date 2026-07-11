# 🖼️ Desktop Wallpaper Policy

This section explains how I implemented a **Desktop Wallpaper Policy** using Group Policy to enforce a consistent desktop background across all user machines in the domain. This helps standardize branding and minimizes distractions in a corporate environment.

---

## 🏷️ 1. GPO Name

- **GPO Name:** Desktop Wallpaper Policy  
- **Linked To:** cloud.com (domain root)

📸 **Group Policy Management Console Showing the Desktop Wallpaper Policy GPO and Link**

<img width="1920" height="909" alt="Group Policy Management Console Showing The Desktop Wallpaper Policy GPO And Link" src="https://github.com/user-attachments/assets/2a789e80-1c0e-4a51-863a-cc4b0c36e515" />

---

## 🛠️ 2. Policy Configuration Steps

1. Navigated to:  
   📂 `User Configuration > Policies > Administrative Templates > Desktop > Desktop`

2. Enabled the setting:  
   `Desktop Wallpaper`

3. Specified the path to the wallpaper image:  
   `\\WINSERVER2022\sysvol\cloud.com\Wallpaper`

4. Set wallpaper style to:  
   `Fit`

📸 **Desktop Wallpaper Policy Configuration**

![Desktop Wallpaper Policy Configuration](https://github.com/user-attachments/assets/1473f3c6-7899-43bd-8f99-9dae4492b0d1)

📸 **Wallpaper File Stored on Shared Server Folder**

![Wallpaper File Stored On Shared Server Folder](https://github.com/user-attachments/assets/890c8a57-539b-41aa-88a2-76e514230588)

---

## ✅ 3. Testing and Results

To test the policy:
1. Logged into a domain-joined client machine as a standard user.
2. Verified that the desktop wallpaper was automatically applied.
3. Attempted to change the wallpaper via settings — confirmed that the option was greyed out.

📸 **Wallpaper Automatically Applied on User Login for `WinServer2022`**

![Wallpaper Automatically Applied On User Login for `WinServer2022`](https://github.com/user-attachments/assets/63a10f3c-e189-4260-911a-472771518e45)

📸 **Wallpaper Automatically Applied on User Login for `AD-WIN10-01`**

![Wallpaper Automatically Applied On User Login for `AD-WIN10-01`](https://github.com/user-attachments/assets/5bde3ac8-a33d-4495-8357-41ce4ba9e9e3)

📸 **Wallpaper Automatically Applied on User Login for `AD-WIN10-02`**

![Wallpaper Automatically Applied On User Login for `AD-WIN10-02`](https://github.com/user-attachments/assets/000b6da9-9c48-47ff-bc7e-3f63d2e0506a)

---

## 🗂️ 4. Screenshot Storage

All screenshots for this section can be found in:<br />
📂 [`06-Screenshots/XXV. Desktop Wallpaper Policy`](https://github.com/Hugh-Kumbi/Hugh-Kumbi-Active-Directory-Lab/blob/main/06-Screenshots/XXV.%20Desktop%20Wallpaper%20Policy/README.md)
