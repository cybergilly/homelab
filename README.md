# Cybersecurity Homelab

Homelab Setup Guide

### 1. **Prerequisites**

#### Hardware Requirements

- **RAM**: Minimum of 8 GB (16 GB recommended)

- **CPU**: Multi-core CPU for efficient virtualization

- **Storage**: At least 100 GB of free space

#### Software Requirements

- **Hypervisor**: VMware Workstation Pro (make sure you have a valid license)

- **Operating System ISOs**: Download the necessary ISO files for the operating systems you wish to deploy.

### 2. **Setting Up Your Homelab**

#### Step 1: Install VMware Workstation Pro

1. **Download**: Navigate to the [VMware Workstation Pro](https://www.vmware.com/products/workstation-pro.html) page.

2. **Install**: Follow the installation instructions suitable for your operating system (Windows/Linux).

#### Step 2: Create Virtual Machines

1. **Open VMware Workstation Pro**.

2. **Create a New Virtual Machine**:

    - Select `File` > `New Virtual Machine`.

    - Choose “Typical” for the configuration.

    - Locate the ISO file for your desired operating system.

3. **Configure the VM**:

    - Allocate memory (use 8 GB or more if possible).

    - Choose the number of CPU cores (2 or more are recommended).

    - Allocate sufficient disk space (at least 40 GB per VM).

#### Step 3: Install Operating Systems

- Boot up each VM and go through the installation process of the operating system as prompted.

### 3. **Networking Configuration**

- To ensure your VMs can communicate with each other and the internet:

    - Set up a **bridged network** or **NAT (Network Address Translation)** configuration in VMware's network settings.

### 4. **Installing Necessary Tools and Applications**

- Based on the purpose of your homelab, install relevant applications. Some examples include:

    - **For a Web Server**: Apache or Nginx.

    - **For a Database Server**: MySQL or PostgreSQL.

    - **For Development**: Docker or Kubernetes.

### 5. **Additional Resources**

- **Learning Resources**:

    - [FreeCodeCamp](https://www.freecodecamp.org) - Great for tutorials on various tech topics.

    - [Udemy](https://www.udemy.com) - Look for homelab-related courses.

- **Community Forums**:

    - [Reddit - Homelab](https://www.reddit.com/r/homelab/) - Share and learn from other homelab-ers.

    - [VMware Community](https://communities.vmware.com) - For troubleshooting and networking advice.

### 6. **Backup and Maintenance**

- Regularly back up your VMs to prevent data loss. Use VMware’s built-in snapshot feature for easy recovery.

- Keep your software and operating systems updated to their latest versions.

### 7. **Experiment and Explore**

- Now that your homelab is up and running, feel free to experiment with different setups and configurations. This is a great opportunity to learn and grow your skills.

---

Feel free to reach out if you have any specific configurations in mind, or if you encounter challenges along the way! What kind of projects are you considering for your homelab?

---

### 2. **Virtual Machines to Set Up**

| VM Name            | OS           | Purpose                                      |
| :----------------- | :----------- | :------------------------------------------- |
| **Kali Linux**     | Debian-based | Penetration testing tools                    |
| **Metasploitable** | Ubuntu       | Vulnerable target for penetration testing    |
| **Windows Server** | Windows      | Active Directory and security configurations |
| **Ubuntu Server**  | Ubuntu       | Hosting vulnerable web applications          |
| **pfSense**        | FreeBSD      | Firewall/router for managing network traffic |

Click to expand Virtual Machines

---

### 3. **Creating Virtual Machines**

1. **Open VMware Workstation Pro**.

2. **Create New Virtual Machine**:

    - Select **Typical** configuration.

    - Choose **Installer disc image file (iso)** and select the ISO file.

3. **Resource Allocation**:

    - Assign appropriate CPU, RAM, and disk space based on the purpose of each VM.

4. **Finish Setup**: Complete the configuration and power on the VM.

Click to expand Creating Virtual Machines

---

### 4. **Networking Setup**

- For the virtual machine network modes:

    - Use **Host-Only** for **Kali Linux** and **Metasploitable** to isolate them.

    - Use **NAT** for **Windows Server** and **Ubuntu Server** to allow internet access.

#### Example Configuration:

- **Kali Linux** and **Metasploitable** → Host-Only

- **Windows Server** → NAT

- **Ubuntu Server** → NAT

Click to expand Networking Setup

---

### 5. **Sample Network Diagram**

```python
+-------------------+
|   Host Machine    |
|         +         |
|   +-----|-----+   |
|   | VMware    |   |
|   +-----------+   |
|         |         |
|    -----------    |
|    | NAT       |  |
|    -----------    |
|         |         |
|         |         |
+-------------------+
   |          |
   |          |
+-----------+ +-------------------+
| Kali      | | Windows Server     |
| Linux     | |                   |
| (Host-Only)| |       (NAT)     |
+-----------+ +-------------------+
   |
   |
+-----------+
| Metasploitable|
|               |
| (Host-Only)   |
+---------------+
```

Click to expand Network Diagram

---

### 6. **Projects for Hands-On Experience**

1. **Penetration Testing**:

    - Use **Kali Linux** to exploit vulnerabilities on **Metasploitable** using Metasploit.

2. **Vulnerability Scanning**:

    - Install **Nessus** or **OpenVAS** on Kali Linux to scan the network and identify weaknesses.

3. **Active Directory Setup**:

    - Configure **Windows Server**, set up Active Directory, and experiment with user/group management and GPOs.

4. **Web Application Testing**:

    - Install a vulnerable web application (e.g., DVWA) on **Ubuntu Server** and practice SQL injection and XSS attacks.

5. **Firewall Configuration**:

    - Set up **pfSense** as a firewall/router and configure rules to control traffic between VMs.

6. **Logging and Monitoring**:

    - Install the **ELK Stack** (Elasticsearch, Logstash, Kibana) on Ubuntu Server to analyze logs generated from other VMs.



---

