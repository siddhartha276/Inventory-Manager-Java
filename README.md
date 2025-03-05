# Billing and Inventory Management System

## Overview
This project is a **Billing and Inventory Management System** built using **Java (Swing GUI)** with MySQL as the database. It manages product inventory, tracks customer outstanding balances, generates bills, and sends automated email notifications to the manager when a product's stock falls below 10.

## Features
- **Product Inventory Management**: Keeps track of available stock with details such as product name, rate, quantity, and barcode.
- **Billing System**: Generates bills for purchases and maintains records of transactions.
- **Outstanding Customer Balances**: Tracks pending payments and due amounts.
- **Revenue Tracking**: Provides daily, monthly, and yearly revenue summaries.
- **Email Alerts**: Sends an automatic email to the manager when stock levels drop below 10.
- **User Authentication**: Implements login functionality for secure access.

## Technologies Used
- **Java (Swing GUI)** for the user interface.
- **MySQL** for database management.
- **JDBC** for database connectivity.
- **Mail API (mail-1.4.7.jar)** for sending email notifications.
- **mysql-connector-j-8.2.0.jar** for database connectivity.
- **Absolute Layout** for GUI design.

## Database Structure
### Tables and Columns

#### **bill**
| Column Name   | Data Type | Description |
|--------------|-----------|-------------|
| Bill_ID      | INT       | Unique bill identifier |
| paymentMode  | VARCHAR   | Payment method used |
| totalAmount  | DECIMAL   | Total bill amount |
| phoneNumber  | VARCHAR   | Customer phone number |
| bill_date    | DATE      | Date of the bill |

#### **outstanding**
| Column Name   | Data Type | Description |
|--------------|-----------|-------------|
| bill_no      | INT       | Bill number (Foreign Key to bill table) |
| name         | VARCHAR   | Customer name |
| phone_no     | VARCHAR   | Customer phone number |
| total_amount | DECIMAL   | Total outstanding amount |
| paid_amount  | DECIMAL   | Amount paid |
| due_amount   | DECIMAL   | Remaining due amount |
| due_date     | DATE      | Due date for payment |

#### **productdetails**
| Column Name   | Data Type | Description |
|--------------|-----------|-------------|
| Sr No        | INT       | Unique product identifier |
| ProductName  | VARCHAR   | Name of the product |
| Rate         | DECIMAL   | Price per unit |
| Quantity     | INT       | Stock available |
| Barcode      | VARCHAR   | Barcode of the product |

## Installation and Setup
### Prerequisites
- **Java JDK 21** installed.
- **MySQL Server** running.
- **NetBeans or Eclipse IDE** for Java development.
- Required JAR dependencies (**mysql-connector-j-8.2.0.jar**, **mail-1.4.7.jar**).

### Steps to Run the Project
1. **Clone the Repository**:
   ```sh
   git clone https://github.com/yourusername/Billing-Inventory-Management.git
   ```
2. **Import the Project** into NetBeans/Eclipse.
3. **Set Up MySQL Database**:
   - Create a database named `petsglorious`.
   - Import the database schema using the provided SQL script.
4. **Update Database Credentials** in `Billing.java`:
   ```java
   String url = "jdbc:mysql://localhost:3306/petsglorious";
   String user = "your_mysql_username";
   String password = "your_mysql_password";
   ```
5. **Run the Application** from the main class.

## Future Enhancements
- Implement role-based access control (Admin, Manager, Staff).
- Add graphical reports for revenue analysis.
- Develop a web-based version for remote access.

## License
This project is licensed under the **MIT License**.

## Contact
For any inquiries or contributions, reach out to **your.email@example.com**.
