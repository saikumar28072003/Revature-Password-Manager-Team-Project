# Revature-Password-Manager-Team-Project

Revature Password Manager
A secure full-stack password management application that allows users to store, manage, and retrieve credentials safely using encryption and authentication mechanisms.
The system follows a two-application architecture with separate frontend and backend Spring Boot applications communicating via REST APIs.

Project Overview
Managing multiple passwords across different platforms is difficult and insecure. Many users reuse passwords or store them in unsafe locations.

Revature Password Manager provides a secure vault system that allows users to:
Store credentials securely
Encrypt sensitive data
Enable two-factor authentication
Recover accounts using security questions
Manage profile and security settings

The application implements enterprise-level security practices and layered architecture.
Features

User Management:
Secure user registration
Login with authentication validation
Password recovery using security questions

Vault Management:
Add password entries
Edit password entries
Delete password entries
Categorize credentials
Store notes for accounts

Security Features:
AES encryption for stored passwords
BCrypt hashing for master password
Two-Factor Authentication (2FA)
OTP verification
Security questions for account recovery

Profile Management:
Update email and phone number
Enable or disable two-factor authentication
Change master password securely

Validation:
Frontend form validation
Backend DTO validation
Field-level error handling

System Architecture
The application uses a two-application architecture.

Browser
↓
Frontend Application (Spring Boot + Thymeleaf)
↓ REST API Calls
Backend Application (Spring Boot REST API)
↓
Service Layer
↓
Repository Layer (JPA/Hibernate)
↓
Oracle Database

Technology Stack
Backend
Java 17
Spring Boot
Spring Data JPA
Hibernate
Oracle 21c Database
AES Encryption
BCrypt Password Hashing

Frontend
Spring Boot (separate application)
Thymeleaf
Bootstrap 5
JavaScript
Custom validation scripts

Security
AES encryption for stored credentials
BCrypt hashing for master password
OTP verification for sensitive operations

Database Design
Main entities used in the system:

Users:
id
username
email
phoneNumber
masterPasswordHash
twoFactorEnabled

SecurityQuestions:
id
userId
question
answerHash

PasswordEntries:
id
userId
accountName
loginUsername
encryptedPassword
websiteUrl
category
notes

OTPVerification:
id
userId
otpCode
expiryTime

Relationships
User (1) → (Many) PasswordEntries
User (1) → (3) SecurityQuestions

Security Implementation
The project uses multiple layers of security.
Encryption
AES encryption is used to store vault passwords securely.
Password Protection
Master passwords are hashed using BCrypt before storage.
Two-Factor Authentication
OTP verification is required for sensitive operations.

Validation
Backend DTO validation prevents invalid data submission.
Frontend validation improves user experience.

Project Structure:

Backend Application
config
controller
service
repository
entity
dto
mapper
security
exception
util

Frontend Application
config
controller
model
templates
layout
static

How to Run the Project:

Prerequisites
Java 17 or later
Maven
Oracle 21c Database
Spring Tool Suite or IntelliJ

Steps:
Clone the repository
git clone https://github.com/saikumar28072003/Revature-Password-Manager-Team-Project.git

Start the Oracle 21c database.
Run the backend application (port 8080).
Run the frontend application (port 8081).

Open the application in a browser
http://localhost:8081

Demonstration Flow:

Register a new user
Login with credentials
Verify OTP (if enabled)
Add a password to the vault
View stored credentials
Update profile information
Change master password
Enable or disable two-factor authentication
Recover account using security questions

Team Members
Member 1 – Security & Config Module (Team Lead)
Member 2 – User & Authentication Module
Member 3 – Vault Module
Member 4 – Encryption Integration Module
Member 5 – Audit Module
Member 6 – Frontend UI Development

Future Improvements:
Email-based OTP delivery
Cloud deployment (AWS or Azure)
Docker containerization
Role-based access control
Secure password sharing between users

Conclusion
Revature Password Manager demonstrates a secure and scalable architecture for credential management. The system integrates encryption, authentication, and validation mechanisms to ensure safe storage and management of user credentials.
