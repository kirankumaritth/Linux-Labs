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

### **Getting Started with Shell Scripting**  

### **Setting Up a Linux Machine on AWS (Optional, Can Be Done Locally)**  

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

## **2. Lab: Introduction to Shell Scripting**  

### **1. Understanding Shell Scripting**  
Shell scripting is a way to automate tasks in a Unix/Linux system by writing commands in a script file that can be executed as a program.

### **2. Checking and Changing the Shell**  

1. **Check the current shell:**  
   
   ```bash
   echo $SHELL
   ```

2. **List available shells:**  
   
   ```bash
   cat /etc/shells
   ```

3. **Change the shell (Example: Changing to Bash shell):**  
   
   ```bash
   chsh -s /bin/bash
   ```
   
   - You may need to log out and log back in for the change to take effect.

---

## **3. Writing Your First Shell Script**  

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
   #!/usr/bin/env bash
   echo "Hello, World!"
   ```

4. **Make it executable and run it:**  

   ```bash
   chmod +x first_script.sh
   ./first_script.sh
   ```

5. **Expected Output:**  

   ```bash
   Hello, World!
   ```

---

## **4. Variables and Data Handling**  

### **4.1 Declaring and Using Variables**  

1. **Create a script file:**  

   ```bash
   touch variables.sh
   ```

2. **Edit the script:**  

   ```bash
   vi variables.sh
   ```

3. **Write script content:**  

   ```bash
   #!/usr/bin/env bash
   NAME="DevOps"
   echo "Welcome to $NAME"
   ```

4. **Make it executable and run it:**  

   ```bash
   chmod +x variables.sh
   ./variables.sh
   ```

5. **Expected Output:**  

   ```bash
   Welcome to DevOps
   ```

---

### **4.2 Performing Arithmetic Operations**  

1. **Create a script file:**  

   ```bash
   touch arithmetic.sh
   ```

2. **Edit the script:**  

   ```bash
   vi arithmetic.sh
   ```

3. **Write script content:**  

   ```bash
   #!/usr/bin/env bash
   NUM1=10
   NUM2=20
   SUM=$((NUM1 + NUM2))
   echo "Sum: $SUM"
   ```

4. **Make it executable and run it:**  

   ```bash
   chmod +x arithmetic.sh
   ./arithmetic.sh
   ```

5. **Expected Output:**  

   ```bash
   Sum: 30
   ```

---

## **5. Control Statements and Loops**  

### **5.1 Using Conditional Statements**  

1. **Create a script file:**  

   ```bash
   touch conditionals.sh
   ```

2. **Edit the script:**  

   ```bash
   vi conditionals.sh
   ```

3. **Write script content:**  

   ```bash
   #!/usr/bin/env bash
   NUM=10
   if [ $NUM -gt 5 ]; then
       echo "Number is greater than 5"
   elif [ $NUM -eq 5 ]; then
       echo "Number is equal to 5"
   else
       echo "Number is less than 5"
   fi
   ```

4. **Make it executable and run it:**  

   ```bash
   chmod +x conditionals.sh
   ./conditionals.sh
   ```

5. **Expected Output:**  

   ```bash
   Number is greater than 5
   ```

---

### **5.2 Using a `for` Loop**  

1. **Create a script file:**  

   ```bash
   touch loops.sh
   ```

2. **Edit the script:**  

   ```bash
   vi loops.sh
   ```

3. **Write script content:**  

   ```bash
   #!/usr/bin/env bash
   for i in {1..5}; do
       echo "Number: $i"
   done
   ```

4. **Make it executable and run it:**  

   ```bash
   chmod +x loops.sh
   ./loops.sh
   ```

5. **Expected Output:**  

   ```bash
   Number: 1
   Number: 2
   Number: 3
   Number: 4
   Number: 5
   ```

---

## **6. Functions in Shell Scripting**  

### **Creating and Using Functions**  

1. **Create a script file:**  

   ```bash
   touch functions.sh
   ```

2. **Edit the script:**  

   ```bash
   vi functions.sh
   ```

3. **Write script content:**  

   ```bash
   #!/usr/bin/env bash
   greet() {
       echo "Hello, $1"
   }
   greet "DevOps"
   ```

4. **Make it executable and run it:**  

   ```bash
   chmod +x functions.sh
   ./functions.sh
   ```

5. **Expected Output:**  

   ```bash
   Hello, DevOps
   ```

---


## **7. Shell script to `install Docker` on an **Ubuntu 24.04 LTS** machine.**  

### **It follows the official installation steps, ensuring that Docker is installed correctly with the latest stable version.**

#### Features of this script:
✅ Removes old Docker versions  
✅ Installs required dependencies  
✅ Adds the official Docker repository  
✅ Installs Docker Engine, CLI, and containerd  
✅ Enables and starts the Docker service  
✅ Adds the current user to the Docker group (optional)  

---
### **Steps for Execution**
1. **Create a script file:**
   ```bash
   touch install_docker.sh
   ```
   ```
   vi install_docker.sh
   ```
---

### **Shell Script: `install_docker.sh`**
```
#!/bin/bash

