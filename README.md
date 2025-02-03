# Linux-Labs

## Detailed step-by-step guide, for virtualization and Linux operating system installations:

### Installing VirtualBox:

#### Step 1: Download VirtualBox

- Open your web browser and go to the [VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads) page.
- Choose the version that corresponds to your host operating system (Windows, macOS, or Linux).
- Click on the download link to start the download.

#### Step 2: Install VirtualBox

- Once the download is complete, locate the installer file and run it.
- Follow the on-screen instructions provided by the installer to install VirtualBox.
- During installation, you may be prompted to install additional components, such as networking features. Accept the default settings unless you have specific requirements.

### Creating a New Virtual Machine (VM):

#### Step 3: Open VirtualBox and Create a New VM

- Launch the VirtualBox application.
- Click on the "New" button in the toolbar to create a new virtual machine.
- Give your virtual machine a name (e.g., "Ubuntu_VM") and choose "Linux" as the type and "Ubuntu" as the version.

#### Step 4: Allocate Memory (RAM)

- Choose the amount of RAM to allocate to your virtual machine. If you're a college student, allocating around 2 GB to 4 GB should be sufficient for basic usage.

#### Step 5: Create a Virtual Hard Disk

- Select "Create a virtual hard disk now" and click "Create."
- Choose the hard disk file type (usually VDI) and click "Next."
- Choose either dynamically allocated or fixed size. If you're unsure, choose dynamically allocated.
- Set the size of the virtual hard disk. A minimum of 25 GB is recommended.

#### Step 6: Specify Disk File Location and Size

- Choose the location where you want to store the virtual disk file and set the size.

### Installing Ubuntu on VirtualBox:

#### Step 7: Mount Ubuntu ISO

- With your new virtual machine selected, click on "Settings."
- Go to the "Storage" tab.
- Under "Controller: IDE," click on the empty disk icon and choose "Choose a disk file."
- Locate and select the Ubuntu ISO file you downloaded earlier.

#### Step 8: Start the Virtual Machine

- Click "Start" to launch the virtual machine.
- The virtual machine will boot from the Ubuntu ISO.

#### Step 9: Install Ubuntu

- Follow the on-screen instructions to install Ubuntu.
- Choose your language and click "Install Ubuntu."
- Follow the installation wizard, including selecting your time zone, keyboard layout, and creating a user account.
- When prompted, choose the option to erase the disk and install Ubuntu (or manually partition if you have specific requirements).

#### Step 10: Complete Installation

- After the installation is complete, eject the installation ISO.
- Restart the virtual machine.

#### Step 11: Post-Installation Steps

- Complete the initial setup, including updating the system and installing any additional software.

You've successfully installed VirtualBox and Ubuntu on your virtual machine.

---
## Linux directory structure

Explanation of each directory in a typical Linux file system:

1. **`/` (Root Directory):**
   - The root directory is the top-level directory in the Linux file system hierarchy. It contains all other directories and files.

2. **`/home`:**
   - The `/home` directory is the default location for user home directories. Each user typically has a subdirectory within `/home` where they store their personal files and configurations.

3. **`/user`:**
   - This directory appears to be a custom directory for storing user programs. However, it's not a standard directory in a typical Linux file system. User programs are often stored in directories like `/usr/bin` or `/usr/local/bin`.

4. **`/bin` (Binary and Executable Files):**
   - The `/bin` directory contains essential binary and executable files that are required for the system to function, even in single-user mode. Common commands like `ls`, `cp`, `mv`, etc., are located here.

5. **`/etc` (Configuration Files):**
   - The `/etc` directory contains system-wide configuration files and shell scripts that are used to boot and initialize system settings. It also includes configuration files for installed software.

6. **`/apt` (Optional/Third-party Software):**
   - The `/apt` directory seems to be a custom directory for optional or third-party software. However, the standard directory for package management on Debian-based systems (like Ubuntu) is `/etc/apt`.

7. **`/var` (Variable Files):**
   - The `/var` directory contains variable data files that may change as the system runs. This includes log files (`/var/log`), spool directories for mail and print queues, and other files that may grow or change size during the system's operation.

8. **`/temp` (Temporary Files):**
   - The `/temp` directory (typically `/tmp`) is used for temporary files. Programs can store temporary data here, and the system may periodically clean up old files. It's important to note that the correct name for the temporary directory is usually `/tmp`, not `/temp`.

9. **`/mnt` (Mount Point):**
   - The `/mnt` directory is often used as a mount point for temporarily mounting filesystems or devices.

10. **`/opt` (Optional Software):**
    - The `/opt` directory is used for the installation of optional software packages. It provides a way to add software packages from vendors that are not part of the default system.

11. **`/srv` (Service Data):**
    - The `/srv` directory is used to store data for services provided by the system. For example, data for a web server or FTP server might be stored in subdirectories of `/srv`.

12. **`/usr` (User Binaries and Data):**
    - The `/usr` directory contains user-related programs, libraries, documentation, and source code. The `/usr/bin` subdirectory, for instance, holds user binaries (executable files).

Remember that while many Linux systems follow a similar directory structure, there can be variations based on the distribution and specific configurations. The Filesystem Hierarchy Standard (FHS) is a set of guidelines that many Linux distributions adhere to maintain a consistent directory structure.

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
