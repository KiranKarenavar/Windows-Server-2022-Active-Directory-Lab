# 🧑‍💻 User Environment Management

## 📘 Overview

This section of the Active Directory Lab focuses on configuring and managing user environments using Group Policy Objects (GPOs). It encompasses folder redirection, drive mappings, logon/logoff scripts, desktop wallpaper settings, and restrictions on Control Panel and Settings access. These configurations aim to streamline user experiences, enhance data security, and ensure consistency across the domain environment.

---

## 🧰 1. Folder Redirection

### 📝 Description

Implemented folder redirection to redirect user profile folders **(i.e., Desktop, Documents, Pictures, Favourites, Contacts, Downloads, Links & Searches)** to network locations. This ensures that user data is stored centrally, facilitating easier backups and data management.

### 🛠️ Group Policy Settings Applied

- **Redirected Folders:**

  - **Desktop:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Desktop`
 
📸 **Desktop Folder Redirection Configuration**
  
<img width="1920" height="909" alt="Root Path Entered for Desktop Redirection1" src="https://github.com/user-attachments/assets/abd947bb-1a3a-4a2d-9565-c1224a148a01" /><br />

  - **Desktop:** Redirected to `\\WINSERVER2022\FileShares\...\Desktop`

📸 **Desktop User Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Desktop Redirection" src="https://github.com/user-attachments/assets/e7675e62-c3cb-486c-8675-b6b2a975f14b" /><br />

  - **Documents:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Documents`
 
  📸 **Documents Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Documents Redirection 1" src="https://github.com/user-attachments/assets/b628c8db-8bfb-4d78-8394-a54b3d9160dc" /><br />

  - **Documents:** Redirected to `\\WINSERVER2022\FileShares\...\Documents`

📸 **Documents User Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Documents Redirection" src="https://github.com/user-attachments/assets/5be97ba4-34e3-497c-b4b6-23853ffbba4f" /><br />

  - **Pictures:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Pictures`
 
  📸 **Pictures Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Pictures Redirection 1" src="https://github.com/user-attachments/assets/0e2e8701-c539-4604-ae7b-b420093cdeb1" /><br />

  - **Pictures:** Redirected to `\\WINSERVER2022\FileShares\...\Pictures`

📸 **Pictures User Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Pictures Redirection" src="https://github.com/user-attachments/assets/6f6e6275-9bf2-4806-9a16-f7f9f6195a89" /><br />

  - **Start Menu:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Start Menu`
 
📸 **Start Menu Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Start Menu Redirection 1" src="https://github.com/user-attachments/assets/c1374b38-b4f5-4b5b-89b1-37295dcc6dfb" /><br />

  - **Start Menu:** Redirected to `\\WINSERVER2022\FileShares\...\Start Menu`

📸 **Start Menu User Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Start Menu Redirection" src="https://github.com/user-attachments/assets/a10471c8-cfc3-4740-a094-0d63eb365f52" /><br />

  - **Music:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Music`
  
  📸 **Music Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Music Redirection 1" src="https://github.com/user-attachments/assets/2dddd00b-a65a-4201-a1f5-cc42004d46c5" /><br />

   - **Music:** Redirected to `\\WINSERVER2022\FileShares\...\Music` 

📸 **Music User Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Music Redirection" src="https://github.com/user-attachments/assets/35fee43e-e183-42bc-bc1c-63b8250d2245" /><br />

   - **Videos:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Videos` 
 
  📸 **Videos Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Videos Redirection 1" src="https://github.com/user-attachments/assets/75110013-3712-40da-b08a-263dcf02b241" /><br />

  - **Videos:** Redirected to `\\WINSERVER2022\FileShares\...\Videos`

📸 **Videos User Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Videos Redirection" src="https://github.com/user-attachments/assets/9e69fab2-2ded-499e-8cf1-2ab8acb0ed67" /><br />

  - **Contacts:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Contacts`
 
📸 **Contacts Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Contacts Redirection 1" src="https://github.com/user-attachments/assets/49bfac85-370f-4e3e-a8f9-5c686b26ba59" /><br />
 
  - **Contacts:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Contacts`

📸 **Contacts User Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Contacts Redirection" src="https://github.com/user-attachments/assets/7da8ee8b-968f-4838-b36b-bb48dc153651" /><br />

  - **Links:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Links`

📸 **Links Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Links Redirection" src="https://github.com/user-attachments/assets/0bb969a3-6004-4000-a90d-ce8770dce66c" /><br />

  - **Searches:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Searches`

