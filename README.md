<<<<<<< HEAD
# HomelyHub - Full Stack Vacation Rental Platform

HomelyHub is a full-stack MERN (MongoDB, Express, React, Node.js) web application for property rental listings and bookings.

---

## Architecture Overview

- **Frontend**: React 18, Vite, Redux Toolkit, React Router, Ant Design, Leaflet
- **Backend**: Node.js, Express 5, Mongoose (MongoDB), JWT Authentication, Nodemailer (Mailtrap), ImageKit, Groq SDK
- **Dev Proxy**: Vite proxies requests from `/api` to `http://localhost:8080`

---

## Prerequisites

1. **Node.js**: v18.0.0 or higher (Tested with Node v24)
2. **MongoDB**: Local MongoDB instance (`mongodb://127.0.0.1:27017/homelyhub`) or a free [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) cloud cluster.

> **Windows PowerShell Note**: If PowerShell blocks script execution (`npm.ps1 cannot be loaded`), either run commands with `npm.cmd` (e.g. `npm.cmd run dev`) or run:
> ```powershell
> Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
> ```

---

## Quick Start (Local Setup)

### Step 1: Configure Backend Environment

1. Open `backend/.env` (or copy `backend/.env.example` to `backend/.env`).
2. Set your **`MONGO_URI`** with your MongoDB connection string:
   ```env
   PORT=8080
   NODE_ENV=development
   ORIGIN_ACCESS_URL=http://localhost:5173

   # Local MongoDB or MongoDB Atlas URI:
   MONGO_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/homelyhub?retryWrites=true&w=majority

   JWT_SECRET=homelyhub_secret_key_batch8_internship_2026
   JWT_EXPIRES_IN=90d
   JWT_COOKIE_EXPIRES_IN=90

   # Optional external services:
   IMAGEKIT_PUBLICKEY=your_imagekit_public_key
   IMAGEKIT_PRIVATEKEY=your_imagekit_private_key
   IMAGEKIT_URLENDPOINT=https://ik.imagekit.io/your_id/

   MAILTRAP_SMTP_HOST=sandbox.smtp.mailtrap.io
   MAILTRAP_SMTP_PORT=2525
   MAILTRAP_SMTP_USER=your_mailtrap_user
   MAILTRAP_SMTP_PASS=your_mailtrap_pass

   GROQ_API_KEY=your_groq_api_key
   ```

---

### Step 2: Install Dependencies

Both folders have their dependencies installed, but if you clone fresh:

```bash
# In backend directory
cd backend
npm install

# In Frontend directory
cd ../Frontend
npm install
```

---

### Step 3: Run the Application

You will need **two terminal windows**:

#### Terminal 1 — Backend Server:
```bash
cd backend
npm run dev
```
- Server will run on: **`http://localhost:8080`**
- Test health check endpoint: **`http://localhost:8080/`**

#### Terminal 2 — Frontend Client:
```bash
cd Frontend
npm run dev
```
- Client will run on: **`http://localhost:5173`**

Open [http://localhost:5173](http://localhost:5173) in your browser to use HomelyHub!
=======
# HomelyHubInternshipBatch8
>>>>>>> c49ea529a143d33d54623d5fea0b2148d99a6626
