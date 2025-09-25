# **CCRM: Campus Course & Records Manager**

**A comprehensive, command-line academic administration system built with Java SE and Oracle SQL.**

*An overview of the main menu presented to the administrator upon launching the application.*

CCRM provides a robust and intuitive interface for managing the entire academic lifecycle within an educational institution. From student enrollment to grade processing, this system is a powerful tool for administrators, built on a solid foundation of core Java principles and database management.

## **Core Features**

| Feature | Description |
| :---- | :---- |
| **Student Lifecycle Management** | Effortlessly add new students, update their personal and academic records, and manage their enrollment status (e.g., active, graduated). |
| **Curriculum Management** | A complete suite for creating, listing, and modifying courses. Easily assign qualified instructors to specific subjects and semesters. |
| **Smart Enrollment System** | A streamlined process for enrolling and unenrolling students, with built-in academic governance rules like credit limit enforcement to prevent over-enrollment. |
| **Academic Performance & Reporting** | Record student grades for each course and generate official, detailed academic transcripts on-demand. |
| **Data Integrity & Portability** | Includes crucial utilities for importing and exporting core data (students, courses, etc.) in CSV format. Create timestamped .zip backups for disaster recovery. |

## **Technical Architecture & Concepts**

This project is a practical showcase of fundamental software engineering principles and advanced Java features.

| Concept/Pattern | Implementation & Purpose |
| :---- | :---- |
| **Object-Oriented Pillars** | **Encapsulation, Inheritance, Polymorphism, and Abstraction** are demonstrated through the Person, Student, and Instructor class hierarchy. |
| **Modern I/O (NIO.2)** | ImportExportService.java and BackupService.java use the java.nio.file package for high-performance, non-blocking file operations. |
| **Database Connectivity (JDBC)** | The application communicates with an Oracle database using the Java Database Connectivity API for all data persistence. |
| **Lambda Expressions & Streams** | CourseService.java leverages lambda expressions for concise, functional-style filtering of course data based on various criteria. |
| **Design Patterns** | Includes the **Singleton Pattern** (AppConfig.java) for a single configuration source and the **Builder Pattern** (Course.java) for robust object construction. |
| **Custom Exception Handling** | The system uses specific, custom exceptions like MaxCreditLimitExceededException to manage application-specific errors gracefully. |

## **Getting Started**

### **1\. Prerequisites**

* **Java Development Kit (JDK)**: Version 11 or higher.  
* **Oracle Database**: An active and accessible Oracle database instance.

### **2\. Database Setup**

Connect to your Oracle database with administrative privileges and create the dedicated user for the application:

CREATE USER ccrm\_user IDENTIFIED BY ccrm\_pass;  
GRANT CONNECT, RESOURCE, DBA TO ccrm\_user;

*Note: The application will automatically create the necessary tables on its first run.*

### **3\. Compilation**

From the project's root directory, execute the following command to compile all source files:

javac \-d bin \-cp "lib/ojdbc17.jar" src/edu/ccrm/cli/\*.java src/edu/ccrm/config/\*.java src/edu/ccrm/domain/\*.java src/edu/ccrm/exception/\*.java src/edu/ccrm/io/\*.java src/edu/ccrm/service/\*.java src/edu/ccrm/util/\*.java

### **4\. Launching CCRM**

Run the application from the command line using the following command:

java \-cp "bin;lib/ojdbc17.jar" edu.ccrm.cli.Main

To enable assertions for debugging, use the \-ea flag:

java \-ea \-cp "bin;lib/ojdbc17.jar" edu.ccrm.cli.Main

## **Java Ecosystem Primer**

A quick overview of the key components of the Java platform.

#### **JDK vs. JRE vs. JVM**

| Component | Full Name | Purpose |
| :---- | :---- | :---- |
| **JVM** | Java Virtual Machine | An abstract machine that provides the runtime environment to execute Java bytecode. |
| **JRE** | Java Runtime Environment | Contains the JVM, libraries, and components needed to **run** Java applications. |
| **JDK** | Java Development Kit | A superset of the JRE; includes everything needed to **develop** Java applications (compiler, debugger, etc.). |

#### **Java Editions: SE vs. EE vs. ME**

| Edition | Full Name | Primary Use Case |
| :---- | :---- | :---- |
| **SE** | Standard Edition | The core Java platform for desktop, server, and console applications (used in this project). |
| **EE** | Enterprise Edition | A superset of SE with APIs for large-scale, distributed enterprise applications. |
| **ME** | Micro Edition | A subset of SE for resource-constrained devices like mobile phones and embedded systems. |

**Developed by Aryan Puri**

*This project was created as part of the "Programming in Java" course on the Vityarthi portal.*