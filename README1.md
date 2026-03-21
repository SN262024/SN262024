# 🚀 VS Code Remote SSH Setup with Azure VM

## 📌 Overview

This project demonstrates how to securely connect to a remote Azure Virtual Machine using VS Code Remote SSH extension. This setup is commonly used in DevOps environments to manage infrastructure remotely.

---

## 🏗️ Architecture

Local Machine (VS Code) → SSH → Azure Virtual Machine

---

## ⚙️ Prerequisites

* VS Code installed
* Remote - SSH Extension installed
* Azure Virtual Machine (Linux)
* Public IP of VM
* SSH Port 22 enabled in NSG
* Username & SSH Key / Password

---

## 🔧 Step-by-Step Setup

### 1. Install Remote SSH Extension

* Open VS Code
* Go to Extensions
* Install **Remote - SSH**

---

### 2. Configure SSH

Open SSH config file:

```bash
Ctrl + Shift + P
Remote-SSH: Open SSH Configuration File
```

Add configuration:

```bash
Host myvm
    HostName <Public-IP>
    User <Username>
    IdentityFile C:\Users\<your-user>\.ssh\id_rsa


### 3. Generate SSH Key (if not available)

```bash
ssh-keygen
```

---

### 4. Copy Public Key to VM

```bash
type C:\Users\<your-user>\.ssh\id_rsa.pub
```

Paste into VM:

```bash
mkdir -p ~/.ssh
nano ~/.ssh/authorized_keys
```

---

### 5. Set Permissions (Linux VM)

```bash
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

---

### 6. Connect to VM

```bash
Ctrl + Shift + P
Remote-SSH: Connect to Host → myvm
```

---

## ✅ Output

* Successfully connected to Azure VM
* VS Code runs directly on remote machine
* No need to install tools locally

---

## 🔥 Benefits

* Secure access using SSH keys
* Industry-standard DevOps workflow
* Remote infrastructure management
* Faster and consistent development environment

---

## ❌ Common Issues

### Permission Denied

* Check SSH key added correctly

### Connection Timeout

* Check NSG port 22
* Verify public IP

---

## 💬 Interview Explanation

"I use VS Code Remote SSH to connect securely to cloud VMs. This allows me to manage infrastructure and run DevOps tools directly on remote machines without local dependencies."

