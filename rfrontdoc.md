## Frontend Detailed Document

**Author**: Raman Tripathi  
**Created on**: 24-11-24  
**Version**: Version 1  
**Last updated by**: Raman Tripathi  
**Last edited on**: 24-11-24

---

### Purpose

This document provides an overview of the OT-Microservices stack, focusing on the ReactJS-based frontend and its integration with backend services such as Employee, Salary, and Attendance APIs. The architecture is built for scalability, performance, and maintainability, leveraging Redis for caching, ScyllaDB for NoSQL, and PostgreSQL for relational data.

---

### Table of Contents

- [Frontend Web](#frontend-web)
- [Employee API](#employee-api)
- [Salary API](#salary-api)
- [Attendance API](#attendance-api)
- [Redis](#redis)
- [ScyllaDB](#scylladb)
- [PostgreSQL](#postgresql)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)
- [Architecture](#architecture)

---

### Frontend Web

The Frontend Web is the primary user interface for the OT-Microservices stack. It is a ReactJS-based application that allows users to interact with the system through a web browser. Built using the ReactJS framework, it provides a fast, responsive, and dynamic UI that can handle complex user interactions with minimal loading times.

| Component       | Description |
|----------------|-------------|
| **ReactJS**     | A popular JavaScript library for building user interfaces, known for its component-based architecture and efficiency in rendering. React enables developers to build reusable components, enhancing both maintainability and scalability. |
| **Cross-platform** | The frontend is designed to run on any platform that supports modern browsers, ensuring compatibility across multiple operating systems and devices. |
| **Dependencies** | The frontend depends on several backend services (APIs) to fetch and display data in real time. These APIs include the Employee API, Salary API, and Attendance API. |
| **Build process** | The frontend is compiled and optimized for production using npm commands and a Makefile. After building, static files are served through a web server, and the bundled application is deployed. |
| **Rendering Logic** | React's root element, defined in the `index.html` file, is where the React components are rendered. The entire app runs within this div, with backend data dynamically injected into the UI via API calls. |

---

### Employee API

The Employee API is responsible for managing all employee-related data and operations within the system.

| Aspect         | Description |
|----------------|-------------|
| **Functionality** | Handles operations such as employee registration, updating employee information, retrieving employee profiles, and more. Each endpoint corresponds to a specific function, such as `/api/v1/employee/{id}`. |
| **Caching**     | Utilizes Redis for caching frequently requested employee data to reduce database queries and improve performance. |
| **Database**    | All employee-related data is stored in **ScyllaDB**, a NoSQL database optimized for handling large datasets. |

---

### Salary API

The Salary API manages all salary-related operations, including salary calculations, pay slips, and adjustments.

| Aspect         | Description |
|----------------|-------------|
| **Functionality** | Provides endpoints for fetching salary details, calculating deductions and bonuses, and updating salary records, e.g., `/api/v1/salary/{employeeId}`. |
| **Caching**     | Leverages Redis to cache frequently accessed salary data. |
| **Database**    | Uses **ScyllaDB** to manage and store salary data with minimal latency. |

---

### Attendance API

The Attendance API handles employee attendance tracking and management.

| Aspect         | Description |
|----------------|-------------|
| **Functionality** | Offers endpoints for logging attendance (`/api/v1/attendance/log`), viewing history (`/api/v1/attendance/history/{employeeId}`), and calculating hours worked. |
| **Caching**     | Does not heavily rely on Redis due to real-time accuracy requirements. |
| **Database**    | Uses **PostgreSQL** to store attendance records, ensuring data integrity and transactional accuracy. |

---

### Redis

Redis is an in-memory data store used for caching in the OT-Microservices stack.

| Aspect         | Description |
|----------------|-------------|
| **Purpose**     | Used by Employee and Salary APIs to cache frequently accessed data, reducing backend load. |
| **Mechanism**   | APIs check Redis first for cached data before querying the main database. |
| **Cache Invalidation** | Employs strategies to invalidate or update cache entries when data changes. |

---

### ScyllaDB

ScyllaDB is the primary NoSQL database used for storing employee and salary data.

| Aspect         | Description |
|----------------|-------------|
| **NoSQL Database** | Uses a column-family structure similar to Apache Cassandra, enabling efficient data storage. |
| **High Performance** | Designed for high throughput and low latency. |
| **Distributed Architecture** | Supports horizontal scaling and data redundancy across multiple nodes. |

---

### PostgreSQL

PostgreSQL is the relational database used for storing attendance records.

| Aspect         | Description |
|----------------|-------------|
| **Relational Database** | Ideal for managing structured data with relationships. |
| **ACID Compliance** | Ensures data integrity and reliable transaction processing. |
| **Transactional Data** | Efficient at handling time-sensitive, accurate transactional records. |

---

### Conclusion

The OT-Microservices stack combines a ReactJS frontend with backend services using Redis for caching, ScyllaDB for NoSQL, and PostgreSQL for relational data. This ensures scalability, performance, and easy maintenance. The Employee, Salary, and Attendance APIs manage data efficiently, with Redis boosting response times. ScyllaDB and PostgreSQL ensure reliable data storage and retrieval. Together, they provide a high-performing system for managing employee operations seamlessly.

---

### Contact Information

| Name            | Email Address                                      |
|-----------------|----------------------------------------------------|
| Raman Tripathi  | raman.tripathi.snaatak@mygurukulam.co              |

---

### References

| Topic                | Link                                              | Description                            |
|----------------------|---------------------------------------------------|----------------------------------------|
| OT-Microservices Repo| https://github.com/OT-MICROSERVICES              | Opstree OT-Microservices               |
| Frontend Application | https://github.com/OT-MICROSERVICES/frontend     | Document format followed from this link|
