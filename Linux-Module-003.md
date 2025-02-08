---

# **Linux Lab 3: DevOps and Cloud Shell Scripting**

---
## **1. Introduction to Shell Scripting**  
### **What is Shell Scripting?**  
Shell scripting involves writing a series of Linux commands in a script file to automate tasks. These scripts help in simplifying system administration, task automation, and DevOps processes.

### **Importance of Shell Scripting in DevOps**  
- Automates repetitive tasks, reducing manual effort.
- Manages system configurations efficiently.
- Plays a crucial role in CI/CD pipelines.
- Enhances productivity in cloud environments like AWS.

---

## **2. Types of Shells**  
A shell acts as an interface between the user and the operating system. Common shell types include:

- **Bourne Shell (`sh`)** – The original Unix shell.
- **Bash Shell (`bash`)** – An improved version of Bourne Shell, widely used.
- **Korn Shell (`ksh`)** – Combines features of Bourne and C shells.
- **C Shell (`csh`)** – Provides a C-like syntax for scripting.
- **Z Shell (`zsh`)** – An extended shell with advanced features.

---

## Step-3 is Optional (This can also be performed on the local machine)

## **3. Setting Up Shell Scripting on AWS**  
### **Creating a Linux Machine on AWS**  
1. Log in to AWS and launch an **EC2 instance**.
2. Select **Amazon Linux 2 AMI**.
3. Configure security groups (allow **SSH on port 22**).
4. Connect to EC2 using SSH:
   ```bash
   ssh -i "your-key.pem" ec2-user@your-instance-ip
   ```

### **Using MobaXterm for Connection**  
1. Install **MobaXterm**.
2. Start a new **SSH session**.
3. Enter public IP and authentication details.
4. Connect and execute Linux commands.

---

## **4. Writing Your First Shell Script**  
### **Steps to Create and Run a Script**  
1. **Create a script file:**
   ```bash
   touch first_script.sh
   ```
2. **Edit the script:**
   ```bash
   vi first_script.sh
   ```
3. **Write script content:**
   ```bash
   #!/bin/bash
   echo "Hello, World!"
   ```
4. **Make the script executable:**
   ```bash
   chmod +x first_script.sh
   ```
5. **Run the script:**
   ```bash
   ./first_script.sh
   ```

---

## **5. Variables and Data Handling**  
### **Declaring Variables**  
```bash
NAME="DevOps"
echo "Welcome to $NAME"
```

### **Arithmetic Operations**  
```bash
NUM1=10
NUM2=20
SUM=$((NUM1 + NUM2))
echo "Sum: $SUM"
```

---

## **6. Control Statements in Shell Scripting**  
### **Conditional Statements (`if`, `if-else`, `if-elif-else`)**  
```bash
#!/bin/bash
NUM=10

if [ $NUM -gt 5 ]; then
    echo "Number is greater than 5"
elif [ $NUM -eq 5 ]; then
    echo "Number is equal to 5"
else
    echo "Number is less than 5"
fi
```

### **Case Statement**  
```bash
#!/bin/bash
DAY="Monday"

case $DAY in
    "Monday") echo "Start of the work week" ;;
    "Friday") echo "End of the work week" ;;
    "Saturday" | "Sunday") echo "Weekend!" ;;
    *) echo "Midweek day" ;;
esac
```

---

## **7. Loops in Shell Scripting**  
### **For Loop**  
```bash
for i in 1 2 3 4 5; do
    echo "Number: $i"
done
```

### **While Loop**  
```bash
COUNTER=1
while [ $COUNTER -le 5 ]; do
    echo "Counter: $COUNTER"
    COUNTER=$((COUNTER + 1))
done
```

### **Until Loop**  
```bash
COUNTER=1
until [ $COUNTER -gt 5 ]; do
    echo "Counter: $COUNTER"
    COUNTER=$((COUNTER + 1))
done
```

---

## **8. Functions in Shell Scripting**  
### **Defining and Calling a Function**  
```bash
#!/bin/bash
greet() {
    echo "Hello, $1"
}
greet "DevOps"
```

### **Returning a Value from a Function**  
```bash
add() {
    SUM=$(( $1 + $2 ))
    echo $SUM
}

RESULT=$(add 3 4)
echo "Sum: $RESULT"
```

---

## **9. Command Line Arguments**  
### **Handling Input Arguments**  
```bash
#!/bin/bash
echo "Script Name: $0"
echo "First Argument: $1"
echo "Second Argument: $2"
echo "All Arguments: $@"
echo "Number of Arguments: $#"
```
**Usage:**  
```bash
./script.sh arg1 arg2 arg3
```

---

## **10. Common Shell Scripting Commands for DevOps**  
### **File and Directory Commands**  
```bash
touch filename  # Create a new file
ls              # List files
cd /path        # Change directory
mkdir dir       # Create directory
rm filename     # Remove file
```

### **Text Processing Commands**  
```bash
grep "pattern" filename  # Search for a pattern
sed 's/old/new/g' file   # Replace text
sort filename            # Sort lines
wc filename              # Count words, lines, and characters
```

### **System Monitoring**  
```bash
df -h      # Check disk space
free -h    # Check memory usage
uptime     # Display system uptime
ps aux     # List running processes
top        # Monitor real-time system activity
```

### **Networking Commands**  
```bash
ping google.com       # Check network connectivity
ifconfig             # Display network interfaces
scp file user@host:/path  # Secure copy files over SSH
```

---

## **11. Example Scripts for DevOps Tasks**  
### **Finding the Greater of Two Numbers**  
```bash
#!/bin/bash
if [ $# -ne 2 ]; then
    echo "Usage: $0 num1 num2"
    exit 1
fi

if [ $1 -gt $2 ]; then
    echo "$1 is greater than $2"
elif [ $1 -lt $2 ]; then
    echo "$2 is greater than $1"
else
    echo "Both numbers are equal"
fi
```

### **Simple Calculator (Addition)**  
```bash
#!/bin/bash
if [ $# -ne 2 ]; then
    echo "Usage: $0 num1 num2"
    exit 1
fi

SUM=$(( $1 + $2 ))
echo "The sum of $1 and $2 is $SUM"
```

---

## **Conclusion**  
- Shell scripting is essential for DevOps engineers.
- It automates workflows, CI/CD pipelines, and system monitoring.
- Used extensively in AWS, Kubernetes, and Linux administration.
