## Users and Groups:

Commonly used Linux commands related to user management:

1. **Listing Users:**
   ```bash
   cat /etc/passwd
   ```

   This command will display a list of all users.

2. **Creating a User:**
   ```bash
   sudo adduser sagar
   ```

   ```bash
   sudo adduser myuser
   ```

3. **User Information:**
   ```bash
   id sagar
   ```

4. **Displaying Currently Logged in Users:**
   ```bash
   who
   ```

5. **Changing Password:**
   ```bash
   sudo passwd sagar
   ```

6. **Granting Sudo Privileges:**
   ```bash
   sudo usermod -aG sudo sagar
   ```

7. **Switching to Another User:**
    ```bash
    su - sagar
    ```

8. **Viewing Last Login Information:**
    ```bash
    last sagar
    ```

9. **Deleting a User:**
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
