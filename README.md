# Windows File Server & Active Directory Permission Management

This project demonstrates how to configure a File Server on Windows Server and implement secure access control using Active Directory, Organizational Units (OUs), Groups, and NTFS/Share permissions. The setup simulates a real-world enterprise environment where different departments have restricted access to specific folders.


---

## Overview

This project sets up a centralized file server where different departments (HR, Finance, IT) can only access their designated folders. Access control is enforced through Active Directory groups and NTFS permissions, with share-level permissions acting as a secondary layer. The setup was verified by logging in as users from different departments to confirm that authorized users gain access and unauthorized users are denied.

---
## Architecture Overview
- Server: Hosts shared folders and manages permissions  
- Active Directory: Manages users, groups, and OUs  
- Client Machine: Used for testing access  
---

## Objectives

- Set up a file server on Windows Server
- Create users and Organizational Units (OUs)
- Implement group-based access control
- Configure folder sharing and NTFS permissions
- Test and verify access restrictions between departments

---

## Technologies Used

- Windows Server 2025
- Active Directory Users and Computers (ADUC)
- NTFS Permissions
- SMB File Sharing
- Windows 11 (client testing)

---

## Step 1: Create the Folder Structure

**1.0 — Create the root folder on drive C**

<img src="https://github.com/Marinus-Bakara/windows-file-server-and-permissions/blob/main/images/1.%20i%20created%20a%20folder%20named%20company%20data%20in%20windows%20server%20drive%20C.png" width="600"/>

A folder named **CompanyData** was created on the Windows Server drive C. This will serve as the root directory for all department folders.

---

**1.1 — Create department subfolders inside CompanyData**

<img src="https://github.com/Marinus-Bakara/windows-file-server-and-permissions/blob/main/images/2.i%20created%20these%20subfolders%20in%20companies%20data%20which%20we%20will%20use%20to%20give%20to%20users%20on%20how%20to%20access%20them.png" width="600"/>

Subfolders were created inside CompanyData — one for each department. These folders will later have separate permissions assigned to restrict access by department.

---

## Step 2: Active Directory Setup

**2.0 — Open Active Directory Users and Computers**

<img src="images/3.we will open the server manager,click on tools and click on active directory users and computers.png" width="600"/>

Open **Server Manager**, click on **Tools**, then select **Active Directory Users and Computers**.

---

**2.1 — Create Organizational Units (OUs)**

<img src="images/4.am going to create OU's according to the subfolders i created earlier,by creating the OU, you right click on the domain you created which mine is test.com .png" width="600"/>

OUs are created to match the department subfolders created earlier. To create an OU, right-click on your domain (in this case `test.com`) and select **New → Organizational Unit**.

---

**2.2 — Enter the OU name and enable protection**

<img src="https://github.com/Marinus-Bakara/windows-file-server-and-permissions/blob/main/images/5AFTER~1.PNG" width="600"/>

After clicking **Organizational Unit**, a dialog box appears. Enter the OU name and check the option to **protect the container from accidental deletion**. Repeat this process to create OUs for all three departments.

---

**2.3 — All OUs created**

<img src="images/6.this is how it is after creating all th OU's.png" width="600"/>

This shows how the Active Directory structure looks after all three Organizational Units have been created.

---

## Step 3: Create Users

**3.0 — Create users under each OU**

<img src="images/7.we are going to create new three new users under each OU..png" width="600"/>

Three new users will be created under each OU. Right-click the OU and select **New → User**.

---

**3.1 — Enter user details**

<img src="images/8.after selecting the you would be asked to enter the details of the user.png" width="600"/>

After selecting **New User**, a form appears where you fill in the user's first name, last name, and login name.

---

**3.2 — Set the user password**

<img src="https://github.com/Marinus-Bakara/windows-file-server-and-permissions/blob/main/images/9AFTER~1.PNG" width="600"/>

After entering the user details, you will be prompted to set a password. It is best practice to select **User must change password at next login** so that each user sets their own password on first login.

---

## Step 4: Create and Configure Groups

**4.0 — Create security groups for each department**

<img src="images/10.i will create groups an name them according the subfolders we created earlier,and you will add the user to the groups.png" width="600"/>

Security groups are created and named to match the department subfolders (e.g. HR-Group, Finance-Group, IT-Group). Users will then be added to their respective groups.

