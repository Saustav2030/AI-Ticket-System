# 🎫 AI-Ticket-Assistant

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge\&logo=node.js\&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge\&logo=mongodb\&logoColor=white)
![Express](https://img.shields.io/badge/Express.js-000000?style=for-the-badge\&logo=express\&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge\&logo=jsonwebtokens)
![Nodemailer](https://img.shields.io/badge/Nodemailer-00979D?style=for-the-badge\&logo=gmail\&logoColor=white)
![Inngest](https://img.shields.io/badge/Inngest-1E90FF?style=for-the-badge)
![Gemini API](https://img.shields.io/badge/Google%20Gemini-4285F4?style=for-the-badge\&logo=google\&logoColor=white)

Welcome to the **AI-Powered Ticket Management System**! 🎉
A web application that uses AI to automatically categorize, prioritize, and assign support tickets to the most appropriate moderators.

---

## 📌 Overview

A **smart ticket management system** that leverages **AI** to:

* Automatically categorize tickets
* Assign priorities intelligently
* Match tickets with the right moderators
* Generate helpful AI-driven notes for moderators

---

## 🚀 Features

### 🔹 AI-Powered Ticket Processing

* Automatic ticket categorization
* Smart priority assignment
* AI-generated moderator notes

### 🔹 Smart Moderator Assignment

* Skill-based moderator matching
* Fallback to admin if no match is found
* Regex-based routing

### 🔹 User Management

* Role-based access control (User, Moderator, Admin)
* Skill management for moderators
* JWT authentication

### 🔹 Background Processing

* Event-driven architecture using **Inngest**
* Asynchronous ticket handling
* Automated email notifications

---

## 🛠️ Tech Stack

* **Backend:** Node.js (Express)
* **Database:** MongoDB
* **Authentication:** JWT
* **Background Jobs:** Inngest
* **AI Integration:** Google Gemini API
* **Email Service:** Nodemailer + Mailtrap
* **Development Tools:** Nodemon

---

## 📋 Prerequisites

* Node.js (v14 or higher)
* MongoDB installed/running
* Google Gemini API key
* Mailtrap account (for testing emails)

---

## ⚙️ Installation/Setup

1. **Environment Setup**
   Create a `.env` file in the root directory:

   ```env
   # MongoDB
   MONGO_URI=your_mongodb_uri

   # JWT
   JWT_SECRET=your_jwt_secret

   # Email (Mailtrap)
   MAILTRAP_SMTP_HOST=your_mailtrap_host
   MAILTRAP_SMTP_PORT=your_mailtrap_port
   MAILTRAP_SMTP_USER=your_mailtrap_user
   MAILTRAP_SMTP_PASS=your_mailtrap_password

   # AI (Gemini)
   GEMINI_API_KEY=your_gemini_api_key

   # Application
   APP_URL=http://localhost:3000
   ```

---

## 🚀 Running the Application

1. Start the main server:

   ```bash
   npm run dev
   ```

2. Start the Inngest dev server:

   ```bash
   npm run inngest-dev
   ```

---

## 📝 API Endpoints

### 🔹 Authentication

* `POST /api/auth/signup` → Register a new user
* `POST /api/auth/login` → Login & get JWT

### 🔹 Tickets

* `POST /api/tickets` → Create a ticket
* `GET /api/tickets` → Fetch all tickets (user-specific)
* `GET /api/tickets/:id` → Get ticket details

### 🔹 Admin

* `GET /api/auth/users` → Get all users (Admin only)
* `POST /api/auth/update-user` → Update role & skills (Admin only)

---

## 🔄 Ticket Processing Flow

1. **Ticket Creation** → User submits a ticket
2. **AI Processing** → AI assigns priority, notes, and type
3. **Moderator Assignment** → Skill-based matching (fallback to admin)
4. **Notification** → Email sent with ticket details + AI notes

---

## 🧪 Testing

Start Inngest dev server:

```bash
npm run inngest-dev
```

Runs at: [http://localhost:8288](http://localhost:8288)

**Example Ticket Creation (cURL):**

```bash
curl -X POST http://localhost:3000/api/tickets \
-H "Content-Type: application/json" \
-H "Authorization: Bearer YOUR_JWT_TOKEN" \
-d '{
  "title": "Database Connection Issue",
  "description": "Experiencing intermittent database connection timeouts"
}'
```

---

## 🔍 Troubleshooting

### Port Conflicts

```bash
lsof -i :8288
kill -9 <PID>
```

### AI Errors

* Verify `GEMINI_API_KEY`
* Check API quota & limits

### Email Issues

* Validate Mailtrap credentials
* Check SMTP configs

---

## 📚 Dependencies

* `@inngest/agent-kit` ^0.7.3
* `bcrypt` ^5.1.1
* `cors` ^2.8.5
* `dotenv` ^16.5.0
* `express` ^5.1.0
* `inngest` ^3.35.0
* `jsonwebtoken` ^9.0.2
* `mongoose` ^8.13.2
* `nodemailer` ^6.10.1

---
