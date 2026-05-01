# 🚀 Windows Server File Server with Access Control

## 📌 Overview
This project demonstrates how to configure a File Server on Windows Server and implement secure access control using Active Directory, Organizational Units (OUs), Groups, and NTFS/Share permissions.

---

## 🎯 Objectives
- Set up a file server
- Create users and groups
- Assign permissions
- Test access control

---

## 🛠️ Technologies Used
- Windows Server 2022  
- Active Directory  
- NTFS Permissions  
- Windows 11  

---

## 🏗️ Architecture
- Server: Hosts shared folders  
- AD: Manages users/groups  
- Client: Tests access  

---

## 📂 Setup & Configuration

### Step 1: Create Main Folder
<p align="center">
  <img src="images/01-create-main-folder.png" width="600"/>
</p>

### Step 2: Create Subfolders
<p align="center">
  <img src="images/02-create-subfolders.png" width="600"/>
</p>

### Step 3: Open ADUC
<p align="center">
  <img src="images/03-open-aduc.png" width="600"/>
</p>

### Step 4: Create OUs
<p align="center">
  <img src="images/04-create-ou.png" width="600"/>
</p>

### Step 5: OU Setup
<p align="center">
  <img src="images/05-ou-setup.png" width="600"/>
</p>

### Step 6: OU Structure
<p align="center">
  <img src="images/06-ou-structure.png" width="600"/>
</p>

### Step 7: Create Users
<p align="center">
  <img src="images/07-create-users.png" width="600"/>
</p>

### Step 8: User Details
<p align="center">
  <img src="images/08-user-details.png" width="600"/>
</p>

### Step 9: Password Setup
<p align="center">
  <img src="images/09-set-password.png" width="600"/>
</p>

### Step 10: Create Groups
<p align="center">
  <img src="images/10-create-groups.png" width="600"/>
</p>

### Step 11: Add Users to Groups
<p align="center">
  <img src="images/11-add-users-to-groups.png" width="600"/>
</p>

### Step 12: Confirm Groups
<p align="center">
  <img src="images/12-confirm-group-selection.png" width="600"/>
</p>

### Step 13: Enable Sharing
<p align="center">
  <img src="images/13-enable-folder-sharing.png" width="600"/>
</p>

### Step 14: Add Permissions
<p align="center">
  <img src="images/14-add-group-permissions.png" width="600"/>
</p>

### Step 15: Assign Permissions
<p align="center">
  <img src="images/15-assign-permissions.png" width="600"/>
</p>

### Step 16: Disable Inheritance
<p align="center">
  <img src="images/16-disable-inheritance.png" width="600"/>
</p>

### Step 17: Apply Security Settings
<p align="center">
  <img src="images/17-apply-security-settings.png" width="600"/>
</p>

### Step 18: Share Folder
<p align="center">
  <img src="images/18-share-folder.png" width="600"/>
</p>

---

## 🧪 Testing

### Authorized Access
<p align="center">
  <img src="images/21-access-shared-folder.png" width="600"/>
</p>

### Unauthorized Access
<p align="center">
  <img src="images/23-access-denied-test.png" width="600"/>
</p>

---

## 📊 Results
- Authorized users accessed resources  
- Unauthorized users denied  
- Permissions worked correctly  

---

## 🔐 Security Best Practices
- Group-based permissions  
- Least privilege  
- Disabled inheritance  

---

## 🚀 Future Improvements
- Add monitoring (Wazuh)
- Enable auditing

---

## 👤 Author
Marinus Bakara