for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

```
---

2. Make the script executable:  
   ```bash
   chmod +x install_docker.sh
   ```
3. Run the script with:  
   ```bash
   ./install_docker.sh -y
   ```
---
### **Post-Installation Verification**
- Check if Docker is installed:
  ```bash
  docker --version
  ```

- Create a docker group to add current user
  ```bash
  sudo groupadd docker
  ```

- Add the Current user to the docker group to get permissions
  ```bash
  sudo usermod -aG docker $USER
  ```
- List docker Images
  ```bash
  docker images
  ```
- Run a test container:
  ```bash
  docker run hello-world
  ```
- List docker Images
  ```bash
  docker images
  ```
---
### Now try to run a web server.  

#### **Example: Running an Nginx Web Server with Alpine**
```bash
docker run -d --name c1 -p 8080:80 nginx:alpine
```
Then, open your browser and visit **`http://localhost:8080`** to see the Nginx default page.

---
### Stop and Remove the Container

List all the Active & Inactive Containers
```bash
docker ps -a
```
Stop the running Container
```bash
docker stop <Container ID>
```
Remove the Running Container

```bash
docker rm <Container ID>
```
---

## **8. Shell script to `Uninstall Docker` on an **Ubuntu 24.04 LTS** machine.**  

### **Shell Script: `remove_docker.sh`**

---

### **What This Script Does**
✅ Stops and removes all running/stopped containers  
✅ Uninstalls Docker packages  
✅ Deletes Docker directories (`/var/lib/docker`, `/etc/docker`, `/var/run/docker.sock`)  
✅ Removes the Docker group (if it exists)  
✅ Cleans up unused dependencies  

---

### **How to Use**
1. Create & Save the script as `remove_docker.sh`.  
   ```bash
   touch remove_docker.sh
   ```
   ```
   vi remove_docker.sh
   ```
---

   ```bash
   #!/bin/bash
   
   set -e  # Exit on error
   
   #!/bin/bash

   sudo apt-get purge docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-ce-rootless-extras

   sudo rm -rf /var/lib/docker
   sudo rm -rf /var/lib/containerd

   sudo rm /etc/apt/sources.list.d/docker.list
   sudo rm /etc/apt/keyrings/docker.asc
   ```

---

2. Make it executable:
   ```bash
   chmod +x remove_docker.sh
   ```
3. Run the script:
   ```bash
   ./remove_docker.sh
   ```
---

### **Post-UnInstallation Verification**
- Check if Docker is completely Uninstalled:
  ```bash
  docker --version
  ```
---

## **9. Lab: Installing and Uninstalling Terraform on Ubuntu**

---

### **Step 1: Checking System Requirements**
Before installing Terraform, verify that your system is up-to-date.

1. Open the terminal.
2. Run the following command to update package lists:
   ```bash
   sudo apt update -y && sudo apt upgrade -y
   ```
3. Ensure that `wget` and `unzip` are installed:
   ```bash
   sudo apt install -y wget unzip
   ```

---

### **Step 2: Creating the Shell Script**

