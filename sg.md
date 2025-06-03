# Manual Dev Infra setup | Setup Infra for Frontend | Security Group

## Document Metadata

| **Author** | **Created on** | **Version** | **Last updated by** | **Last Edited On** | **Level**          | **Reviewer**    |
|------------|----------------|-------------|----------------------|---------------------|---------------------|------------------|
| Himanshu   | 2025-06-02     | 1.0         | Himanshu             | 2025-06-03          | Internal Reviewer   | Komal Jaiswal    |
| Himanshu   | 2025-06-02     | 1.0         | Himanshu             | 2025-06-03          | L0                  | Imran            |
| Himanshu   | 2025-06-02     | 1.0         | Himanshu             | 2025-06-03          | L1                  | Shashi           |
| Himanshu   | 2025-06-02     | 1.0         | Himanshu             | 2025-06-03          | L2                  | Mahesh Kumar     |

---

## Table of Contents

- [Purpose](#purpose)  
- [Steps Performed with Screenshots](#steps-performed-with-screenshots)  
  - [1. Create Security Group](#1-create-security-group)  
  - [2. Edit Inbound Rule](#2-edit-inbound-rule)  
  - [3. Security Group Created](#3-security-group-created)  
- [Summary](#summary)  
- [Contact Information](#contact-information)  
- [References](#references)

---

## Purpose

To record the manual steps followed during the setup of the **security group for the frontend infrastructure** in the development environment.

---

## Steps Performed with Screenshots

### 1. Create Security Group

> Created a security group with the name:  
**`dev-otms-frontend-sg`**

![Screenshot 1 – Create SG](./Screenshot-from-2025-06-03-17-11-20.png)

---

### 2. Edit Inbound Rule

> Edited the **Inbound Rules** to allow:
>
> - **SSH access on port 22** (for secure shell into EC2)  
> - **Frontend application access on port 3000** (commonly used for React development server)

![Screenshot 2 – Edit Inbound Rules](./Screenshot-from-2025-06-03-17-11-41.png)

---

### 3. Security Group Created

> Security group successfully created and attached to the respective instance or resource.

![Screenshot 3 – Created SG](./Screenshot-from-2025-06-03-17-12-04.png)

---

## Summary

The security group `dev-otms-frontend-sg` was manually created and configured to allow SSH access (port 22) and frontend access (port 3000) in the dev environment.

---

## Contact Information

| Name              | Email Address                                   |
|-------------------|--------------------------------------------------|
| Himanshu Parashar | himanshu.parashar.snaatak@mygurukulam.co         |

---

## References

No external references were used for this documentation. All actions were performed via AWS Console.
