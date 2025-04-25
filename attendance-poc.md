#    **Attendance API POC**
#    **(OT-MICROSERVICES)**
| Created     |    Version   | Author | Comment | Reviewer | Date |
|:------------------:|:-------------:|:-------------:|:-------------:|:------------------:|:--------:|
| 11-11-2024   | V1   | Mohit Saini | Internal Review | Komal Jaiswal and Amit kumar Nagar| 15-11-24 |
|   |  V2 | Mohit Saini | L0 | Kushi | 21-11-24 |
|  | V3 | Mohit Saini | L1  | Parmod |21-11-24|
| | V4 |  Mohit Saini | L2  | Piyush |5-12-2024 |


## **Table of Contents**

-   [**Introduction**](#introduction)

-   [**Pre-requisites**](#pre-requisites)

-   [**System Requirements**](#system-requirements)

-   **[Dependencies](#dependencies)**

-   **[Important Ports](#important-ports)**

-   [**Architecture**](#architecture)

-   [**Flow Diagram**](#flow-diagram)

-   [**Step by step
    installation**](#step-by-step-installation-of-attendance-api)

-   [**Conclusion**](#conclusion)

-   [**Contacts**](#contact-information)

-   [**References**](#references)

## Introduction

This document explains how to install the Attendance API Service easily. The project is built using Python.

## Pre-requisites

This service needs certain hardware, software, security, and network setup to work properly. These are important to make sure the system runs smoothly, stays secure, and can handle more users as needed.

[PostgreSQL](https://www.postgresql.org/)

[Redis](https://redis.io/)

[Poetry](https://python-poetry.org/)

[Liquibase](docs.liquibase.com/home.html)

## System Requirements

| **Hardware Specifications** | **Minimum**         | **Recommendation**              |
|-----------------------------|---------------------|----------------------------------|
| Processor                  | Dual-core          | Quad-core processor             |
| RAM                        | 4GB                | 8GB or higher                   |
| Disk                       | 20GB               | 50GB or higher                  |
| OS                         | Ubuntu (22.04)     | Latest LTS version of Ubuntu    |
| VM                         |  t2.medium         |  t3.large                       |

## Dependencies

| **Name**     | **Version** | **Description**                                                   |
|--------------|-------------|-------------------------------------------------------------------|
| Poetry       | 1.8.4       | Python package manager for managing dependencies                |
| Liquibase    | 4.30.0      | For managing database migrations and updates.                   |
| PostgreSQL   | 14.13       | Relational database system to store attendance data securely.    |
| Python 3.11  | 3.10.12     | Used for running the core application and managing dependencies. |
| Redis        | 4.6.0       | In-memory key-value store for caching to improve performance.    |
| Gunicorn     | Latest      | WSGI HTTP server to host the Flask application.                 |

## Important Ports

| **Port No.** | **Service**   | **Source Side**       | **Destination Side** | **Uses**                         |
|--------------|---------------|-----------------------|----------------------|----------------------------------|
| 5432         | PostgreSQL    | Application Server    | Database Server      | Accessing PostgreSQL database   |
| 6379         | Redis         | Application Server    | Redis Server         | Caching and in-memory database  |
| 80/443       | HTTP/HTTPS    | Client Browser        | Web Server           | Web browsing and secure connections |
| 8080         | API           | Client/Application    | API Server           | Accessing application APIs      |


## **Architecture**

![image](https://github.com/user-attachments/assets/43af60ba-5103-451f-9bd9-fd96c46c75ba)

## **Flow Diagram**

![image](https://github.com/user-attachments/assets/2de208d6-04c2-4d53-9ac5-5ffaebd7f8ea)


## Step-by-step installation of Attendance API
There are some steps how to set up a virtual machine (VM), install dependencies, configure the database and caching services, and run the `Attendance-api` application. Follow each step carefully to ensure the application is correctly installed and functioning.

### 1.  **First create the instance t2.medium or t3.large.**

### 2.  **Open the port**
![image](https://github.com/user-attachments/assets/736dc842-cbcf-4e8c-abc6-32b9c482ed0d)


### 3.  **Update and Upgrade System Packages**
```bash 
sudo apt update
```
![image](https://github.com/user-attachments/assets/445ea424-4620-4867-baef-365ae53e2eaf)

### 4. **Upgrade OS**
```bash 
sudo apt upgrade -y
```

![image](https://github.com/user-attachments/assets/411268f3-bae1-42a6-8475-1cebdb9ff4c5)

### 5.  **Install Python 3.11 and Dependencies**
```bash 
sudo apt install python3.11 python3.11-dev python3.11-venv -y
```
![image](https://github.com/user-attachments/assets/8907390c-f9cf-4133-8961-3e64e97c24df)

### 6.  **Install Poetry (Python Dependency Manager)**
```bash 
curl -sSL https://install.python-poetry.org | POETRY_VERSION=1.8.4 python3 -
```
![image](https://github.com/user-attachments/assets/d59f8d34-064f-4fb9-bc57-19efca779603)


### 7.  **Updating PATH in .bashrc**

```bash 
nano ~/.bashrc
```

```bash 
export PATH="$HOME/.local/bin:$PATH"
```
![image](https://github.com/user-attachments/assets/b542ca93-3680-4fbd-9a17-bb209b1808bc)

```bash
source ~/.bashrc
```

### 8.  **Check Poetry Version**
```bash 
poetry --version
```
![image](https://github.com/user-attachments/assets/1e0d7c78-4576-4bc8-a069-883e4623a3c5)

### 9.  **Install PostgreSQL**

```bash 
sudo apt install postgresql postgresql-contrib -y
```
![image](https://github.com/user-attachments/assets/11ff5d4f-3814-4d9b-8365-47f036815e73)


### 10. **Start and Enable PostgreSQL Service**

```bash 
sudo systemctl start postgresql
```


```bash 
sudo systemctl enable postgresql
```
![image](https://github.com/user-attachments/assets/2de8f897-1cd4-493f-ab35-dd9a400d7051)


```bash 
sudo systemctl status postgresql
```

### 11. **Install Redis Server**

```bash 
sudo apt install redis-server -y
```

![image](https://github.com/user-attachments/assets/e02ff69a-5a7b-4637-ba55-3ae7c4989cf4)

### 12. **Start and Enable Redis Service**

```bash 
sudo systemctl start redis
```

```bash 
sudo systemctl status redis
```

### 13. **Clone GitHub Repository**
```bash 
git clone https://github.com/OT-MICROSERVICES/attendance-api
```

### 14. **Change to the Project Directory**

```bash 
cd attendance-api
```
![image](https://github.com/user-attachments/assets/c037de45-f8e4-43e2-9cc3-a5b630233c8e)

### 15. **Install Poetry for the Project**

```bash 
sudo apt install python3-poetry
```
![image](https://github.com/user-attachments/assets/4cda9633-199f-42c8-a320-6eda3c5fc1d6)


### 16. **Install Project Dependencies Using Poetry**

```bash 
poetry install
```
![image](https://github.com/user-attachments/assets/341b87aa-8615-4320-b695-ae417a17b154)


### 17. **Modify pyproject.toml to Include Specific Packages**

```bash 
vi pyproject.toml
```
![image](https://github.com/user-attachments/assets/8a75c49a-79fe-484f-ae68-4f971625912b)


change the project models as per mentioned snapshot
 ```
packages = [
        {include = "models"},
        {include = "router"},
        {include = "client"},
        {include = "utils"},
]
```

### 18. **Install PostgreSQL Development Libraries**

```bash 
sudo apt install libpq-dev
```

![image](https://github.com/user-attachments/assets/db662ed0-f489-4893-9ca1-45b9837c79fa)

### 19. **Show Installed Poetry Packages**

```bash 
poetry show
```
![image](https://github.com/user-attachments/assets/8d54b5e8-a366-45a4-8dca-1fd7e40cf439)

### 20. **Install Liquibase (Database Change Management)**

```bash 
sudo snap install liquibase
```
![image](https://github.com/user-attachments/assets/4b816918-f4eb-4722-ab0a-2b916939fe53)


### 21. **Check Liquibase Version**

```bash 
liquibase \--version
```
![image](https://github.com/user-attachments/assets/93ad2373-ca17-4e10-9fb0-1d00e13e3940)


### 22. **Run Database Migrations Using Liquibase**

```bash 
make run-migrations
```

![image](https://github.com/user-attachments/assets/fba85229-7391-40cf-b368-a50d41f28c7e)

### 23. **Update PostgreSQL Database Using Liquibase**

```bash 
liquibase \--changeLogFile=db-changelog.xml--driver=org.postgresql.Driver--url=jdbc:postgresql://18.208.150.188:5432/attendance_db--username=postgres --password=password update
```
![image](https://github.com/user-attachments/assets/ad091666-4f07-439f-8312-1ad5db6967cd)


### 24. **Download PostgreSQL JDBC Driver**
```bash 
Wget [https://jdbc.postgresql.org/download/postgresql-42.5.4.jar -P /home/ubuntu/attendance-api/liquibase_lib/](https://jdbc.postgresql.org/download/postgresql-42.5.4.jar%20-P%20/home/ubuntu/attendance-api/liquibase_lib/)
```
![image](https://github.com/user-attachments/assets/f33959df-d72e-451b-baca-31500899b3d7)


### 25. **Modify PostgreSQL pg_hba.conf File for Remote Connections**

```bash 
sudo vi /etc/postgresql/14/main/pg_hba.conf
```
![image](https://github.com/user-attachments/assets/981363f4-dae1-4b0a-98f0-64fde0412b5a)


### 26. **Edit Liquibase Properties**

```bash 
vi liquibase.properties
```


### 27. **Check PostgreSQL Server Listening on Port 5432**

```bash 
sudo netstat -plnt \| grep 5432
```
![image](https://github.com/user-attachments/assets/4613979a-a412-4123-a93d-539dc72e576a)

```bash 
Log in to PostgreSQL as postgres User
```

```bash 
sudo -u postgres psql
```

### 28. **Alter PostgreSQL User Password**

```bash 
ALTER USER postgres WITH PASSWORD \'password\';
```
![image](https://github.com/user-attachments/assets/25d9626c-4fbb-4e98-8424-baf9c8571714)



Create a New Database in PostgreSQL

```bash 
CREATE DATABASE attendance_db;
```


### 29. **Run Liquibase Migrations**

```bash 
liquibase \--changeLogFile=db-changelog.xml update
```

![image](https://github.com/user-attachments/assets/cc9d94cb-b63d-4006-8ddc-59f18bef178b)

### 30. **Install Required Python Packages Using pip**

```bash 
pip install python-json-logger flaskpoetry flasgger prometheus_flask_exporter voluptuous psycopg2 redis flask-caching peewee
```

### 31. **Run the Flask Application Using Gunicorn**

```bash 
gunicorn app:app \--log-config log.conf -b 0.0.0.0:8080
```
![image](https://github.com/user-attachments/assets/acc8de4d-e031-4717-9029-7406d2714e50)

# Conclusion

This API is a tool that helps businesses keep track of their employees' attendance. It's designed to be easy to use, reliable, and secure. By using this API, we can automate the process of recording attendance, generating reports, and sending reminders.

# Contact Information

| **Name**       | **Email Address**            |
|-----------------|------------------------------|
| Mohit Saini    | <it.mohitsaini@gmail.com>     |

# References

| **Link**                                                                                                                     | **Description**                                    |
|-----------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| [How to install and configure PostgreSQL on Ubuntu 20.04](https://medium.com/devops-technical-notes-and-manuals/how-to-install-and-configure-postgresql-on-ubuntu-20-04-4fd3cf072d6f) | PostgreSQL installation and configuration       |
| [How to install Liquibase Database DevOps](https://chandrapurnimabhatnagar.medium.com/how-to-install-liquibase-database-devops-34ca9a6d9705) | Liquibase installation                          |
| [Redis POC Documentation](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Redis/Redis%20POC/README.md) | Redis                                           |
