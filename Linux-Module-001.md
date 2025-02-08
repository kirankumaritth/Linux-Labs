---

# **Linux Lab - Essential Commands with Explanation**

---

## **1. User & System Information Commands**  

### **1.1 `whoami` – Check Logged-in User**
- This command displays the currently logged-in user.
- Useful for verifying user identity in a multi-user environment.

```bash
whoami
```

### **1.2 `echo $SHELL` – Display the Current Shell**
- Shows the default shell (e.g., Bash, Zsh).
- Important for knowing the command syntax and scripting behavior.

```bash
echo $SHELL
```

### **1.3 `hostname` – Display Computer Name**
- Prints the machine’s hostname.
- Useful when working in networks or SSH.

```bash
hostname
```

### **1.4 `uname -a` – Display System Information**
- Shows system details such as OS type, kernel version, and architecture.

```bash
uname -a
```

### **1.5 `date` – Show Current Date & Time**
- Displays the system's current date and time.

```bash
date
```

### **1.6 `cal` – Show Calendar**
- Displays the current month’s calendar.
- Useful for checking dates.

```bash
cal
```

---

## **2. Navigating the Filesystem**  

### **2.1 `pwd` – Print Current Directory**
- Displays the absolute path of the current working directory.

```bash
pwd
```

### **2.2 `ls` – List Directory Contents**
- Lists files and folders in the current directory.

```bash
ls
```

### **2.3 `ls -l` – List Files with Details**
- Shows additional file information (permissions, size, owner, timestamp).

```bash
ls -l
```

### **2.4 `ls -a` – Show Hidden Files**
- Displays all files, including hidden ones (starting with `.`).

```bash
ls -a
```

### **2.5 `cd` – Change Directory**
- Moves between directories.

```bash
cd Documents
```

### **2.6 `cd ~` – Go to Home Directory**
- Takes the user back to the home directory.

```bash
cd ~
```

or simply:

```bash
cd
```

---

## **3. File & Directory Management**  

### **3.1 `mkdir` – Create a New Directory**
- Creates an empty directory.

```bash
mkdir NewFolder
```

### **3.2 `mkdir -p` – Create Nested Directories**
- Creates parent directories if they don’t exist.

```bash
mkdir -p /home/user/projects/devops
```

### **3.3 `rmdir` – Remove Empty Directories**
- Only removes empty directories.

```bash
rmdir EmptyFolder
```

### **3.4 `touch` – Create an Empty File**
- Creates a blank file.

```bash
touch file1.txt
```

### **3.5 `cp` – Copy Files**
- Copies a file to another location.

```bash
cp file1.txt /home/user/Desktop/
```

- To copy a directory recursively:

```bash
cp -r folder1/ /home/user/Desktop/
```

### **3.6 `mv` – Move or Rename Files**
- Moves a file to another directory.

```bash
mv file1.txt /home/user/Documents/
```

- Rename a file:

```bash
mv oldname.txt newname.txt
```

### **3.7 `rm` – Remove Files**
- Deletes a file.

```bash
rm file1.txt
```

- Remove a folder and its contents recursively:

```bash
rm -rf foldername
```

---

## **4. Viewing & Editing Files**  

### **4.1 `echo` – Print or Write to a File**
- Prints a message on the screen.

```bash
echo "Hello, World!"
```

- Writes content to a file (overwrites existing content).

```bash
echo "Sample text" > file1.txt
```

- Appends text to a file.

```bash
echo "Another line" >> file1.txt
```

### **4.2 `cat` – Display File Content**
- Shows the content of a file.

```bash
cat file1.txt
```

- Merge two files into a new file.

```bash
cat file1.txt file2.txt > merged.txt
```

### **4.3 `head` – View First Lines of a File**
- Displays the first 10 lines by default.

```bash
head file1.txt
```

### **4.4 `tail` – View Last Lines of a File**
- Displays the last 10 lines.

```bash
tail file1.txt
```

### **4.5 `vi` – Open a File in the Vi Editor**
- Opens a file for editing.

```bash
vi file1.txt
```

#### **Basic Vi Commands:**
- Press `i` to enter insert mode.
- Type text.
- Press `Esc` to exit insert mode.
- Type `:wq` to save and exit.
- Type `:q!` to exit without saving.

---

## **5. Working with Commands & Processes**  

### **5.1 `man` – View Command Manual**
- Opens the manual for a command.

```bash
man ls
```

### **5.2 `history` – Show Command History**
- Displays previously executed commands.

```bash
history
```

- Save history to a file.

```bash
history > my_history.txt
```

### **5.3 `ping` – Check Network Connectivity**
- Sends a request to a domain or IP.

```bash
ping google.com
```

### **5.4 `wget` – Download a File**
- Downloads a file from the internet.

```bash
wget https://example.com/file.zip
```

### **5.5 `ssh` – Connect to a Remote Server**
- Securely logs into another machine.

```bash
ssh user@remote_server
```

---

## **6. System Administration**  

### **6.1 `sudo` – Execute Commands as Superuser**
- Runs commands with administrative privileges.

```bash
sudo apt-get update
```

### **6.2 `shutdown` – Turn Off the System**
- Shutdown immediately.

```bash
shutdown -h now
```

- Schedule a shutdown after 5 minutes.

```bash
shutdown -h +5
```

### **6.3 `reboot` – Restart the System**
- Reboots the system.

```bash
reboot
```

### **6.4 `exit` – Logout or Close the Terminal**
- Closes the terminal session.

```bash
exit
```

---
