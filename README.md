
# 🖥️ Ubuntu OS - Software Management SOP

| Author       | Created on | Version | Last updated by | Last edited on | Internal Reviewer | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|--------------|------------|---------|------------------|----------------|-------------------|-------------|-------------|-------------|
| Himanshu     | 2025-04-14 | 1.0     | Himanshu         | 2025-04-14     | Komal Jaiswal     | Imran       | Shashi      | Mahesh Kumar|

---

## 📌 Overview

This document outlines the standard procedure for managing software on Ubuntu OS using the `apt` package manager. It also covers Snap and Flatpak package systems, including installing, updating, and removing software packages efficiently and securely.

---

## 🧰 Tools & Commands Used

- `apt` – Advanced Package Tool (primary command-line package manager for Ubuntu)
- `dpkg` – Debian package manager backend used to query package status
- `snap` – Snap package manager for universal Linux packages
- `flatpak` – Software deployment and package management utility

---

## 🔐 Prerequisites

- Ubuntu 20.04 or later (LTS recommended)
- User must have `sudo` privileges
- Stable internet connection for accessing repositories

---

## 🔄 Update System

### 🟢 Update Package List
```bash
**sudo apt update**
```

### 🟡 Upgrade Installed Packages
```bash
**sudo apt upgrade**
```

### 🔴 Full Upgrade (with dependency resolution)
```bash
**sudo apt full-upgrade**
```

---

## ➕ Install Software

### ✅ Basic Installation
```bash
**sudo apt install <package-name>**
```

### 🚀 Auto-confirm Installation
```bash
**sudo apt install -y <package-name>**
```

---

## ➖ Remove Software

### 🗑️ Remove (keep config)
```bash
**sudo apt remove <package-name>**
```

### 🔥 Purge (remove config too)
```bash
**sudo apt purge <package-name>**
```

### 🧹 Auto-remove Unused Dependencies
```bash
**sudo apt autoremove**
```

---

## 🧼 Clean Package Cache

### 🧽 Remove downloaded .deb files
```bash
**sudo apt clean**
```

### 🗃️ Remove outdated package lists
```bash
**sudo apt autoclean**
```

---

## 🔍 Search & Inspect Packages

### 🔎 Search for Packages
```bash
**apt search <package-name>**
```

### 📦 Show Package Info
```bash
**apt show <package-name>**
```

---

## 📋 List Installed Packages

### 📃 All Installed Packages
```bash
**dpkg -l**
```

### 🔍 Filter Installed Package
```bash
**dpkg -l | grep <package-name>**
```

---

## 📦 Snap Commands

### ➕ Install a Snap Package
```bash
**sudo snap install <package-name>**
```

### 🔁 Refresh/Update Snap Packages
```bash
**sudo snap refresh**
```

### ➖ Remove a Snap Package
```bash
**sudo snap remove <package-name>**
```

### 📋 List Installed Snaps
```bash
**snap list**
```

---

## 📦 Flatpak Commands

### ➕ Install Flatpak (if not installed)
```bash
**sudo apt install flatpak**
```

### ➕ Add Flathub Repository
```bash
**flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo**
```

### 🟢 Install a Flatpak App
```bash
**flatpak install flathub <app-id>**
```

### 🔁 Update Flatpak Apps
```bash
**flatpak update**
```

### ➖ Remove a Flatpak App
```bash
**flatpak uninstall <app-id>**
```

### 📋 List Installed Flatpaks
```bash
**flatpak list**
```

---

## ✅ Best Practices

### 📦 APT
- Always run **`sudo apt update`** before installing new software  
- Schedule **`apt upgrade`** or **`apt full-upgrade`** periodically  
- Use **`apt purge`** instead of **`apt remove`** when clearing old configs  
- Run **`apt autoremove`** and **`apt clean`** monthly to free up space  

---

### 🛠️ Snap
- Use **`--classic`** flag only for trusted apps needing full system access  
- Run **`sudo snap refresh`** weekly to ensure apps are updated  
- Use **`snap list`** to audit installed applications periodically  

---

### 📦 Flatpak
- Always enable the Flathub repository for a wide range of apps  
- Regularly run **`flatpak update`** to keep apps secure  
- Uninstall apps you no longer use with **`flatpak uninstall`**

---

## 📞 Contact Information

| Name              | Email Address                                   |
|-------------------|--------------------------------------------------|
| Himanshu Parashar | himanshu.parashar.snaatak@mygurukulam.co        |

---

## 🔗 References

- [APT - Ubuntu Manpage](https://manpages.ubuntu.com/manpages/jammy/en/man8/apt.8.html)
- [dpkg - Debian Package Manager](https://manpages.ubuntu.com/manpages/jammy/en/man1/dpkg.1.html)
- [Snapcraft Documentation](https://snapcraft.io/docs)
- [Flatpak Documentation](https://docs.flatpak.org/en/latest/)
- [Debian Wiki: APT](https://wiki.debian.org/Teams/Apt)
- [Flatpak on Flathub](https://flathub.org/)
- [Snap Package List](https://snapcraft.io/store)
