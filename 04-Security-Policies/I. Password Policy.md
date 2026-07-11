# 🔐 Password Policy (Domain GPO)

This document outlines the **Password Policy** implemented through Group Policy to enforce strong password requirements in the domain. Password policies are essential for reducing the risk of unauthorized access through weak credentials.

---

## 📛 1. GPO Name

- **GPO Name:** Password Policy
- **Linked to:** cloud.com (domain root)

This policy was created using the **Group Policy Management Console (GPMC)** and linked at the domain level to ensure that it applies uniformly to all domain user accounts.

📸 **GPMC Showing the Domain Password Policy GPO**

<img width="1920" height="909" alt="GPMC Showing the Domain Password Policy GPO" src="https://github.com/user-attachments/assets/7a68f83e-b007-48d5-869a-512a18f7316b" />

---

## ⚙️ 2. Policy Settings

The following settings were configured under:<br />
📂 `Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Password Policy`

| Setting                                         | Value                   |
|-------------------------------------------------|-------------------------|
| **Enforce password history**                    | 24 passwords remembered |
| **Maximum password age**                        | 90 days                 |
| **Minimum password age**                        | 30 day                   |
| **Minimum password length**                     | 12 characters           |
| **Password must meet complexity requirements**  | Enabled                 |
| **Store passwords using reversible encryption** | Disabled                |

These settings ensure users cannot reuse old passwords frequently, must use complex and lengthy passwords, and cannot store passwords insecurely.

📸 **Group Policy Editor Window Showing the Password Policy Path**

<img width="1920" height="909" alt="Group Policy Editor Window Showing the Password Policy Path" src="https://github.com/user-attachments/assets/6c979a92-4794-418f-a77a-1f8f1a4be9d7" />

---

## 📌 3. Purpose and Justification

### 🛡️ Why These Settings?

- **Password history** prevents reuse of recently used passwords.
- **Expiration** ensures users periodically change their passwords.
- **Complexity requirements** force users to use a mix of characters.
- **Minimum length** increases entropy and password strength.
- **Reversible encryption** is disabled to avoid plaintext storage.

These settings align with best practices and compliance requirements such as NIST and CIS Benchmarks.

---

## ✅ 4. Testing and Validation

Logged into a test account and attempted to change the password using a weak one — blocked by GPO.
- Verified GPO application using:
```powershell
gpresult /r
```
- Checked rsop.msc (Resultant Set of Policy) to confirm applied settings.

📸 **`gpresult` Showing Password Policy Application for `AD-WIN10-01`**

![`gpresult` Showing Password Policy Application for `AD-WIN10-01`](https://github.com/user-attachments/assets/b8efa2b6-49ee-4456-9005-432ae51312c1)

![`gpresult` Showing Password Policy Application for `AD-WIN10-01` 1](https://github.com/user-attachments/assets/05f7ce83-918e-4594-b4e0-d9689c050eee)

📸 **`gpresult` Showing Password Policy Application for `AD-WIN10-02`**

![presult` Showing Password Policy Application for `AD-WIN10-02`](https://github.com/user-attachments/assets/86ad4f47-f523-456c-92e5-2a85fd19ec3e)

![presult` Showing Password Policy Application for `AD-WIN10-02` 1](https://github.com/user-attachments/assets/3f5a2733-3c40-4425-9347-40b7e822cba5)

📸 **Resultant Set of Policy**

<img width="1920" height="909" alt="Resultant Set of Policy for Password Policy" src="https://github.com/user-attachments/assets/abb5311c-ddb0-4985-94be-d3ea773f98dc" />

---

## 📁 5. Screenshot Storage

All screenshots for this section can be found in:<br />
📂 [`06-Screenshots/XI. Password Policy`](https://github.com/Hugh-Kumbi/Hugh-Kumbi-Active-Directory-Lab/tree/main/06-Screenshots/XI.%20Password%20Policy)
