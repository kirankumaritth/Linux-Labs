---

# **Linux Lab 3: Shell Scripting for DevOps**

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

## **3. Setting Up Shell Scripting on AWS (Optional, Can Be Done Locally)**  
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
4. **Save and exit the editor:** Press `Esc`, then type `:wq` and press `Enter`.
5. **Change file permissions to make it executable:**
   ```bash
   chmod +x first_script.sh
   ```
6. **Run the script:**
   ```bash
   ./first_script.sh
   ```
7. **Expected output:**
   ```bash
   Hello, World!
   ```

---

## **5. Variables and Data Handling**  
### **Steps to Declare and Use Variables**  
1. **Create a script file:**
   ```bash
   touch variables.sh
   ```
2. **Edit the script:**
   ```bash
   vi variables.sh
   ```
3. **Write the script:**
   ```bash
   #!/bin/bash
   NAME="DevOps"
   echo "Welcome to $NAME"
   ```
4. **Make the script executable and run it:**
   ```bash
   chmod +x variables.sh
   ./variables.sh
   ```
5. **Expected output:**
   ```bash
   Welcome to DevOps
   ```

### **Steps for Arithmetic Operations**  
1. **Modify the script to include arithmetic operations:**
   ```bash
   #!/bin/bash
   NUM1=10
   NUM2=20
   SUM=$((NUM1 + NUM2))
   echo "Sum: $SUM"
   ```
2. **Run the script:**
   ```bash
   ./variables.sh
   ```
3. **Expected output:**
   ```bash
   Sum: 30
   ```

---

## **6. Control Statements in Shell Scripting**  
### **Steps to Use Conditional Statements**  
1. **Create a script file:**
   ```bash
   touch conditionals.sh
   ```
2. **Write the script:**
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
3. **Make it executable and run it:**
   ```bash
   chmod +x conditionals.sh
   ./conditionals.sh
   ```
4. **Expected output:**
   ```bash
   Number is greater than 5
   ```

---

## **7. Loops in Shell Scripting**  
### **Steps to Use a `for` Loop**  
1. **Create a script file:**
   ```bash
   touch loops.sh
   ```
2. **Write the script:**
   ```bash
   #!/bin/bash
   for i in {1..5}; do
       echo "Number: $i"
   done
   ```
3. **Make it executable and run it:**
   ```bash
   chmod +x loops.sh
   ./loops.sh
   ```
4. **Expected output:**
   ```bash
   Number: 1
   Number: 2
   Number: 3
   Number: 4
   Number: 5
   ```

---

## **8. Functions in Shell Scripting**  
### **Steps to Create and Use Functions**  
1. **Create a script file:**
   ```bash
   touch functions.sh
   ```
2. **Write the script:**
   ```bash
   #!/bin/bash
   greet() {
       echo "Hello, $1"
   }
   greet "DevOps"
   ```
3. **Make it executable and run it:**
   ```bash
   chmod +x functions.sh
   ./functions.sh
   ```
4. **Expected output:**
   ```bash
   Hello, DevOps
   ```

---

## **Conclusion**  
- Shell scripting is essential for DevOps engineers.
- It automates workflows, CI/CD pipelines, and system monitoring.
- Used extensively in AWS, Kubernetes, and Linux administration.
