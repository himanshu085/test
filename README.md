# **Installation  of Migration Tool**

| **Author** | **Created on** | **Version** | **Last updated by**|**Last Edited On**|**Level** |**Reviewer** |
|------------|---------------------------|-------------|----------------|-----|-------------|-------------|
| Nikita Joshi|  11-02-2025           | v1          | Nikita Joshi    |11-02-2025    |  L2 | Mahesh Kumar| 
| Nikita Joshi|  11-02-2025           | v1          | Nikita Joshi    |11-02-2025    |  L1 | Shashi | 
| Nikita Joshi|   11-02-2025          | v1          | Nikita Joshi    |11-02-2025    |   L0 | Bhavnesh Baghel | 
| Nikita Joshi|   11-02-2025          | v1          | Nikita Joshi   |11-02-2025    |  Internal Reviewer | Komal Jaiswal |

---

## **Table of Content**
[1. Introduction](#introduction)

[2. Install migrate](#1-install-migrate)

[3. move the file](#2-move-the-file-to-below-location)

[4. check version](#3-check-the-version-of-migrate)

[5. contact Information](#contact-information)


## **Introduction**

The migrate tool is used to manage database schema migrations. It allows you to apply, rollback, and version-control database changes. Below is a detailed guide on how to install and use the migrate tool, including its dependency on jq.

___
### 1. **Install migrate**

- Download the migrate binary for your system. using  the following command:

``` bash
curl -L https://github.com/golang-migrate/migrate/releases/download/v4.15.2/migrate.linux-amd64.tar.gz | tar xvz
```

curl: Downloads the file from the internet.

-L: Follows redirects if the download link changes.

tar xvz: Extracts the downloaded .tar.gz file.
___
### 2. **Move the file to below location**

``` bash
sudo mv migrate /usr/local/bin/migrate
```

sudo mv: Moves the file with superuser privileges.

/usr/local/bin/: A directory for system-wide executable files.
___
#### 3. **Check the version of migrate**

``` bash
migrate --version
```
This command will display the installed version of migrate.
___

### **Contact Information**

| **Name** | **Email address**            | **Github ID**
|----------|-------------------------------|-------------------|
| Nikita joshi    |  jnikita647@gmail.com   | https://github.com/jnikita19  |
