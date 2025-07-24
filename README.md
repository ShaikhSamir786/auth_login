



````markdown
# MERN Authentication System (Backend) 🔐

A secure and professional full-stack authentication backend built with the MERN stack, featuring JWT authentication, email verification, and protected routes. Suitable for learning secure auth best practices or establishing a foundation for production-grade applications.

---

## 🧩 Table of Contents

- [Features](#features)  
- [Tech Stack](#tech-stack)  
- [Architecture](#architecture)  
- [Setup & Installation](#setup--installation)  
- [Usage](#usage)  
- [API Documentation](#api-documentation)  
- [Validation & Error Handling](#validation--error-handling)  
- [Testing](#testing)  
- [File Structure](#file-structure)  
- [Contribution](#contribution)  
- [License](#license)

---

## ⚙️ Features

- **User Registration and Login** with secure password hashing via `bcrypt` and session management using `JWT`.
- **Email Verification**: Sends time-limited, secure tokens via email to confirm user accounts.
- **Protected Routes**: Middleware ensures that only verified users can access sensitive endpoints.
- **Resend Verification & Password Reset Support** ready for implementation.
- **Robust Validation** with express-validator and custom error handling.
- **Real-time Feedback**: Clear API responses for every outcome — success, failure, or validation error.

---

## 🛠 Tech Stack

- **Languages & Frameworks**: Node.js, Express.js  
- **Database**: MongoDB (via Mongoose ODM)  
- **Auth**: JSON Web Tokens (JWT), bcrypt  
- **Email Service**: NodeMailer (or any SMTP/mail API)  
- **Validation**: express-validator  
- **Logging**: morgan (or winston)

---

## 🔧 Setup & Installation

1. **Clone Package**
   ```bash
   git clone https://github.com/yourusername/mern-auth-backend.git
   cd mern-auth-backend
````

2. **Install Dependencies**

   ```bash
   npm install
   ```

3. **Configure Environment Variables** (`.env`):

   ```ini
   PORT=5000
   MONGODB_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret
   EMAIL_HOST=smtp.example.com
   EMAIL_PORT=587
   EMAIL_USER=your_email_account
   EMAIL_PASS=your_email_password
   EMAIL_FROM="YourAppName <no-reply@yourapp.com>"
   CLIENT_URL=http://localhost:3000
   VERIFICATION_TOKEN_EXPIRY=1h
   ```

4. **Run the Server**

   ```bash
   npm run dev
   ```

   🟢 Server listens on `http://localhost:5000`

---

## 🚀 Usage

Below are the public API endpoints with request/response details:

### 📬 `POST /api/auth/register`

* **Purpose**: Register a new user and trigger verification email.
* **Request Body**:

  ```json
  {
    "name": "Jane Doe",
    "email": "jane@domain.com",
    "password": "SuperSecret123"
  }
  ```
* **Response**:

  * `201 Created`: Prompt to check email

### 🔑 `POST /api/auth/login`

* **Purpose**: Authenticate existing, verified users.
* **Request**:

  ```json
  {
    "email": "jane@domain.com",
    "password": "SuperSecret123"
  }
  ```
* **Response**:

  * `200 OK`: Returns JWT access token

### ✅ `GET /api/auth/verify/:token`

* **Purpose**: Verify a user's email via token link.
* **Response**:

  * `200 OK`: Account verified
  * `400/404`: Invalid/expired token



---

## 💡 Validation & Error Handling

We use `express-validator` to enforce:

* Email syntactic checks
* Password strength
* Required field validation

Uniform error responses across endpoints ensure graceful failure handling.

---

## 🔬 Testing

TBD – Use frameworks like Jest or Mocha to test endpoints:

* Signup & email verification
* Login with verified credentials
* Access control test for protected routes

---

## 🗂 File Structure

```
mern-auth-backend/
├── config/           # DB & email setup
├── controllers/      # Request handlers (Auth)
├── middlewares/      # Auth & error middlewares
├── models/           # Mongoose schemas (User, Token)
├── routes/           # API routes
├── utils/            # Helper (email sender, token generator)
├── .env              # Env variables (not tracked)
├── server.js         # App entry point
└── package.json
```

---

## 🌱 Contribution

Contributions are welcome! Please fork the repo, create feature-based branches, and open pull requests. Ensure new code is secure and validated.



---

## 📌 Credits

* This project is inspired by the YouTube tutorial:

🎥 Video: Advanced MERN Auth Course: Email Verification, Password Recovery, and Welcome Emails
📺 Channel: Codesistency

Special thanks to Codesistency for providing an in-depth, high-quality guide on building a secure and modern authentication system using the MERN stack, featuring email verification, password recovery, and welcome email functionality

---

*Feel free to customize names, styles, or add demo badges/screenshots to match your frontend.*


