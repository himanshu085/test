# POC for Frontend

### This document provides Proof-of-Concept (POC) of frontend Setup and run the App in detail.

| **Author** | **Created on** | **Version** | **Last updated by** | **Last Edited On** | **Level**          | **Reviewer**    |
|------------|----------------|-------------|---------------------|--------------------|--------------------|-----------------|
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-27         | Internal Reviewer  | Komal Jaiswal   |
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-27         | L0                 | Imran           |
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-27         | L1                 | Shashi          |
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-27         | L2                 | Mahesh Kumar    |

---

## Table of Contents
- [Introduction](#introduction)
- [Purpose](#purpose)
- [Installation Steps](#installation-steps)
- [Contact Information](#contact-information)
- [References](#references)

---

## Introduction
In [OT-Microservices](https://github.com/OT-MICROSERVICES) stack, the Frontend API is built on ReactJS which integrates with other APIs of the application.

## Purpose
This document outlines the step-by-step process for deploying a Node.js-based frontend application, utilizing the necessary dependencies, and ensuring the application is up and running.
The purpose of this application deployment process is to set up the environment for the frontend application, handle the necessary dependencies, and ensure that it is fully operational.


## Installation Steps
For the Frontend PoC, follow the steps mentioned below:

###  Update Packages
First step is to update the packages (instance type t2.small, volume 20GB):
```sh
sudo apt update
sudo apt upgrade -y
```

###  Clone the Repository
```sh
git clone https://github.com/OT-MICROSERVICES/frontend.git
cd frontend
```
![Screenshot from 2025-04-26 21-01-30](https://github.com/user-attachments/assets/16095d21-023d-435b-911e-4bf9712455d0)


###  Install Node.js
```sh
sudo apt install nodejs -y
nodejs -v
```
![Screenshot from 2025-04-26 21-04-27](https://github.com/user-attachments/assets/48b6e8f6-be31-4ccf-af75-7aa575cb0898)


###  Install NPM
```sh
sudo apt install npm
npm -v
```
![Screenshot from 2025-04-26 21-06-47](https://github.com/user-attachments/assets/3e21056f-1e0a-47eb-a0c0-4b3340fcef11)

###  Edit the package.json
In the `package.json`, replace the proxy IP with your public VM IP address along with the specified port.

```sh
vi package.json
```

![Screenshot from 2025-04-26 21-10-32](https://github.com/user-attachments/assets/ba0876e5-f852-4534-a17d-422784c273db)

###  Build the Application
For building the application, use the `make` command from the Makefile:
```sh
make build
```
If you encounter an OpenSSL error, run:
```sh
export NODE_OPTIONS=--openssl-legacy-provider
```
![Screenshot from 2025-04-26 21-14-23](https://github.com/user-attachments/assets/e03c8618-acce-4b28-a892-7fb932c2415f)

###  Run the Application
To run the application:
```sh
npm start
```
![Screenshot from 2025-04-26 21-15-47](https://github.com/user-attachments/assets/3c3d4518-42f5-4a3d-8c5e-e79cc1c0464d)

###  Output
Access the application via the public IP address of the VM in a browser.
```
http://localhost/pubic-ip:3000
```

![Screenshot from 2025-04-26 21-16-31](https://github.com/user-attachments/assets/5a719dec-5a47-4d6a-80ef-644bd82ed977)

---

## Contact Information
| Name              | Email Address                                   |
|-------------------|--------------------------------------------------|
| Himanshu Parashar | himanshu.parashar.snaatak@mygurukulam.co         |

---

## References

| Topic                | Link                                                                 | Description                                               |
|----------------------|----------------------------------------------------------------------|-----------------------------------------------------------|
| Frontend Application | https://github.com/OT-MICROSERVICES/frontend                         | Document format followed from this link.                 |

