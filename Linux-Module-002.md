---

# **Linux Lab 2: Users, Groups, Files, Directories, and Permissions**  

---

## **1. User Management Commands**  

### **Commands Covered:**  
1. **Listing Users**  
   ```bash
   cat /etc/passwd
   ```

2. **Creating a User**  
   ```bash
   sudo adduser sagar
   ```
   ```bash
   sudo adduser adam
   ```

3. **Setting/Changing a User Password**  
   ```bash
   sudo passwd sagar
   ```

4. **Checking User Information**  
   ```bash
   id sagar
   ```

5. **Displaying Currently Logged-in Users**  
   ```bash
   who
   ```

6. **Switching to Another User**  
   ```bash
   su - sagar
   ```

7. **Granting sudo privileges to a user (If not allowed, a user with sudo privileges must grant access).**  
   ```bash
   sudo usermod -aG sudo sagar
   ```

8. **Viewing Last Login Information of a User**  
   ```bash
   last sagar
   ```

9. **Deleting a User**  
   ```bash
   sudo deluser adam
   ```

---

## **2. Group Management Commands**  

### **Commands Covered:**  
1. **Listing Groups**  
   ```bash
   cat /etc/group
   ```

2. **Creating a Group**  
   ```bash
   sudo groupadd mygroup
   ```

3. **Adding a User to a Group**  
   ```bash
   sudo usermod -aG mygroup sagar
   ```

4. **Checking a User's Group Membership**  
   ```bash
   groups sagar
   ```

5. **Changing a User's Primary Group**  
   ```bash
   sudo usermod -g mygroup sagar
   ```

6. **Removing a user from a group (Note: A user cannot be removed from their primary group; they must be in at least one group).**
   ```bash
   sudo gpasswd -d sagar mygroup
   ```

7. **Renaming a Group**  
   ```bash
   sudo groupmod -n newgroup mygroup
   ```

8. **Deleting a Group.**  
   ```bash
   sudo groupdel newgroup
   ```
The error message **"groupdel: cannot remove the primary group of user 'sagar'"** means that `newgroup` is the **primary group** of the user `sagar`. You cannot delete a group if it is assigned as the primary group of any user.  

### **Solution: Change the Primary Group of `sagar` Before Deleting**  
You need to change `sagar`'s primary group to another existing group before deleting `newgroup`. Follow these steps:

#### **Step 1: Check `sagar`'s Current Groups**
Run:
```bash
id sagar
```
This will show the user’s **UID, primary group (GID), and other group memberships**.

#### **Step 2: Change the Primary Group**
Assign a different existing group (e.g., `sagar` or `sudo`) as `sagar`'s primary group:
```bash
sudo usermod -g sagar sagar
```

#### **Step 3: Delete `newgroup`**
Now, you should be able to delete `newgroup` without errors:
```bash
sudo groupdel newgroup
```

#### **Step 4: Verify**
Check if `newgroup` is removed:
```bash
getent group newgroup
```
If it returns nothing, the group has been successfully deleted.

---

## **3. File and Directory Management**  

### **Commands Covered:**  
1. **Checking Current Directory**  
   ```bash
   pwd
   ```

2. **Listing Files and Directories**  
   ```bash
   ls -l
   ```

3. **Creating a New Directory**  
   ```bash
   mkdir DemoDirectory
   ```

4. **Navigating Between Directories**  
   ```bash
   cd DemoDirectory
   ```

5. **Creating an Empty File**  
   ```bash
   touch DemoFile.txt
   ```

6. **Copying a File to Another Location**  
   ```bash
   cp DemoFile.txt /home/kiran/Desktop
   ```

7. **Moving/Renaming a File**  
   ```bash
   mv DemoFile.txt TestFile.txt
   ```

8. **Deleting a File**  
   ```bash
   rm TestFile.txt
   ```

9. **Deleting a Directory**  
   ```bash
   rm -r DemoDirectory
   ```

---

## **4. Viewing and Editing Files**  

### **Commands Covered:**  
1. **Viewing File Content with `cat`**  
   ```bash
   cat TestFile.txt
   ```

2. **Editing a File Using `vi`**  
   ```bash
   vi TestFile.txt
   ```

   - Press **`i`** → Enter insert mode to edit text  
   - Press **`Esc`** → Exit insert mode  
   - Type **`:wq`** → Save and exit  
   - Type **`:q!`** → Exit without saving  

---

## **5. File Permissions and Ownership**  

### **Commands Covered:**  
1. **Viewing File Permissions**  
   ```bash
   ls -l
   ```

2. **Changing File Permissions with `chmod`**  
   - Give full permissions to owner, read & write to group, read-only to others:  
     ```bash
     chmod 766 TestFile.txt
     ```
   - Add execute permission to a file:  
     ```bash
     chmod +x TestFile.txt
     ```
   - Set read and write permissions for the owner:  
     ```bash
     chmod u=rw TestFile.txt
     ```

3. **Changing File Ownership with `chown`**  
   - Change the owner and group of a file:  
     ```bash
     sudo chown user:group TestFile.txt
     ```

---
