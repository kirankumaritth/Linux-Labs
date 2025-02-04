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
