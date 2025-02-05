## Users and Groups:

Commonly used Linux commands related to user management:

1. **adduser/useradd:**
    - Adds a new user to the system.

    ```bash
    adduser demouser
    ```

    or

    ```bash
    useradd username
    ```

2. **passwd:**
    - Changes the user password.

    ```bash
    passwd username
    ```

3. **su (Switch User):**
    - Switches to another user account.

    ```bash
    su - username
    ```

4. **groups:**
    - Displays the groups a user belongs to.

    ```bash
    groups username
    ```
5. **Listing Users:**
   ```bash
   cat /etc/passwd
   ```

   This command will display a list of all users.

6. **Creating a User:**
   ```bash
   sudo adduser sagar
   ```

   ```bash
   sudo adduser myuser
   ```

7. **User Information:**
   ```bash
   id sagar
   ```

8. **Displaying Currently Logged in Users:**
   ```bash
   who
   ```

9. **Changing Password:**
   ```bash
   sudo passwd sagar
   ```

10. **Granting Sudo Privileges:**
   ```bash
   sudo usermod -aG sudo sagar
   ```

11. **Switching to Another User:**
    ```bash
    su - sagar
    ```

12. **Viewing Last Login Information:**
    ```bash
    last sagar
    ```

13. **Deleting a User:**
   ```bash
   sudo deluser sagar
   ```
#### Note:
Remember to use `sudo` before these commands if you need superuser privileges. Also, be cautious when managing users, as it can impact system security and functionality.

---
In Linux, the commands related to groups primarily involve managing user groups. Here are some common commands:

1. **Creating a Group:**
   ```bash
   sudo groupadd [groupname]
   ```
   Example:
   ```bash
   sudo groupadd mygroup
   ```

2. **Adding a User to a Group:**
   ```bash
   sudo usermod -aG [groupname] [username]
   ```
   Example:
   ```bash
   sudo usermod -aG mygroup myuser
   ```

3. **Listing Groups:**
   ```bash
   cat /etc/group
   ```
   or
   ```bash
   getent group
   ```

4. **Displaying Group Information:**
   ```bash
   id [username]
   ```
   Example:
   ```bash
   id myuser
   ```

5. **Changing a User's Primary Group:**
   ```bash
   sudo usermod -g [groupname] [username]
   ```
   Example:
   ```bash
   sudo usermod -g mygroup myuser
   ```

6. **Removing a User from a Group:**
   ```bash
   sudo gpasswd -d [username] [groupname]
   ```
   Example:
   ```bash
   sudo gpasswd -d myuser mygroup
   ```

7. **Changing a Group's Name:**
   ```bash
   sudo groupmod -n [newgroupname] [oldgroupname]
   ```
   Example:
   ```bash
   sudo groupmod -n newmygroup mygroup
   ```

8. **Deleting a Group:**
   ```bash
   sudo groupdel [groupname]
   ```
   Example:
   ```bash
   sudo groupdel newmygroup
   ```
---


## Files, Directories and Permissions:

1. **pwd:** Print working directory.
   ```bash
   pwd
   ```

2. **ls:** List files and directories.
   ```bash
   ls
   ```

3. **mkdir:** Create a new directory.
   ```bash
   mkdir [directory_name]
   ```
   ```bash
   mkdir DemoDirectory
   ```

4. **cd:** Change directory.
   ```bash
   cd [directory_name]
   ```
   ```bash
   cd DemoDirectory
   ```

5. **touch:** Create an empty file or update the access and modification times of a file.
   ```bash
   touch [file_name]
   ```
   ```bash
   touch DemoFile.txt
   ```

6. **cp:** Copy files or directories.
   ```bash
   cp [source] [destination]
   ```
   ```bash
   cp DemoFile.txt /home/kiran/Desktop
   ```
   ```bash
   ls /home/kiran/Desktop
   ```

7. **mv:** Move or rename files or directories.
   ```bash
   mv [source] [destination]
   ```
   ```bash
   mv DemoFile.txt TestFile.txt
   ```
   ```bash
   mv TestFile.txt /home/kiran/Desktop
   ```
   ```bash
   ls /home/kiran/Desktop
   ```

8. **rm:** Remove files or directories.

   ```bash
   cd /home/kiran/Desktop
   ```
   ```bash
   rm [file_name]
   ```
   ```bash
   rm DemoFile.txt
   ```
---
### Viewing File Contents:

9. **vim:** A powerful text editor in the terminal.

    ```bash
    cd /home/kiran/Desktop
    ```
    ```bash
    vi TestFile.txt
    ```
---
**Entering Insert Mode:**
   - Press `i` to enter insert mode. In insert mode, you can type and edit the content of the file.

   ```bash
   i
   ```

**Saving Changes and Quitting:**
   - To save changes and exit vi, press `Esc` to ensure you are in command mode, then type `:wq` and press `Enter`.

   ```bash
   :wq
   ```

**Quitting Without Saving:**
   - If you want to quit vi without saving changes, press `Esc` to ensure you are in command mode, then type `:q!` and press `Enter`.

   ```bash
   :q!
   ```

10. **cat:** Display the content of a file.

    ```bash
    cat [file_name]
    ```
    ```bash
    cat TestFile.txt
    ```
---
### Permissions:

11. **chmod:** Change file permissions.
   ```bash
   cd /home/kiran/Desktop
   ```
   ```bash
   ls -l
   ```
   ```bash
   chmod [permissions] [file_name]
   ```
   ```bash
   chmod 766 TestFile.txt
   ```
   Example:
   ```bash
   chmod +x TestFile.txt    # Add execute permission
   ```
   ```bash
   chmod u=rw TestFile.txt  # Set read and write permission for the owner
   ```

12. **chown:** Change file owner and group.
    ```bash
    chown [new_owner]:[new_group] [file_name]
    ```

    Example:
    ```bash
    chown user:group file.txt
    ```