1. Open the terminal and navigate to your working directory:
   ```bash
   cd ~
   ```
2. Create a new script file:
   ```bash
   touch terraform_installer.sh
   ```
3. Open the script file using a text editor (e.g., nano):
   ```bash
   vi terraform_installer.sh
   ```
4. Copy and paste the following script into the file:
   ```bash
   #!/usr/bin/env bash

   install_terraform() {
       echo "Installing Terraform..."
       sudo apt update -y
       sudo apt install -y wget unzip
       wget -qO- https://releases.hashicorp.com/terraform/$(curl -s https://api.github.com/repos/hashicorp/terraform/releases/latest | grep 'tag_name' | cut -d '"' -f 4 | tr -d 'v')/terraform_$(curl -s https://api.github.com/repos/hashicorp/terraform/releases/latest | grep 'tag_name' | cut -d '"' -f 4 | tr -d 'v')_linux_amd64.zip -O terraform.zip
       unzip terraform.zip
       sudo mv terraform /usr/local/bin/
       rm terraform.zip
       echo "Terraform installation complete."
   }

   uninstall_terraform() {
       echo "Uninstalling Terraform..."
       sudo rm -f /usr/local/bin/terraform
       echo "Terraform has been removed."
   }

   echo "Choose an option:"
   echo "1. Install Terraform"
   echo "2. Uninstall Terraform"
   read -p "Enter choice [1-2]: " choice

   case $choice in
       1) install_terraform ;;
       2) uninstall_terraform ;;
       *) echo "Invalid option. Exiting." ;;
   esac
   ```
5. Save and exit the editor:
   - Esc + :wq!
---

### **Step 3: Granting Execution Permissions**
Before running the script, grant execution permissions:
```bash
chmod +x terraform_installer.sh
```

---

### **Step 4: Running the Script**
Execute the script by running:
```bash
./terraform_installer.sh
```
You will be prompted to choose an option:
```
Choose an option:
1. Install Terraform
2. Uninstall Terraform
Enter choice [1-2]:
```

---

### **Step 5: Verifying the Installation**
After installing Terraform, check if it is installed correctly by running:
```bash
terraform -v
```
You should see an output displaying the Terraform version:
```
Terraform v1.xx.x
```

---

### **Step 6: Uninstalling Terraform**
If you need to uninstall Terraform, rerun the script and select option `2`.
```bash
./terraform_installer.sh
```

Verify that Terraform has been removed by running:
```bash
terraform -v
```
If Terraform is uninstalled successfully, you will see:
```
bash: /usr/local/bin/terraform: No such file or directory
```

---

### **Summary**
In this lab, you:
- Created a shell script to install and uninstall Terraform.
- Made the script executable and ran it.
- Verified the installation and uninstallation of Terraform.

This approach helps automate Terraform setup, making it easy to manage on multiple machines.

---

### **Next Steps**
- Try modifying the script to support different Terraform versions.
- Explore using Terraform to provision infrastructure on AWS, Azure, or Google Cloud.

---

**End of Lab** 🎉







































## **10. Sample Shell Script for System Backup 💾**

---
### **Steps for Execution**
1. **Create a script file:**
   ```bash
   touch backup.sh
   ```
   ```
   vi backup.sh
   ```
---
```bash
#!/bin/bash  
# Backup script to copy important files  

SOURCE="/home/user/documents"  
DESTINATION="/backup/documents_$(date +%F).tar.gz"  

tar -czf $DESTINATION $SOURCE  
echo "Backup completed successfully: $DESTINATION"  
```

### **Executing the Script ▶️**  
```bash
chmod +x backup.sh  # Grant execute permission
```
```bash
./backup.sh  # Run the script  
```

### **Automating with Cron Job 🕒**  
To run the script daily at **2 AM**, add it to the cron scheduler:  
```bash
crontab -e
```
```bash
0 2 * * * /path/to/backup.sh  
```

---

## **Conclusion**  
- Shell scripting is essential for DevOps engineers.
- It automates workflows, CI/CD pipelines, and system monitoring.
- Used extensively in AWS, Kubernetes, and Linux administration.
