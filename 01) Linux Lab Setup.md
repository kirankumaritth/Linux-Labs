## Virtual Machine (VM) Setup for Individual Users  

### **1st Priority: Virtualization and Linux Installation**  
Virtualization allows you to run Linux within another operating system using dedicated software.  

### **Popular Virtualization Tools:**  
- **VirtualBox** (Free)  
- **VMware Workstation/Player**  
- **Hyper-V** (Built-in for Windows)  

---

## **Setting Up a Virtual Machine (VM) Using VirtualBox**  
This guide walks you through installing VirtualBox on your laptop and setting up an Ubuntu virtual machine for practical labs.  

### **Step-by-Step Guide:**  
1. **Install VirtualBox** – Download and install [VirtualBox](https://www.virtualbox.org/) for your OS.  
2. **Download Ubuntu ISO** – Get the latest [Ubuntu Desktop ISO](https://ubuntu.com/download/desktop).  
3. **Create a New Virtual Machine**  
   - Open VirtualBox and click **"New"**.  
   - Set a name (e.g., "Ubuntu VM") and choose **Linux → Ubuntu (64-bit)**.  
   - Allocate RAM (at least **2GB**, preferably **4GB+**).  
   - Create a virtual hard disk (minimum **20GB**).  
4. **Configure VM Settings**  
   - Go to **Settings → System** and enable **EFI** (if required).  
   - Under **Display**, increase **Video Memory** for better performance.  
   - Attach the Ubuntu ISO in **Storage → Optical Drive**.  
5. **Install Ubuntu OS**  
   - Start the VM and boot from the Ubuntu ISO.  
   - Follow the installation prompts (**Install Ubuntu**, choose language, configure partitions).  
   - Set username, password, and complete the installation.  
6. **Post-Installation Configuration**  
   - Install VirtualBox Guest Additions for better resolution and seamless integration.  
   - Update Ubuntu using:  
     ```bash
     sudo apt update && sudo apt upgrade -y
     ```
   - Install essential tools for labs as needed.  

For a detailed official guide, refer to [Ubuntu's VirtualBox Tutorial](https://ubuntu.com/tutorials/how-to-run-ubuntu-desktop-on-a-virtual-machine-using-virtualbox#1-overview).