---

**4.1 — Add users to their department group**

<img src="images/11.am putting all the users we created under OU HR to the HR Group i created,and going to di for all of them.png" width="600"/>

All users created under the HR OU are added to the HR-Group. The same process is repeated for Finance and IT.

---

**4.2 — Enter the group name to add members**

<img src="images/12.you have to enter the name of the group and click on ok.png" width="600"/>

When adding members, type the name of the group in the dialog box and click **OK** to confirm.

---

## Step 5: Configure Folder Permissions

**5.0 — Open folder properties and configure sharing**

<img src="https://github.com/Marinus-Bakara/windows-file-server-and-permissions/blob/main/images/13WEWA~1.PNG" width="600"/>

To share the HR folder with the HR-Group, right-click the HR folder, select **Properties → Sharing → Advanced Sharing**, and proceed to configure the permissions.

---

**5.1 — Add the HR-Group to the share permissions**

<img src="images/14. we will click on add to add the HR group.png" width="600"/>

Click **Add** to add the HR-Group to the folder's share permissions.

---

**5.2 — Grant Read and Change permissions to the HR-Group**

<img src="images/15.am giving the HR group to permission to read and change.png" width="600"/>

The HR-Group is granted **Read** and **Change** permissions, allowing members to view and modify files within the HR folder.

---

## Step 6: Security Configuration

**6.0 — Disable inheritance on the HR folder**

<img src="images/16.we have to disable inheritance to prevent other departments from seeing the HR folder..png" width="600"/>

Inheritance is disabled on the HR folder to prevent users from other departments from accessing it through inherited parent permissions.

---

**6.1 — Convert inherited permissions to explicit permissions**

<img src="images/17.we have to select the first option to store the setting.png" width="600"/>

When disabling inheritance, select the first option — **Convert inherited permissions into explicit permissions** — to retain the existing settings as standalone rules.

---

**6.2 — Share the folder**

<img src="images/18.we would now click on share.png" width="600"/>

Click **Share** to finalize the sharing configuration for the folder.

---

## Step 7: Testing Access

**7.0 — Select a test user from the HR department**

<img src="images/19.we are going to use one of these users to access HR folder using a windows 11 machine.png" width="600"/>

One of the HR department users is selected to test access to the HR folder from a Windows 11 machine.

---

**7.1 — Log in as the test user (mari)**

<img src="images/20.we are loging in using the user name mari.png" width="600"/>

Login is performed on the Windows 11 machine using the HR user account **mari**.

---

**7.2 — Test folder access by pasting the network path**

<img src="images/21.we paste the folder path to see whether the user in the HR department can access it.png" width="600"/>

The shared folder path is pasted into File Explorer to test whether the HR user can successfully access the HR folder.

---

**7.3 — Map the folder to a drive letter**

<img src="images/22.after that we map it to a drive for easy access.png" width="600"/>

The shared HR folder is mapped to a drive letter for convenient, persistent access by department users.

---

**7.4 — Unauthorized access attempt (IT user trying to open HR folder)**

<img src="images/23.i logged into the win 11 using a user under IT group to access the HR folder and this is the message that was given meaning the settings we did are working properly.png" width="600"/>

An IT department user attempts to access the HR folder. The **Access Denied** message confirms that the permission settings are working correctly and cross-department access is blocked.

---

## Results

- Access control worked as expected
- Authorized users (HR members) successfully accessed the HR folder
- Unauthorized users (IT members) were denied access to the HR folder
- Mapped drives worked correctly for authorized users

---

> **Best practice:** Always use NTFS permissions for granular access control. Set share permissions broadly (Read for Everyone) and restrict at the NTFS level using AD security groups — never assign permissions directly to individual user accounts.

---

## Security Best Practices Applied

- Group-based permission assignment (no individual user permissions)
- Principle of least privilege — users only access what their role requires
- Inheritance disabled on sensitive folders to isolate department data
- Password policy enforces user-defined passwords at first login

---

## Future Improvements

- Integrate monitoring tools such as Wazuh for real-time alerts
- Enable Windows auditing and event logging for access tracking
- Expand the setup to a full domain-wide deployment
- Automate user and group creation using PowerShell scripts

---

## Author

**Marinus Bakara**  
Email: bakaramarinus3@gmail.com
