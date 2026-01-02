# Spring Boot Backend Deployment Guide for Windows

## Part 1: Deploying Locally

### Prerequisites

- Java Development Kit (JDK 8 or higher) installed.
- Maven installed.
- Spring Boot application source code or JAR file.

### Step 1: Install Java

1. Verify if Java is installed by running the following command in **Command Prompt**:

   ```bash
   java -version
   ```

If Java is not installed, download and install the JDK from Oracle JDK Downloads or OpenJDK.

After installing Java, verify the installation again:

```bash

java -version
```

## Step 2: Install Maven

Verify if Maven is installed by running the following command in Command Prompt:

```bash

mvn -version
```

If Maven is not installed, follow these steps:

Download Maven from the official Maven website.

Extract the archive to a directory of your choice (e.g., C:\Program Files\Apache\maven).

Set the MAVEN_HOME environment variable and add the bin directory to the PATH environment variable.

Example for setting environment variables:

Right-click on This PC and select Properties.

Click Advanced system settings and then Environment Variables.

Under System Variables, click New and add:

MAVEN_HOME = C:\Program Files\Apache\maven

Edit Path and add: C:\Program Files\Apache\maven\bin.

## Verify Maven installation:

```bash

mvn -version
```

## Step 3: Build the Spring Boot Application

Open Command Prompt and navigate to your Spring Boot project directory:

```bash

cd C:\path\to\your\project
```

Build the project using Maven:

```bash

mvn clean package -Dmaven.test.skip=true
```

After a successful build, the JAR file will be located in the target/ directory (e.g., target\spring-backend-v1.jar).

## Step 4: Run the Application

Run the generated JAR file by using the following command:

```bash

java -jar target\student-registration-backend-0.0.1-SNAPSHOT.jar
```

The application will start and be accessible at:

http://localhost:8080

### Step 5: Keep the Application Running

To keep the application running in the background, you can use nohup or a similar method. However, Windows does not have a native nohup command. Instead, you can use PowerShell to run the process in the background.

To run the JAR file in the background using PowerShell:

```powershell

Start-Process java -ArgumentList '-jar', 'C:\path\to\your\project\target\spring-backend-v1.jar'

```

This will keep the application running even if you close the PowerShell window.
#new