📸 **Searches Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Searches Redirection" src="https://github.com/user-attachments/assets/b69f72ab-d45f-43f9-bbf3-586a5c39005f" /><br />

  - **Downloads:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Downloads`

📸 **Downloads Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Downloads Redirection1" src="https://github.com/user-attachments/assets/84bdde99-3d03-43c4-87d4-5be2d12512fb" /><br />

  - **Downloads:** Redirected to `\\WINSERVER2022\FileShares\...\Downloads`

📸 **Downloads User Folder Redirection Configuration**

<img width="1920" height="909" alt="Root Path Entered for Downloads Redirection" src="https://github.com/user-attachments/assets/e5224464-4b82-4d45-84e3-d9b2bca504ee" />

- **Settings:**
  - Enabled offline files for redirected folders to allow access during network outages.
  - Configured redirection to follow the user across different computers within the domain.
  
### Paths Redirected

- `\\WINSERVER2022\FolderRedirection$`
- `\\WINSERVER2022\FileShares`

📸 **Group Policy Management Console Showing The Folder Redirection Policy Link to Domain**

<img width="1920" height="909" alt="Group Policy Management Console Showing the Folder Redirection Policy GPO and Link to the ITSecurity OU" src="https://github.com/user-attachments/assets/c086dc0a-f8de-4455-b964-0125932a45ce" /><br />

<img width="1920" height="909" alt="Group Policy Management Console Showing the Folder Redirection Policy GPO and Link to the Employees OU" src="https://github.com/user-attachments/assets/f8ad48a3-c9dd-4c3d-b7f3-cb3a9c537e5f" /><br />

These settings are detailed in the [`I. Folder-Redirection Settings`](https://github.com/Hugh-Kumbi/Hugh-Kumbi-Active-Directory-Lab/blob/main/08-User-Environment-Management/I.%20User%20Folder-Redirection%20Settings.md) and [`II. Folder-Redirection Properties`](https://github.com/Hugh-Kumbi/Hugh-Kumbi-Active-Directory-Lab/blob/main/08-User-Environment-Management/II.%20Folder-Redirection%20Properties.md) files.

---

## 🖼️ 5. Desktop Wallpaper Policy

### 📝 Description

I enforced a corporate desktop background to maintain a consistent visual identity and prevent inappropriate or distracting wallpapers. Standardising the desktop appearance enhances corporate branding and user experience.

### 🛠️ Group Policy Preferences Applied

- Stored the desired wallpaper image on a shared network location accessible by all users.
- **UNC Path to Wallpaper:** `\\WIN-D2PQBCI88JQ\Users\Wallpaper\MEIVAULT SYSTEMS LOGO.png`    
- Created a GPO and navigated to:
  📂 `User Configuration > Policies > Administrative Templates > Desktop > Desktop`
- Enabled the **Desktop Wallpaper Policy** and specified the UNC path to the wallpaper image.

  📸 **Desktop Wallpaper Policy Enabling Prevent changing desktop background**

  ![Desktop Wallpaper Policy Recreation Settings Path](https://github.com/user-attachments/assets/0c8ddc53-c182-4732-a549-7412ce3bff2a)

- Set the wallpaper style to "Fit" to ensure proper scaling across different screen resolutions.
- Enabled the **Prevent changing desktop background** policy to restrict users from altering the wallpaper:
  📂 `User Configuration > Administrative Templates > Control Panel > Personalization`

  📸 **Desktop Wallpaper Policy Enabling Prevent changing desktop background**
  
  ![Desktop Wallpaper Policy Recreation Contol Panel Settings Path](https://github.com/user-attachments/assets/d69d2223-622f-457b-8bbc-ab9a0dd7e4a8)

- Applied the GPO to the appropriate OUs containing user accounts.
- Forced a Group Policy update using `gpupdate /force` and verified the wallpaper application on client machines.

📸 **Desktop Wallpaper Policy Linked to Tech OU**

![Desktop Wallpaper Policy Linked to Tech OU](https://github.com/user-attachments/assets/63096489-2aad-4081-8845-d42a2ac94843)

📸 **Desktop Wallpaper Policy Implemented Successfully**

![Changed Wall Paper](https://github.com/user-attachments/assets/20190256-7d77-4f36-b1fd-a8ca3c32fb07)

Configuration details are provided in the `VIII. Desktop Wallpaper Policy.md`.

---

## 🚫 6. Control Panel & Settings Restrictions

### 📝 Description

To reduce risk and accidental misconfigurations, I restricted access to the Control Panel and selected system settings. This policy enhances security and prevents unauthorized system changes by restricting user access to the Control Panel and Settings app.

### 🛠️ Group Policy Preferences Applied

- Prevent access to Control Panel and PC Settings
- Hide specific Control Panel items (e.g., Network Settings)
- Created a GPO and navigated to:
  📂 `User Configuration > Policies > Administrative Templates > Control Panel`
- Enabled the **Prohibit access to Control Panel and PC settings** policy to block access entirely.

📸 **Prohibit Access to Control Panel and PC settings**

![Prohibit Access to Control Panel and PC settings](https://github.com/user-attachments/assets/b6ebe29c-a88d-40dd-9eac-2f9de66fe1a0)

- Enabled the Show only specified Control Panel items policy.

📸 **Control Panel Restrictions Showing Only Specified Control Panel Items**
  
![Control Panel Restrictions Showing Only Specified Control Panel Items](https://github.com/user-attachments/assets/72b81a45-4fe8-44c9-877a-bbe60c637446)

- Entered the canonical names of items to be shown (e.g., Microsoft.Personalization and Microsoft.Fonts).
- Referenced Microsoft's list of canonical names for accuracy.
- Applied the GPO to Tech OU.
- Verified the restrictions by attempting to access the Control Panel and Settings app on client machines.

📸 **Control Panel Restrictions Policy Linked to Tech OU**

![Control Panel Restrictions Policy Linked to Tech OU](https://github.com/user-attachments/assets/54e6a4b3-db5b-4674-b387-5961684030a6)

📸 **Control Panel Restrictions Showing disallowed Control Panel Items**

![Control Panel Restrictions Policy 1](https://github.com/user-attachments/assets/fa9264c7-7440-40eb-b34c-4b037c7acef2)

📸 **Control Panel Restrictions Policy Implemented Successfully**

![Control Panel Restrictions](https://github.com/user-attachments/assets/5e38fcf2-69cf-4d0c-8106-8b7d624f39fc)

![Control Panel Restrictions Policy 2](https://github.com/user-attachments/assets/18760da3-914e-43cb-8f81-afafe8ffe9db)

Configuration details are provided in the `IX. Control Panel Restrictions Policy.md`.

---

## ✅ 7. Verification

- Logged into test user accounts and confirmed policies were applied.
- Checked drive mappings, desktop background, Control Panel restrictions, and folder redirection behavior.
- Used `gpresult /H report.html` and Event Viewer for policy status.

---

## 📂 8. Files Included

- `I. Desktop Wallpaper Policy.md`: Enforced a corporate desktop background.
- `II. Control Panel Restrictions Policy.md`: Configured restricted access to the Control Panel and selected system settings.
- `README.md`: This documentation file summarizing the configurations and their purposes.

## ✅ 9. Outcome

By implementing these configurations:
- **Enhanced User Experience:** Automated access to necessary resources and consistent desktop environments.
- **Improved Data Security:** Centralized storage of user data simplifies backups and reduces data loss risks.
- **Operational Efficiency:** Automated scripts reduce manual administrative tasks and enforce compliance.

## 📚 10. References

[Group Policy Overview](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/group-policy/group-policy-overview)

[Group Policy Management Console](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/group-policy/group-policy-management-console)

[Best Practices for Group Policy in Active Directory](https://learn.microsoft.com/en-us/answers/questions/1377673/best-practices-for-group-policy-in-active-director)

[Set Desktop Wallpaper using GPO - Microsoft Q&A](https://learn.microsoft.com/en-us/answers/questions/1053594/set-desktop-wallpaper-using-gpo)

[Restrict Control Panel Access using Group Policy](https://activedirectorypro.com/restrict-control-panel-access-using-group-policy/)

[Deploy Desktop Background Wallpaper using Group Policy](https://msftwebcast.com/2019/08/deploy-desktop-background-wallpaper-using-group-policy.html)

[Manage the Settings app with Group Policy - Microsoft Learn](https://learn.microsoft.com/en-us/windows/client-management/client-tools/manage-settings-app-with-group-policy)
