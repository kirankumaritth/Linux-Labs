# Linux-Labs

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
   
14. **`cd ~` (Home Directory):**
   - Changes the current working directory to the user's home directory.

   ```bash
   cd ~
   ```

   or simply

   ```bash
   cd
   ```

15. **`rmdir` (Remove Directory):**
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
