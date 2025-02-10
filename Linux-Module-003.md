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

## **2. Getting Started with Shell Scripting**  

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

### **Declaring and Using Variables**  

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

### **Performing Arithmetic Operations**  

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

### **Using Conditional Statements**  

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

### **Using a `for` Loop**  

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


## **9. Shell script to `install Docker` on an **Ubuntu 24.04 LTS** machine.**  

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

## **9. Shell script to `Uninstall Docker` on an **Ubuntu 24.04 LTS** machine.**  

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
## **Sample Shell Script for System Backup 💾**

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
