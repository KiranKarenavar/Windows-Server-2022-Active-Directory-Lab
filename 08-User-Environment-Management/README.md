# 🧑‍💻 User Environment Management

## 📘 Overview

This section of the Active Directory Lab focuses on configuring and managing user environments using Group Policy Objects (GPOs). It encompasses folder redirection, drive mappings, logon/logoff scripts, desktop wallpaper settings, and restrictions on Control Panel and Settings access. These configurations aim to streamline user experiences, enhance data security, and ensure consistency across the domain environment.

---

## 🧰 Folder Redirection

### 📝 Description

Implemented folder redirection to redirect user profile folders **(i.e., Desktop, Documents, Pictures, Favourites, Contacts, Downloads, Links & Searches)** to network locations. This ensures that user data is stored centrally, facilitating easier backups and data management.

### 🛠️ Group Policy Settings Applied

- **Redirected Folders:**

  - **Desktop:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Desktop`
 
  - **Desktop:** Redirected to `\\WINSERVER2022\FileShares\...\Desktop`

  - **Documents:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Documents`

  - **Documents:** Redirected to `\\WINSERVER2022\FileShares\...\Documents`

  - **Pictures:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Pictures`

  - **Pictures:** Redirected to `\\WINSERVER2022\FileShares\...\Pictures`

  - **Start Menu:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Start Menu`

  - **Start Menu:** Redirected to `\\WINSERVER2022\FileShares\...\Start Menu`

  - **Music:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Music`

  - **Music:** Redirected to `\\WINSERVER2022\FileShares\...\Music` 

  - **Videos:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Videos` 

  - **Videos:** Redirected to `\\WINSERVER2022\FileShares\...\Videos`

  - **Contacts:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Contacts`
 
  - **Contacts:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Contacts`

  - **Links:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Links`

  - **Searches:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Searches`

  - **Downloads:** Redirected to `\\WINSERVER2022\FolderRedirection$\...\Downloads`

  - **Downloads:** Redirected to `\\WINSERVER2022\FileShares\...\Downloads`

- **Settings:**
  - Enabled offline files for redirected folders to allow access during network outages.
  - Configured redirection to follow the user across different computers within the domain.
  
### Paths Redirected

- `\\WINSERVER2022\FolderRedirection$`
- `\\WINSERVER2022\FileShares`

---

## ✅ Verification

- Logged into test user accounts and confirmed policies were applied.
- Checked drive mappings, desktop background, Control Panel restrictions, and folder redirection behavior.
- Used `gpresult /H report.html` and Event Viewer for policy status.

---

## 📂 Files Included

- `I. Desktop Wallpaper Policy.md`: Enforced a corporate desktop background.
- `II. Control Panel Restrictions Policy.md`: Configured restricted access to the Control Panel and selected system settings.
- `README.md`: This documentation file summarizing the configurations and their purposes.

## ✅ 9. Outcome

By implementing these configurations:
- **Enhanced User Experience:** Automated access to necessary resources and consistent desktop environments.
- **Improved Data Security:** Centralized storage of user data simplifies backups and reduces data loss risks.
- **Operational Efficiency:** Automated scripts reduce manual administrative tasks and enforce compliance.

## 🗂️ 4. Screenshot Storage

All screenshots for this section can be found in:<br />
📂 [`06-Screenshots/G-User-Environment-Management`](../06-Screenshots/G-User-Environment-Management)

