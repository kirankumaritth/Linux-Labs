# Linux-Labs

## Detailed step-by-step guide, for virtualization and Linux operating system installations:

1. Virtual Machine (VM) Setup-Individual User (1st Priority)
   •	Use virtualization software to run Linux within another OS.
   •	Popular VM tools:
o	VirtualBox (Free)
o	VMware Workstation/Player
o	Hyper-V (Windows built-in)
Virtual Machine (VM) Setup-Individual User
Here’s a step-by-step guide for setting up a virtual machine (VM) on your laptop using VirtualBox (free option) and running Ubuntu on it for performing labs. 
The instructions cover the installation of VirtualBox, creation of a VM, and the installation of Ubuntu OS on it.
Follow this Official Guide from Ubuntu Tutorials [Click Here](https://ubuntu.com/tutorials/how-to-run-ubuntu-desktop-on-a-virtual-machine-using-virtualbox#1-overview)


---
## Most Important and Frequently used Linux Commands:

Here's an explanation of each of the basic commands you've listed:

1. **`whoami`:**
   - Displays the username of the currently logged-in user.

   ```bash
   whoami
   ```

2. **echo $SHELL:**
   This will print the path to the current shell.

   ```bash
   echo $SHELL
   ```

3. **`hostname`:**
    - Prints the name of the host (computer).

    ```bash
    hostname
    ```

4. **`date`:**
    - Prints the current date and time.

    ```bash
    date
    ```
    
5. **cal (Calendar):**
    - Displays a calendar.

    ```bash
    cal
    ```

6. **`echo` (Print Message):**
   - Prints a message to the screen.

   ```bash
   echo "Hello, World!"
   ```

7. **man (Manual):**
    - Displays the manual or help for a command.
    ```bash
    man ls
    ```

8. **`pwd` (Print Working Directory):**
   - Displays the current working directory's full path.

   ```bash
   pwd
   ```

9. **`ls` (List):**
   - Lists the files and directories in the current directory.

   ```bash
   ls
   ```

10. **`ls -l` (Long List):**
   - Displays a detailed long-format listing of files and directories, including additional information such as permissions, owner, group, size, and modification time.

   ```bash
   ls -l
   ```

11. **`ls -a` (List All):**
   - Displays all files and directories, including hidden ones. Hidden files start with a dot (`.`).

   ```bash
   ls -a
   ```

12. **`mkdir` (Make Directory):**
   - Creates a new directory.

   ```bash
   mkdir Demo_Directory
   ```

13. **`cd` (Change Directory):**
   - Changes the current working directory.

   ```bash
   cd Demo_Directory
   ```
   
15. **`cd ~` (Home Directory):**
   - Changes the current working directory to the user's home directory.

   ```bash
   cd ~
   ```

   or simply

   ```bash
   cd
   ```

14. **`rmdir` (Remove Directory):**
   - Removes an empty directory.

   ```bash
   rmdir Demo_Directory
   ```

16. **`mkdir -p /home/ubuntu/New_Directory` (Create Directory with Path):**
    - Creates a directory and any necessary parent directories in the specified path.

    ```bash
    mkdir -p /home/kiran/NewDirectory
    ```

    ```bash
    cd NewDirectory
    ```

17. **`touch` (Create Empty File):**
   - Creates an empty file with the specified name.

   ```bash
   touch file1.txt file2.txt file3.txt
   ```

18. **`vi` (Text Editor):**
   - Opens the default text editor in Linux, Vi.

   ```bash
   vi file3.txt
   ```
---
1. **Entering Insert Mode:**
   - Press `i` to enter insert mode. In insert mode, you can type and edit the content of the file.

   ```bash
   i
   ```

2. **Saving Changes and Quitting:**
   - To save changes and exit vi, press `Esc` to ensure you are in command mode, then type `:wq` and press `Enter`.

   ```bash
   :wq
   ```

3. **Quitting Without Saving:**
   - If you want to quit vi without saving changes, press `Esc` to ensure you are in command mode, then type `:q!` and press `Enter`.

   ```bash
   :q!
   ```
---

19. **`echo "content" > filename` (Append Line to File):**
   - Adds a line of content to a file. If the file already exists, it will be overwritten.

   ```bash
   echo "This is a sample Text." > file1.txt
   ```

   ```bash
   echo "This is sample content." > file2.txt
   ```

20. **`cat` (Concatenate and Display):**
   - Displays the content of a file.

   ```bash
   cat file1.txt
   ```

21. **`cat file1.txt file2.txt > test3` (Merge Files):**
   - Merges the content of two files into a new file.

   ```bash
   cat file1.txt file2.txt > test3
   ```
   
22. **`echo "content" >> filename` (Append Next Line to File):**
   - Appends the specified content as the next line in the file.

   ```bash
   echo "This is another line of content." >> file1.txt
   ```
   ```bash
   cat file1.txt
   ```

23. **`cp` (Copy):**
    - Copies files or directories.

    ```bash
    cp file1.txt /home/kiran/Desktop
    ```

24. **`mv` (Move):**
    - Moves a file from one location to another or renames a file.

    ```bash
    mv file2.txt /home/kiran/Desktop
    ```

25. **`rm` (Remove):**
    - Removes files or directories.

    ```bash
    rm file1.txt
    ```

    To remove a directory and its contents recursively and forcefully:

    ```bash
    cd ~
    ```
    ```bash
    rm -rf NewDirectory
    ```

27. **`history > filename.txt` (Save Command History to File):**
    - Writes the command history to a text file.

    ```bash
    history > historyfile.txt
    ```

28. **head/tail:**
    - Displays the first/last part of a file.

    ```bash
    head historyfile.txt
    ```
    ```bash
    tail historyfile.txt
    ```

29. **chmod (Change Mode):**
    - Changes file permissions.

    ```bash
    ls -l
    ```
    ```bash
    chmod 766 historyfile.txt
    ```

30. **chown (Change Owner):**
    - Changes the owner of a file or directory.

    ```bash
    chown user:group file.txt
    ```

31. **ping (Network Connectivity):**
    - Tests network connectivity to a specific IP.

    ```bash
    ping google.com
    ```

32. **wget (Web Get):**
    - Downloads files from the internet.

    ```bash
    wget https://example.com/file.zip
    ```

33. **ssh (Secure Shell):**
    - Connects to a remote server securely.

    ```bash
    ssh user@remote_server
    ```

34. **uname:**
    - Displays system information.

    ```bash
    uname -a
    ```

35. **history:**
    - Displays the command history.

    ```bash
    history
    ```

36. **sudo (Superuser Do):**
    - Executes a command with administrative privileges.

    ```bash
    sudo apt-get update
    ```

37. **adduser/useradd:**
    - Adds a new user to the system.

    ```bash
    adduser demouser
    ```

    or

    ```bash
    useradd username
    ```

38. **passwd:**
    - Changes the user password.

    ```bash
    passwd username
    ```

39. **su (Switch User):**
    - Switches to another user account.

    ```bash
    su - username
    ```

40. **groups:**
    - Displays the groups a user belongs to.

    ```bash
    groups username
    ```

41. **shutdown/reboot:**
    - Shuts down or reboots the system.

    ```bash
    shutdown -h now
    ```

    or

    ```bash
    reboot
    ```

42. **exit:**
    - Exits the current shell or terminal.

    ```bash
    exit
    ```

---
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
