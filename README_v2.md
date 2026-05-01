# Windows Server File Server with Access Control

## Overview
This project demonstrates how to configure a File Server on Windows Server and implement secure access control using Active Directory, Organizational Units (OUs), Groups, and NTFS/Share permissions.

The setup simulates a real-world enterprise environment where different departments have restricted access to specific folders.


## Objectives
- Set up a file server on Windows Server  
- Create users and Organizational Units (OUs)  
- Implement group-based access control  
- Configure folder sharing and permissions  
- Test access restrictions  


## Technologies Used
- Windows Server 2022  
- Active Directory Users and Computers (ADUC)  
- NTFS Permissions  
- Windows 11  


## Architecture Overview
- Server: Hosts shared folders and manages permissions  
- Active Directory: Manages users, groups, and OUs  
- Client Machine: Used for testing access  


## Step 1: Create File Structure

<p align="center">
1.0<img src="https://github.com/Marinus-Bakara/windows-file-server-and-permissions/blob/main/images/1.%20i%20created%20a%20folder%20named%20company%20data%20in%20windows%20server%20drive%20C.png" width="600"/>
  I created a folder named company data in windows server drive C.
</p>

<p align="center">
1.1<img src="https://github.com/Marinus-Bakara/windows-file-server-and-permissions/blob/main/images/2.i%20created%20these%20subfolders%20in%20companies%20data%20which%20we%20will%20use%20to%20give%20to%20users%20on%20how%20to%20access%20them.png" width="600"/>
  I created subfolders in companies data which, we will use to give to users permissions on how to access them.
</p>



##  Step 2: Active Directory Setup

<p align="center">
2.0<img src="images/3.we will open the server manager,click on tools and click on active directory users and computers.png" width="600"/>
We will open the server manager,click on tools and click on active directory users and computers
</p>

<p align="center">
 2.1 <img src="images/4.am going to create OU's according to the subfolders i created earlier,by creating the OU, you right click on the domain you created which mine is test.com .png" width="600"/>
Am going to create OU's according to the subfolders i created earlier,by creating the OU, you right click on the domain you created which mine is test.com
</p>

<p align="center">
 2.2 <img src="https://github.com/Marinus-Bakara/windows-file-server-and-permissions/blob/main/images/5AFTER~1.PNG" width="600"/>
After clicking on the Organisational unit ,a window shows for you to enter the OU name ,and select protection of contain from accident deletion,and we are creating  ou for all the three subfolders we created earlier using these same steps.
</p>

<p align="center">
  <img src="images/6.this is how it is after creating all th OU's.png" width="600"/>
This is how it is after creating all th OU's.
</p>


## 👤 Step 3: Create Users

<p align="center">
3.0 <img src="images/7.we are going to create new three new users under each OU..png" width="600"/>
We are going to create new three new users under each OU.
</p>

<p align="center">
3.1<img src="images/8.after selecting the you would be asked to enter the details of the user.png" width="600"/>
After selecting the you would be asked to enter the details of the user
</p>

<p align="center">
3.2<img src="https://github.com/Marinus-Bakara/windows-file-server-and-permissions/blob/main/images/9AFTER~1.PNG" width="600"/>
After entering the detials you be asked to enter the password for the user,and industry wise you have to select the option user must chande password at next login this enables the person to enter his or her own password
</p>

## Step 4: Groups Configuration

<p align="center">
4.0<img src="images/10.i will create groups an name them according the subfolders we created earlier,and you will add the user to the groups.png" width="600"/>
I will create groups and name them according the subfolders we created earlier,we you will add the user to the groups.
</p>

<p align="center">
 4.1<img src="images/11.am putting all the users we created under OU HR to the HR Group i created,and going to di for all of them.png" width="600"/>
Am putting all the users we created under OU HR to the HR Group i created,and going to do for all of them.
</p>

<p align="center">
4.2<img src="images/12.you have to enter the name of the group and click on ok.png" width="600"/>
We have to enter the name of the group and click on ok
</p>

##  Step 5: Permissions Configuration

<p align="center">
5.0<img src="https://github.com/Marinus-Bakara/windows-file-server-and-permissions/blob/main/images/13WEWA~1.PNG" width="600"/>
We want to share the folder with the HR group and give them permissions on only modify.in doing that we will right click on the HR folder and select properties and sharing and click on advanced sharing accept the permissions
</p>

<p align="center">
5.1<img src="images/14. we will click on add to add the HR group.png" width="600"/>
We will click on add to add the HR group
</p>

<p align="center">
5.2<img src="images/15.am giving the HR group to permission to read and change.png" width="600"/>
Am giving the HR group to permission to read and change
</p>


## 🚫 Step 6: Security Configuration

<p align="center">
  <img src="images/16.we have to disable inheritance to prevent other departments from seeing the HR folder..png" width="600"/>
</p>

<p align="center">
  <img src="images/17.we have to select the first option to store the setting.png" width="600"/>
</p>

<p align="center">
  <img src="images/18.we would now click on share.png" width="600"/>
</p>

---

## 🧪 Step 7: Testing

<p align="center">
  <img src="images/19.we are going to use one of these users to access HR folder using a windows 11 machine.png" width="600"/>
</p>

<p align="center">
  <img src="images/20.we are loging in using the user name mari.png" width="600"/>
</p>

<p align="center">
  <img src="images/21.we paste the folder path to see whether the user in the HR department can access it.png" width="600"/>
</p>

<p align="center">
  <img src="images/22.after that we map it to a drive for easy access.png" width="600"/>
</p>

### ❌ Unauthorized Access
<p align="center">
  <img src="images/23.i logged into the win 11 using a user under IT group to access the HR folder and this is the message that was given meaning the settings we did are working properly.png" width="600"/>
</p>

---

## 📊 Results
- Access control worked as expected  
- Authorized users gained access  
- Unauthorized users were denied  

---

## 🔐 Security Best Practices
- Group-based permission assignment  
- Least privilege principle  
- Disabled inheritance to protect sensitive folders  

---

## 🚀 Future Improvements
- Integrate with monitoring tools like Wazuh  
- Enable auditing and logging  
- Expand to domain-wide deployment  

---

## 👤 Author
Marinus Bakara  
Email: bakaramarinus3@gmail.com  
