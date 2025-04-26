# Frontend POC
### This document provides Proof-of-Concept (POC) of frontend in detail.

| **Author** | **Created on** | **Version** | **Last updated by** | **Last Edited On** | **Level**          | **Reviewer**    |
|------------|----------------|-------------|---------------------|--------------------|--------------------|-----------------|
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-25         | Internal Reviewer  | Komal Jaiswal   |
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-25         | L0                 | Imran           |
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-25         | L1                 | Shashi          |
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-25         | L2                 | Mahesh Kumar    |

---

## Table of Contents
- [Introduction](#introduction)
- [Purpose](#purpose)
- [System Requirements](#system-requirements)
- [Pre-requisites](#pre-requisites)
- [Architecture](#architecture)
- [Installation Steps](#installation-steps)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)

---

## Introduction
In [OT-Microservices](https://github.com/OT-MICROSERVICES) stack, the Frontend API is built on ReactJS which integrates with other APIs of the application.

## Purpose
The frontend web is a REACTJS-based application serving as the user interface of [OT-Microservices](https://github.com/OT-MICROSERVICES) stack.  
This application supports cross-platform and can be executed on multiple OS as long as a JavaScript runtime environment is available.  
A ReactJS-based web framework for complete webpage-based operations.  
Test case integration for application functionality verification.

## System Requirements
| System Requirement | Minimum Requirement |
|--------------------|----------------------|
| **OS**              | Ubuntu or other Linux-based OS |
| **Disk space**      | 20 GB |
| **RAM**             | 4 GB |
| **Processor**       | Dual-core recommended |
| **Instance Type**   | t2.small |

## Pre-requisites
| Dependencies | Details|
|--------------|--------|
| **REST APIs** | The frontend application has dependencies on other REST APIs of OT-Microservices like Employee, Attendance, and Salary APIs which need to be configured. |
| **Node.js**   | Provides the runtime environment for executing JavaScript on the server-side and building and packaging React code. |
| **NPM (Node Package Manager)** | Used to install, manage, and run dependencies (JavaScript libraries and tools) that the application depends upon. NPM helps manage these dependencies by adding them to a package.json file, which lists all the libraries our application depends on. |

## Architecture

![Architecture](https://github.com/OT-MICROSERVICES/frontend/blob/main/static/frontend.png?raw=true)

## Installation Steps
For the Frontend PoC, follow the steps mentioned below:

### - Update Packages
First step is to update the packages (instance type t2.small, volume 20GB):
```sh
sudo apt update
sudo apt list --upgradable
```

### - Clone the Repository
```sh
git clone https://github.com/OT-MICROSERVICES/frontend.git
cd frontend
```

### - Install Node.js
```sh
sudo apt update
sudo apt install nodejs -y
nodejs -v
```

### - Install NPM
```sh
sudo apt install npm
npm -v
```

### - Create Directory and `index.html`
Create a directory named `public` inside the `frontend` directory and create an `index.html` file with the following content:

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>React Frontend App</title>
</head>

<body>
  <div id="root"></div>
  <h1>Welcome to Frontend Web Page</h1>
</body>

</html>
```

### - Edit the package.json
In the `package.json`, replace the proxy IP with your public VM IP address along with the specified port.

### - Build the Application
For building the application, use the `make` command from the Makefile:
```sh
make build
```
If you encounter an OpenSSL error, run:
```sh
export NODE_OPTIONS=--openssl-legacy-provider
```

### - Run the Application
To run the application:
```sh
npm start
```

### - Output
Access the application via the public IP address of the VM in a browser.

---

## Conclusion
The Frontend API is a robust microservice designed to manage the user interface within the OT-Microservices architecture.  
The API is dynamic and interactive as it is based on ReactJS, a high-performance JavaScript library.

---

## Contact Information
| Name              | Email Address                                   |
|-------------------|--------------------------------------------------|
| Himanshu Parashar | himanshu.parashar.snaatak@mygurukulam.co         |

---

## References
| Links | Description |
|-------|-------------|
| [Node.js Installation Guide](https://nodejs.org/en/download/package-manager/all) | For Node.js Installation |
| [GeeksforGeeks Node.js and NPM Setup](https://www.geeksforgeeks.org/how-to-install-node-js-and-npm-on-ubuntu/) | For NPM Installation |


