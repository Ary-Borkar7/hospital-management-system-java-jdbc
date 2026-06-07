# Hospital Management System

Console-based Hospital Management System built using Java, JDBC and MySQL.

## Features
- Add new patients
- View all patients
- View all doctors
- Book appointments between patients and doctors
- Check doctor availability by date

## Tech Stack
- **Language**: Java
- **Database**: MySQL
- **Connectivity**: JDBC
- **IDE**: IntelliJ IDEA

## Database Setup
1. Create a MySQL database named `hospital`
2. Create tables `patients`, `doctors`, `appointments`

```sql
CREATE DATABASE hospital;

USE hospital;

CREATE TABLE patients (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    age INT,
    gender VARCHAR(10)
);

CREATE TABLE doctors (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    specialization VARCHAR(100)
);

CREATE TABLE appointments (
    id INT PRIMARY KEY AUTO_INCREMENT,
    patient_id INT,
    doctor_id INT,
    appointment_date DATE,
    FOREIGN KEY (patient_id) REFERENCES patients(id),
    FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);
