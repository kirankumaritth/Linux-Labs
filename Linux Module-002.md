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
