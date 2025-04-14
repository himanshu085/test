# 🖥️ Ubuntu OS - Software Management SOP

| Author       | Created on | Version | Last updated by | Last edited on | Internal Reviewer | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|--------------|------------|---------|------------------|----------------|-------------------|-------------|-------------|-------------|
| Himanshu     | 2025-04-14 | 1.0     | Himanshu         | 2025-04-14     |   Komal Jaiswal                |       Imran      |    Shashi         |       Mahesh kumar      |

---

## 📌 Overview

This document outlines the standard procedure for managing software on Ubuntu OS using the `apt` package manager. It covers installing, updating, and removing software packages efficiently and securely.

---

## 🧰 Tools & Commands Used

- `apt` – Advanced Package Tool (primary command-line package manager for Ubuntu)
- `dpkg` – Debian package manager backend used to query package status

---

## 🔐 Prerequisites

- Ubuntu 20.04 or later (LTS recommended)
- User must have `sudo` privileges
- Stable internet connection for accessing repositories

---

## 🔄 Update System

### 🟢 Update Package List
```bash
sudo apt update
```
> Syncs the local package index with the upstream repositories.

---

### 🟡 Upgrade Installed Packages
```bash
sudo apt upgrade
```
> Installs the newest versions of all currently installed packages.

---

### 🔴 Full Upgrade (with dependency resolution)
```bash
sudo apt full-upgrade
```
> Like `upgrade` but removes/installs packages to resolve dependency changes.

---

## ➕ Install Software

### ✅ Basic Installation
```bash
sudo apt install <package-name>
```

**Example:**
```bash
sudo apt install nginx
```

### 🚀 Auto-confirm Installation
```bash
sudo apt install -y <package-name>
```

---

## ➖ Remove Software

### 🗑️ Remove (keep config)
```bash
sudo apt remove <package-name>
```

### 🔥 Purge (remove config too)
```bash
sudo apt purge <package-name>
```

### 🧹 Auto-remove Unused Dependencies
```bash
sudo apt autoremove
```

---

## 🧼 Clean Package Cache

### 🧽 Remove downloaded .deb files
```bash
sudo apt clean
```

### 🗃️ Remove outdated package lists
```bash
sudo apt autoclean
```

---

## 🔍 Search & Inspect Packages

### 🔎 Search for Packages
```bash
apt search <package-name>
```

### 📦 Show Package Info
```bash
apt show <package-name>
```

---

## 📋 List Installed Packages

### 📃 All Installed Packages
```bash
dpkg -l
```

### 🔍 Filter Installed Package
```bash
dpkg -l | grep <package-name>
```

---

## ✅ Best Practices

- Always run `sudo apt update` before installing new software
- Schedule `apt upgrade` or `full-upgrade` periodically
- Use `purge` instead of `remove` when clearing old configs
- Run `autoremove` and `clean` monthly to free up space

---

## 📞 Contact Information

| Name              | Email Address                                   |
|-------------------|--------------------------------------------------|
| Himanshu Parashar | himanshu.parashar.snaatak@mygurukulam.co        |
