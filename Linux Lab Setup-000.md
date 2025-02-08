---

# **Linux Lab 0: Virtual Machine (VM) Setup for Individual Users**

---

## **1. Introduction**
Virtualization allows users to run multiple operating systems on a single machine, enabling efficient software testing, development, and system administration. This guide provides step-by-step instructions for setting up a virtual machine (VM) using VirtualBox and installing Ubuntu Linux.

## **2. Popular Virtualization Tools**
Below are widely used virtualization platforms:
- **VirtualBox** – Free, open-source, and cross-platform.
- **VMware Workstation/Player** – Paid (Workstation) and free (Player) options available.
- **Hyper-V** – Built-in for Windows Pro and Enterprise editions.

## **3. Setting Up a Virtual Machine Using VirtualBox**
This section outlines the process of installing VirtualBox and setting up an Ubuntu VM.

### **Step 1: Install VirtualBox**
1. Download **VirtualBox** from the [official website](https://www.virtualbox.org/).
2. Install it following the on-screen instructions.

### **Step 2: Download Ubuntu ISO**
1. Visit the [Ubuntu official website](https://ubuntu.com/download/desktop).
2. Download the latest Ubuntu **Desktop ISO** file.

### **Step 3: Create a New Virtual Machine**
1. Open **VirtualBox** and click **"New"**.
2. Set a name (e.g., "Ubuntu VM").
3. Choose **Linux → Ubuntu (64-bit)** as the OS type.
4. Allocate RAM (**Minimum: 2GB; Recommended: 4GB+**).
5. Create a virtual hard disk (**Minimum: 20GB**), selecting **VDI (VirtualBox Disk Image)** format.
6. Choose **Dynamically Allocated** for efficient storage use.

### **Step 4: Configure Virtual Machine Settings**
1. Go to **Settings → System** and enable **EFI** (if required by your system).
2. Under **Display**, increase **Video Memory** to at least **128MB**.
3. Navigate to **Storage → Optical Drive**, click **Add**, and select the Ubuntu ISO file.

### **Step 5: Install Ubuntu on the Virtual Machine**
1. Start the VM and boot from the **Ubuntu ISO**.
2. Select **"Install Ubuntu"**.
3. Follow the setup prompts:
   - Choose **language** and keyboard layout.
   - Select **"Erase disk and install Ubuntu"** (or manual partitioning if needed).
   - Create a username and password.
4. Wait for the installation to complete and restart the VM when prompted.

### **Step 6: Post-Installation Configuration**
1. **Install VirtualBox Guest Additions** for better display and integration:
   ```bash
   sudo apt update && sudo apt install -y virtualbox-guest-utils
   ```
2. **Update Ubuntu** to ensure all software is up to date:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
3. **Install essential tools** for DevOps and development needs:
   ```bash
   sudo apt install -y build-essential curl git
   ```

## **4. Conclusion**
Setting up a VM using VirtualBox is a crucial step for system administrators, developers, and DevOps engineers. This setup provides an isolated environment for testing, development, and automation tasks.

For more details, refer to the [official Ubuntu VirtualBox guide](https://ubuntu.com/tutorials/how-to-run-ubuntu-desktop-on-a-virtual-machine-using-virtualbox#1-overview).
