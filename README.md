# Dmoney Transaction API

A complete backend solution for handling digital money transactions including customer, agent, and merchant operations. This project provides secure authentication, account handling, money transfers, deposits, withdrawals, and transaction history management.

---

## 🚀 Features

* JWT‑based secure authentication
* Customer, Agent & Merchant account management
* Balance check & balance update
* Payment transaction (customer/agent → merchant)
* Deposit & withdrawal transactions
* Transaction history APIs
* API input validation & proper error handling
* Follows clean folder structure
* Postman collection included for testing

---

## 🏗️ Project Structure

```
project-root/
├── src/
│   ├── controllers/
│   ├── routes/
│   ├── middlewares/
│   ├── services/
│   ├── models/
│   └── utils/
├── config/
├── tests/
├── .env
├── package.json
└── README.md
```

---

## 🔧 Tech Stack

* **Node.js**
* **JWT Authentication**
* **Bcrypt Password Hashing**

---

## 📦 Installation & Setup

### 1️⃣ Clone the repository

```bash
git clone https://github.com/your-username/dmoney-transaction-api.git
cd dmoney-transaction-api
```

### 2️⃣ Install dependencies

```bash
npm install
```

### 3️⃣ Create `.env` file

Add the following variables:

```
PORT=5000
MONGO_URI=your_mongo_connection
JWT_SECRET=your_secret_key
```

### 4️⃣ Run the server

```bash
npm start
```

Or for development mode:

```bash
npm run dev
```

---

## 🔐 Authentication Flow

* User registers/logs in
* Server returns JWT token
* All protected routes require:

```
Authorization: Bearer <token>
```

---

## 🔗 API Endpoints Summary

### Authentication

| Method | Endpoint         | Description       |
| ------ | ---------------- | ----------------- |
| POST   | `/auth/register` | Create account    |
| POST   | `/auth/login`    | Login and get JWT |

### Account Operations

| Method | Endpoint               | Description           |
| ------ | ---------------------- | --------------------- |
| GET    | `/account/:id`         | Get user account info |
| GET    | `/account/balance/:id` | Get balance           |

### Transaction APIs

| Method | Endpoint                   | Description                    |
| ------ | -------------------------- | ------------------------------ |
| POST   | `/transaction/deposit`     | Cash-in by Agent to Customer   |
| POST   | `/transaction/withdraw`    | Cash-out by Customer via Agent |
| POST   | `/transaction/payment`     | Pay Merchant                   |
| GET    | `/transaction/history/:id` | Full history                   |

---

## 🧪 Testing (Postman)

### ✔ Automated Test Cases (SQA API Testing)

This project includes multiple automated assertion-based test cases using Postman. Below is the categorized list of all tests:

---

### 🔹 **General API Status Checks**

* HTTP Status code is 200
* HTTP Status code Validation
* Status 200

---

### 🔹 **Send Money API Tests**

* SendMoney Message Validation
* SendMoney trnxId Validation
* SendMoney fee Validation
* SendMoney currentBalance Validation

---

### 🔹 **Payment Transaction API Tests**

* Process payment transaction Message Validation
* Process payment trnxId Validation
* Process payment transaction fee Validation
* Process payment transaction currentBalance Validation

---

### 🔹 **Deposit Money API Tests**

* Deposit Money Message Validation
* Deposit Money trnxId Validation
* Deposit Money commission Validation
* Deposit Money currentBalance Validation
* HTTP Status 200

---

### 🔹 **Merchant Balance Validation**

Example failing test:

```
Merchant balance updated correctly | AssertionError: expected 205 to deeply equal 204.75
```

This error typically occurs due to computation mismatch such as:

* Transaction fee not subtracted correctly
* Backend rounding/precision issues
* Incorrect previous balance value

---

### 🔹 **Login API Test**

Example response:

```
{"message": "Login success"}
```

Message validation is performed for this response.

---

### 🔹 **Example Test Snippet**

```javascript
pm.test("HTTP status code Validation", function(){
    pm.expect(pm.response.code).to.eql(200);
});

pm.test("SendMoney Message Validation", function(){
    var jsonData = pm.response.json();
    pm.expect(jsonData.message).to.include("success");
});
```

---

### ✔ Postman Runner Support

* Fully compatible with Postman Collection Runner
* Automated assertions included
* Environment variables auto-generated (randomId, phoneNumber, token)

---

## ⚠️ Error Handling

API returns clear, consistent error responses:

```json
{
  "success": false,
  "message": "Insufficient balance"
}
```

---


## 👩‍💻 Author

**Tasnia Sultana Hema**
 QA Engineer
