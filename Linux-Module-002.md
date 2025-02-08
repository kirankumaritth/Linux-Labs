---

# **Linux Lab 2: Users, Groups, Files, Directories, and Permissions**  

---

## **1. User Management Commands**  

User management in Linux involves creating, modifying, and deleting users while managing their access and permissions. The following commands are commonly used for user management:

### **1.1 Listing Users**  
The `/etc/passwd` file contains user account information. Use the following command to list all users:
```bash
cat /etc/passwd
```

### **1.2 Creating a User**  
To create a new user, use the `adduser` command:
```bash
sudo adduser sagar
```
```
sudo adduser adam
```
This will prompt for a password and additional details.

### **1.3 Setting/Changing a User Password**  
To set or change a password for a user:
```bash
sudo passwd sagar
```

### **1.4 Checking User Information**  
To check user ID (UID), group ID (GID), and group memberships:
```bash
id sagar
```

### **1.5 Displaying Currently Logged-in Users**  
The `who` command lists currently logged-in users:
```bash
who
```

### **1.6 Switching to Another User**  
To switch to another user session:
```bash
su - sagar
```

### **1.7 Granting sudo Privileges to a User**  
If a user is not allowed to execute sudo commands, an administrator must grant access:
```bash
sudo usermod -aG sudo sagar
```

### **1.8 Viewing Last Login Information of a User**  
To check the last login history of a user:
```bash
last sagar
```

### **1.9 Deleting a User**  
To remove a user from the system:
```bash
sudo deluser adam
```

---

## **2. Group Management Commands**  

Linux groups help organize users and manage permissions efficiently. Below are essential commands for managing groups.

### **2.1 Listing Groups**  
To view all groups on the system:
```bash
cat /etc/group
```

### **2.2 Creating a Group**  
To create a new group:
```bash
sudo groupadd mygroup
```

### **2.3 Adding a User to a Group**  
To add a user to an existing group:
```bash
sudo usermod -aG mygroup sagar
```

### **2.4 Checking a User's Group Membership**  
To check which groups a user belongs to:
```bash
groups sagar
```

### **2.5 Changing a User's Primary Group**  
To change the primary group of a user:
```bash
sudo usermod -g mygroup sagar
```

### **2.6 Removing a User from a Group**  
(Note: A user cannot be removed from their primary group; they must belong to at least one group.)
```bash
sudo gpasswd -d sagar mygroup
```

### **2.7 Renaming a Group**  
To rename an existing group:
```bash
sudo groupmod -n newgroup mygroup
```

### **2.8 Deleting a Group**  
To delete a group, ensure it is not a user's primary group:
```bash
sudo groupdel newgroup
```
If you get an error stating **"cannot remove the primary group of user 'sagar'"**, change the user's primary group first:
```bash
sudo usermod -g sagar sagar
```
```
sudo groupdel newgroup
```
Verify the deletion:
```bash
getent group newgroup
```

---

## **3. File and Directory Management**  

### **3.1 Checking Current Directory**  
To display the present working directory:
```bash
pwd
```

### **3.2 Listing Files and Directories**  
To list files and directories with details:
```bash
ls -l
```

### **3.3 Creating a New Directory**  
To create a directory:
```bash
mkdir DemoDirectory
```

### **3.4 Navigating Between Directories**  
To move between directories:
```bash
cd DemoDirectory
```

### **3.5 Creating an Empty File**  
To create an empty file:
```bash
touch DemoFile.txt
```

### **3.6 Copying a File to Another Location**  
```bash
cp DemoFile.txt /home/kiran/Desktop
```

### **3.7 Moving/Renaming a File**  
```bash
mv DemoFile.txt TestFile.txt
```

### **3.8 Deleting a File**  
```bash
rm TestFile.txt
```

### **3.9 Deleting a Directory**  
```bash
cd ~
```
```
rm -r DemoDirectory
```
```
ls
```

---

## **4. Viewing and Editing Files**  

### **4.1 Viewing File Content**  
```bash
touch TestFile.txt
```
```
cat TestFile.txt
```

### **4.2 Editing a File Using `vi`**  
```bash
vi TestFile.txt
```
- Press `i` → Insert mode to edit text
- Press `Esc` → Exit insert mode  
- Type `:wq` → Save and exit  
- Type `:q!` → Exit without saving  

---

## **5. File Permissions and Ownership**  

### **5.1 Viewing File Permissions**  
```bash
ls -l
```

### **5.2 Changing File Permissions**  
- Grant full permissions to the owner, read & write to the group, read-only to others:
  ```bash
  chmod 766 TestFile.txt
  ```
- Add execute permission:
  ```bash
  chmod +x TestFile.txt
  ```
- Set read and write permissions for the owner only:
  ```bash
  chmod u=rw TestFile.txt
  ```

### **5.3 Changing File Ownership**  
To change the `owner` and `group` of a file to sagar:
```bash
sudo chown sagar:sagar TestFile.txt
```

### **5.4 Deleting a User and Verifying**  
```bash
sudo deluser sagar
```
```
cat /etc/passwd
```

---
