# MariaDB Setup and Configuration Guide for Windows

This guide explains how to set up MariaDB, create a database, and import data from a SQL file on a Windows system.

## 1. Installing MariaDB

Download and Install MariaDB

Visit the MariaDB download page.

Select the appropriate version for Windows and download the installer.

Run the installer and follow the prompts. Choose the default options unless you need custom configurations.

Start MariaDB Service

After installation, the MariaDB service should be running automatically. To verify, follow these steps:

Open the Command Prompt as an Administrator.
Type the following command to check if the MariaDB service is running:

```bash
net start MariaDB

```

If the service is not running, you can start it using:

```bash

net start MariaDB

```

## 2. Securing MariaDB

Open the Command Prompt as Administrator and run the following command to secure your installation:

```bash

mysql_secure_installation
```

Follow the prompts to:
Set a root password.
Remove insecure default users and test databases.
Disable remote root login.

## 3. Setting Up the Database

Open Command Prompt as Administrator and login to MariaDB:

```bash

mysql -u root -p
```

Enter the root password when prompted.

Create a new database and user:

```sql

CREATE DATABASE student_db;
GRANT ALL PRIVILEGES ON springbackend.* TO 'username'@'localhost' IDENTIFIED BY 'your_password';
Replace username and your_password with your desired username and password.
```

Exit MariaDB:

```sql

EXIT;
```

## 4. Importing the Database

To import an SQL file into your new database, use the following command: Open Command Prompt as Administrator and run:

```bash

mysql -u username -p student_db < C:\path\to\student_db.sql
```

Replace C:\path\to\springbackend.sql with the actual path to your SQL file.

Verify the database import by logging back into MariaDB:

```bash

mysql -u username -p
```

Run the following commands to check if the database and tables have been created correctly:

```sql

SHOW DATABASES;
USE student_db;
SHOW TABLES;
SELECT * FROM tbl_workers;
```

Query for table schema

```sql
CREATE TABLE `students` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) DEFAULT NULL,
  `email` varchar(255) DEFAULT NULL,
  `course` varchar(255) DEFAULT NULL,
  `student_class` varchar(255) DEFAULT NULL,
  `percentage` double DEFAULT NULL,
  `branch` varchar(255) DEFAULT NULL,
  `mobile_number` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=80 DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci;
```
#test hh
###2121

