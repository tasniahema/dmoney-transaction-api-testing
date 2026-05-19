# Dmoney Transaction API 

A complete API test Dmoney Transaction System using Postman.  
This collection covers authentication, user management, transaction workflows, balance validation, and payment operations with automated test assertions and dynamic environment handling.

---

# Project Overview

This project automates end-to-end API testing for the Dmoney Transaction System.

The collection includes:

- Authentication API
- User Management APIs
- Agent Operations
- Merchant Operations
- Deposit Transactions
- Withdraw Transactions
- Send Money Transactions
- Payment Transactions
- Balance Verification
- Dynamic Environment Variables
- Automated Response Assertions

---

# Tech Stack

- Postman
- JavaScript
- REST API
- JSON

---

# Project Structure

```bash
.
├── Dmoney-API.postman_environment.json
├── .Dmoney-Trxn-API-Flow.postman_collection.json
└── README.md
```

---

# Modules Covered

## Authentication
- Login with valid credentials

## User Management
- Users List
- Create New User
- Search User by ID
- Full Update User

## Agent Operations
- Create Agent
- Agent Search by ID
- Deposit Money to Agent
- Agent Balance Validation

## Merchant Operations
- Create Merchant
- Merchant Search by ID
- Merchant Balance Validation

## Customer Transactions
- Withdraw Money via Agent
- Send Money Between Customers
- Customer to Merchant Payment

## Balance Verification
- System Balance Check
- Agent Balance Check
- Customer Balance Check
- Merchant Balance Check

---

# Environment Variables

The following environment variables are required:

| Variable | Description |
|---|---|
| `BaseURL` | API base URL |
| `token` | Authentication token |
| `email` | Login email |
| `password` | Login password |
| `UpdateID` | User ID for update operation |
| `phoneNumber` | Dynamic phone number |
| `randomId` | Random generated user ID |
| `agent-phone-number` | Agent account phone number |
| `customer-phone-number` | Customer account phone number |
| `Merchant-phone-number` | Merchant account phone number |
| `amount` | Transaction amount |
| `prevBalance` | Previous system balance |
| `agent-prev-balance` | Previous agent balance |
| `CustomerPrevBalance` | Previous customer balance |
| `MerchantPrevBalance` | Previous merchant balance |

---

# Sample Environment Configuration

```json
{
  "BaseURL": "http://xyz.net",
  "email": "xyz@gmail.com",
  "password": "1234",
  "amount": 10,
  "agent-phone-number": "01502476...",
  "customer-phone-number": "015028....",
  "Merchant-phone-number": "0150286...."
}
```

---

# Setup Instructions

## 1. Clone Repository

```bash
git clone <repository-url>
```

---

## 2. Import Collection

Import the following collection file into Postman:

```bash
.Dmoney-Trxn-API-Flow.postman_collection.json
```

---

## 3. Import Environment

Import the environment file:

```bash
Dmoney-API.postman_environment.json
```

---

## 4. Select Environment

Choose the imported environment from the top-right environment dropdown in Postman.

---

# Running the Collection

## Run Using Collection Runner

1. Open Postman
2. Click Collection Runner
3. Select the collection
4. Select environment
5. Click Run

---

# Automated Validations

The collection validates:

- HTTP status codes
- API response messages
- Authentication token generation
- User information
- Transaction IDs
- Balance calculations
- Transaction fee validation
- Commission validation

---

# Transaction Flows

## Deposit Flow

```text
SYSTEM → AGENT
```

## Withdraw Flow

```text
CUSTOMER → AGENT
```

## Send Money Flow

```text
CUSTOMER → CUSTOMER
```

## Payment Flow

```text
CUSTOMER → MERCHANT
```

---

# Sample Assertions

```javascript
pm.response.to.have.status(200);

pm.expect(jsonData.message).to.eql("Login successful");

pm.expect(newBalance).to.eql(prevBalance + depositAmount);
```

---

# Future Improvements

- Newman Integration
- CI/CD Integration
- Data-Driven Testing
- Performance Testing

---

# Author

## Tasnia Sultana Hema

Software Quality Assurance (SQA) Engineer
