# Universal Banking API

## Overview

The **Universal Banking API** is a MuleSoft RESTful application that provides core digital banking services such as account management, deposits, withdrawals, transaction history, health monitoring, and WhatsApp notifications. It is designed using MuleSoft's API-led approach and integrates with Snowflake for data storage.

---

# Features

* Account Creation
* Retrieve All Accounts
* Retrieve Account by Account Number
* Update Account Details
* Delete Account
* Deposit Money
* Withdraw Money
* View Transaction History
* API Health Check
* WhatsApp Notification Integration
* JSON and XML Support
* Snowflake Database Integration
* Error Handling
* Logging and Monitoring
* SMS Notifications
* Email Notifications
* PDF Bank Statements
* Loan Management

---

# Technology Stack

| Technology      | Version         |
| --------------- | --------------- |
| Mule Runtime    | 4.x             |
| Anypoint Studio | 7.x             |
| DataWeave       | 2.0             |
| RAML            | 1.0             |
| Java            | 17              |
| Maven           | 3.x             |
| Snowflake       | Latest          |
| Git             | Version Control |

---

# Architecture

```
                Client Applications
      (Web | Mobile | Postman | Third-Party)

                     │
                     ▼

         Universal Banking API (MuleSoft)

                     │
     ┌───────────────┼────────────────┐
     │               │                │
 Snowflake DB   WhatsApp Service   Logging

```

---

# Project Structure

```
universal-banking-api
│
├── src
│   ├── main
│   │   ├── mule
│   │   ├── resources
│   │   ├── api
│   │   └── dwl
│   │
│   └── test
│
├── pom.xml
├── README.md
└── mule-artifact.json
```

---

# API Endpoints

## Health

| Method | Endpoint |
| ------ | -------- |
| GET    | /health  |

Returns application health status.

---

## Accounts

### Create Account

```
POST /accounts
```

Query Parameters

* adharNumber
* bankName

Request Body

```json
{
  "FullName":"John Doe",
  "dateOfBirth":"1998-05-12",
  "mobileNumber":"9876543210",
  "email":"john@example.com",
  "address":"Hyderabad"
}
```

---

### Get All Accounts

```
GET /accounts
```

Optional Query Parameter

```
status=ACTIVE
```

---

### Get Account

```
GET /accounts/{accountNumber}
```

---

### Update Account

```
PATCH /accounts/{accountNumber}
```

---

### Delete Account

```
DELETE /accounts/{accountNumber}
```

---

## Deposit

```
POST /accounts/{accountNumber}/deposit
```

Example

```json
{
  "amount":1000
}
```

---

## Withdraw

```
POST /accounts/{accountNumber}/withdraw
```

Example

```json
{
  "amount":500
}
```

---

## Transaction History

```
GET /accounts/{accountNumber}/transactions
```

---

## WhatsApp Notification

```
POST /assistance/whatsapp
```

Query Parameter

```
token=<UltraMsg Token>
```

Example Request

```json
{
  "mobileNumber":"919876543210",
  "message":"Welcome to Universal Banking API."
}
```

---

# Supported Banks

* SBI
* HDFC
* ICICI
* AXIS
* YES Bank
* Union Bank of India
* Bank of Baroda
* Punjab National Bank
* Canara Bank
* Indian Bank
* UCO Bank
* Central Bank of India
* IOB
* Federal Bank
* IndusInd Bank
* APGVB
* APGB
* Saptagiri Grameena Bank
* APCOB
* DCCBs

---

# Response Codes

| Status Code | Description           |
| ----------- | --------------------- |
| 200         | Success               |
| 201         | Resource Created      |
| 400         | Bad Request           |
| 401         | Unauthorized          |
| 404         | Resource Not Found    |
| 500         | Internal Server Error |

---

# Database

## BANK_CUSTOMER_DATA

Stores customer account information.

Main Fields

* ACCOUNTNUMBER
* FULLNAME
* DOB
* MOBILENUMBER
* EMAIL
* ADDRESS
* STATUS
* BALANCE
* TRANSACTIONS

---

# Error Handling

The API returns meaningful error responses for:

* Invalid Request
* Account Not Found
* Duplicate Account
* Invalid Aadhaar Number
* Invalid Bank Name
* Insufficient Balance
* Invalid Mobile Number
* Internal Server Error

---

# Security

* HTTPS Enabled
* Request Validation
* Input Validation
* Secure Configuration Properties
* Environment-Based Configuration

---

# Deployment

Build the application

```bash
mvn clean package
```

Run locally

```bash
mvn mule:run
```

Deploy to CloudHub

```bash
mvn clean deploy
```

---

# Testing

The API can be tested using:

* Postman
* Anypoint Studio API Console
* curl
* REST Client Extensions

---

# Future Enhancements

* UPI Payments (Google Pay, PhonePe, Paytm)
* Credit Card Services
* Fixed Deposits
* Beneficiary Management
* Fund Transfers
* AI Banking Assistant
* Fraud Detection
* QR Code Payments
* Scheduled Payments
* Standing Instructions

---

# Author

**Narsingarao Beesetti**

**MuleSoft Developer**

---

# License

This project is intended for learning, demonstration, and banking API development purposes.
