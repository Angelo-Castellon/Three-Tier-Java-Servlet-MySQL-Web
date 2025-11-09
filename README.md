# Three-Tier Java Servlet MySQL Web Application

*Enterprise-Grade Role-Based Access Control with Secure Database Integration*

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white) ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white) ![Apache Tomcat](https://img.shields.io/badge/Apache_Tomcat-F8DC75?style=for-the-badge&logo=apache-tomcat&logoColor=black) ![Servlets](https://img.shields.io/badge/Servlets-007396?style=for-the-badge)

Built with proven enterprise technologies:

![Java](https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white) ![JSP](https://img.shields.io/badge/JSP-007396?logo=java&logoColor=white) ![MySQL](https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white) ![Tomcat](https://img.shields.io/badge/Tomcat-F8DC75?logo=apache-tomcat&logoColor=black)

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Configuration](#configuration)
- [Usage](#usage)
- [User Roles](#user-roles)
- [Technologies](#technologies)

## Overview

A role-based enterprise web application built using Java Servlets, JSP, and MySQL, running on Apache Tomcat 11.0. This project demonstrates multi-tier architecture, secure authentication, role-based access control, and comprehensive SQL database integration.

Developed for **CNT 4714 (Spring 2025)** as a showcase of enterprise application design patterns and secure database-driven web development.

## Features

### 🔐 **Secure Authentication**
- Login validation via `AuthenticationServlet` with JDBC integration
- Credential verification against MySQL user database
- Session management for authenticated users
- Custom error handling for failed login attempts

### 👥 **Four-Tier Role-Based Access Control**
- **Root**: Full system access with all privileges
- **Client**: Client-facing operations and queries
- **Data Entry**: Insert and update operations
- **Accountant**: Financial data access and reporting

Each role has unique permissions and access to role-appropriate interfaces.

### 🗃️ **Dynamic SQL Execution**
- Prepared statements for secure parameterized queries
- Callable statements for stored procedure execution
- Protection against SQL injection attacks
- Real-time query execution and result display

### ⚡ **Business Logic Automation**
- Automatic supplier status updates triggered by shipment quantity thresholds
- Data-driven workflows that minimize manual database operations
- Optimized business rules implementation

### 🎯 **Enterprise-Grade Architecture**
- Clean separation between presentation, business logic, and data layers
- Persistent MySQL database backend
- Scalable servlet-based request handling
- JSP templates for dynamic content rendering

## Architecture
```
┌─────────────────┐
│  Presentation   │  JSP Pages (Role-specific UI)
│      Layer      │
└────────┬────────┘
         │
┌────────▼────────┐
│   Business      │  Java Servlets (AuthenticationServlet, Business Logic)
│     Logic       │
└────────┬────────┘
         │
┌────────▼────────┐
│   Data Access   │  JDBC, Prepared Statements, Stored Procedures
│      Layer      │
└────────┬────────┘
         │
┌────────▼────────┐
│   Database      │  MySQL (User credentials, business data)
└─────────────────┘
```

## Getting Started

### Prerequisites

Ensure you have the following installed:

- **Java Development Kit (JDK)**: Version 17 or higher
- **Apache Tomcat**: Version 11.0
- **MySQL Server**: Version 8.0+ recommended
- **IDE**: Eclipse, IntelliJ IDEA, or VS Code with Java extensions (optional)

### Installation

1. **Clone the repository**:
```bash
git clone https://github.com/Angelo-Castellon/Three-Tier-Java-Servlet-MySQL-Web.git
```

2. **Navigate to the project directory**:
```bash
cd Three-Tier-Java-Servlet-MySQL-Web
```

3. **Set up the MySQL database**:
```sql
-- Create database
CREATE DATABASE enterprise_app;

-- Import schema and sample data (adjust path as needed)
SOURCE /path/to/schema.sql;
SOURCE /path/to/data.sql;
```

4. **Configure JDBC connection**:

Edit the database connection properties file or servlet configuration:
```properties
db.url=jdbc:mysql://localhost:3306/enterprise_app
db.username=your_username
db.password=your_password
```

5. **Deploy to Tomcat**:

- Copy the project WAR file to Tomcat's `webapps` directory, or
- Configure your IDE to deploy directly to Tomcat

6. **Start Tomcat**:
```bash
# Linux/Mac
./catalina.sh run

# Windows
catalina.bat run
```

### Configuration

Update the following configuration files as needed:

- `web.xml` - Servlet mappings and security constraints
- `context.xml` - Database connection pool settings
- User credentials - Add/modify users in the MySQL database

## Usage

1. **Access the application**:

Navigate to `http://localhost:8080/Three-Tier-Java-Servlet-MySQL-Web` in your browser.

2. **Login with role-specific credentials**:
```
Root User:
  Username: root
  Password: [configured password]

Client User:
  Username: client
  Password: [configured password]

Data Entry User:
  Username: dataentry
  Password: [configured password]

Accountant User:
  Username: accountant
  Password: [configured password]
```

3. **Perform operations based on your role**:

- Execute SQL queries through the web interface
- View role-appropriate data and reports
- Trigger automated business logic workflows

## User Roles

| Role | Permissions | Use Cases |
|------|-------------|-----------|
| **Root** | Full system access, all CRUD operations | System administration, database management |
| **Client** | Read operations, client-specific queries | Customer data viewing, report generation |
| **Data Entry** | Insert and update operations | Order processing, inventory updates |
| **Accountant** | Financial data access, reporting queries | Financial analysis, audit reports |

## Technologies

**Backend:**
- Java 17+
- Java Servlets (Jakarta EE)
- JSP (JavaServer Pages)
- JDBC (Java Database Connectivity)

**Database:**
- MySQL 8.0+

**Server:**
- Apache Tomcat 11.0

**Frontend:**
- HTML5
- CSS3
- JavaScript (if applicable)

---

**Course**: CNT 4714 - Enterprise Computing (Spring 2025)  
**Institution**: University of Central Florida
