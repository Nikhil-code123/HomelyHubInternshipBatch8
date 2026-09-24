# 🏡 HomelyHub — Full-Stack Vacation Rental & Booking Platform

[![Frontend Deployed on Netlify](https://img.shields.io/badge/Frontend-Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white)](https://homelyhubbatch8.netlify.app/)
[![Backend Deployed on Render](https://img.shields.io/badge/Backend-Render-46E3B7?style=for-the-badge&logo=render&logoColor=black)](https://homelyhubinternshipbatch8-1.onrender.com/)
[![React](https://img.shields.io/badge/React-18.2-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-6.3-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![Redux Toolkit](https://img.shields.io/badge/Redux_Toolkit-2.8-764ABC?style=for-the-badge&logo=redux&logoColor=white)](https://redux-toolkit.js.org/)
[![Node.js](https://img.shields.io/badge/Node.js-20+-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-5.2-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)

**HomelyHub** is a modern, full-stack vacation rental platform that connects travellers with unique stays and enables property hosts to list, manage, and monetize their accommodations. Built with a reactive frontend in **React 18** and a scalable **Node.js / Express** REST API powered by **MongoDB**, it features AI-powered trip planning, automatic property description generation via **Groq LLM**, interactive map browsing with **Leaflet**, cloud image hosting with **ImageKit**, and secure cookie-based **JWT authentication**.

---

## 🌐 Live Deployments

| Component | Service | Live URL |
| :--- | :--- | :--- |
| **Client (Frontend)** | Netlify | [https://homelyhubbatch8.netlify.app/](https://homelyhubbatch8.netlify.app/) |
| **API Server (Backend)** | Render | [https://homelyhubinternshipbatch8-1.onrender.com/](https://homelyhubinternshipbatch8-1.onrender.com/) |

---

## 📑 Table of Contents

- [Key Features](#-key-features)
- [Architecture & Tech Stack](#-architecture--tech-stack)
- [Project Directory Structure](#-project-directory-structure)
- [API Endpoints Reference](#-api-endpoints-reference)
- [Environment Variables](#-environment-variables)
- [Local Development Setup](#-local-development-setup)
- [Deployment Guide](#-deployment-guide)
- [License](#-license)

---

## ✨ Key Features

### 👤 User Authentication & Account Management
- **Secure Authentication**: Password hashing using `bcrypt` and session tokens stored in secure, `httpOnly` HTTP cookies.
- **Role-Based Workflows**: Separate capabilities for regular guests and listing hosts.
- **Password Recovery**: Complete forgot/reset password workflow with branded transactional emails powered by **Mailgen** and **Nodemailer**.
- **User Profile Management**: Edit profile details, change passwords, and upload custom avatars via **ImageKit**.

### 🔍 Property Search & Interactive Discovery
- **Multi-criteria Filtering**: Filter properties by city, price range, property type, room category, and specific amenities.
- **Search & Pagination**: Server-side fuzzy search and paginated responses for performance.
- **Interactive Geospatial Maps**: Visual location exploration using **Leaflet** and **React-Leaflet**.
- **Comprehensive Listing Details**: High-resolution image galleries, amenities list, host details, and check-in/out policies.

### 🏠 Host & Accommodation Management
- **Create Listings**: Multi-step accommodation creation with image uploading directly to **ImageKit**.
- **Host Dashboard**: View and manage all properties listed under your account.
- **🤖 AI Description Generator**: Automatic, professional listing description creation powered by **Groq SDK** and Llama 3 models.

### 📅 Bookings & Payment Processing
- **Dynamic Pricing Engine**: Automated calculation of base fare, extra guest fees, cleaning fees, service taxes, and grand totals.
- **Date Range Picker**: Interactive calendar reservation preventing overlapping dates.
- **Booking Management**: View upcoming, active, and past booking confirmations with full itemized invoice details.
- **Order & Payment Verification**: Complete order creation and simulated transaction confirmation lifecycle.

### 🤖 AI Trip Planner
- **Customized Itinerary Generator**: Smart AI-driven travel recommendations tailored to user destinations, group size, and travel duration.

---

## 🛠 Architecture & Tech Stack

### Frontend
- **Framework**: [React 18](https://react.dev/)
- **Build Tool**: [Vite](https://vitejs.dev/)
- **State Management**: [Redux Toolkit](https://redux-toolkit.js.org/) & `react-redux`
- **Routing**: [React Router DOM v6](https://reactrouter.com/)
- **UI Components & Styling**: [Ant Design (antd)](https://ant.design/), CSS Modules, Responsive CSS
- **Animations & Icons**: [GSAP](https://gsap.com/), [Lucide React](https://lucide.dev/)
- **Maps**: [Leaflet](https://leafletjs.com/) & [React-Leaflet](https://react-leaflet.js.org/)
- **HTTP Client**: [Axios](https://axios-http.com/) (with credentials & query serialization)
- **Notifications**: [React Hot Toast](https://react-hot-toast.com/)

### Backend
- **Runtime**: [Node.js](https://nodejs.org/) (ES Modules)
- **Web Framework**: [Express.js 5](https://expressjs.com/)
- **Database & ODM**: [MongoDB](https://www.mongodb.com/) via [Mongoose](https://mongoosejs.com/)
- **Authentication**: [JSON Web Tokens (JWT)](https://jwt.io/) & [cookie-parser](https://www.npmjs.com/package/cookie-parser)
- **Security**: [bcrypt](https://www.npmjs.com/package/bcrypt), [CORS](https://www.npmjs.com/package/cors)
- **Media Storage**: [ImageKit.io](https://imagekit.io/)
- **Email Service**: [Nodemailer](https://nodemailer.com/) & [Mailgen](https://www.npmjs.com/package/mailgen)
- **Artificial Intelligence**: [Groq SDK](https://groq.com/)

---

## 📂 Project Directory Structure

```text
HomelyHubInternshipBatch8/
├── Frontend/                           # React + Vite client application
│   ├── public/                         # Public static assets & Netlify _redirects
│   │   ├── _redirects                  # Netlify SPA routing rules
│   │   └── ...
│   ├── src/
│   │   ├── ai/                         # Client-side AI API helpers
│   │   ├── assets/                     # Images, logos, and icons
│   │   ├── components/                 # Reusable UI components
│   │   │   ├── home/                   # Header, Search, Filter, PropertyList
│   │   │   ├── propertyListing/        # Listing Details, PaymentForm, MapView
│   │   │   ├── accomodation/           # Host property creation & management
│   │   │   ├── myBookings/             # Booking history & details
│   │   │   ├── payment/                # Order payment workflow
│   │   │   └── user/                   # Login, Signup, Profile, Password reset
│   │   ├── store/                      # Redux Toolkit slices and async thunks
│   │   ├── utils/                      # Axios centralized instance
│   │   ├── App.jsx                     # Root application routes
│   │   └── main.jsx                    # Application entry point & Store Provider
│   ├── package.json
│   └── vite.config.js                  # Vite configuration & /api proxy
│
├── backend/                            # Express.js REST API
│   ├── src/
│   │   ├── ai/                         # Groq SDK configuration & client
│   │   ├── controllers/                # Request handlers
│   │   │   ├── authController.js       # Authentication & user profile
│   │   │   ├── propertyController.js   # Listing CRUD & image upload
│   │   │   ├── bookingController.js    # Reservations & payment verification
│   │   │   └── tripController.js       # AI descriptions & itineraries
│   │   ├── Models/                     # Mongoose database schemas
│   │   │   ├── userModel.js
│   │   │   ├── propertyModel.js
│   │   │   └── bookingModel.js
│   │   ├── routes/                     # Express route definitions
│   │   ├── utils/                      # Database connector, ImageKit, Mailer, JWT
│   │   └── index.js                    # Server bootstrap & middleware setup
│   ├── .env.example                    # Sample backend environment variables
│   └── package.json
│
└── README.md                           # Master repository documentation
```

---

## 📡 API Endpoints Reference

### 🔐 Authentication & User Routes (`/api/v1/rent/user`)

| Method | Endpoint | Description | Access | Status |
| :--- | :--- | :--- | :--- | :---: |
| `POST` | `/signup` | Register a new user account | ✅ Public | ✅ Available |
| `POST` | `/login` | Authenticate user & set JWT session cookie | ✅ Public | ✅ Available |
| `GET` | `/logout` | Invalidate cookie and log out | ✅ Public | ✅ Available |
| `GET` | `/me` | Get currently authenticated user profile | ✅ Protected (JWT) | ✅ Available |
| `PATCH` | `/updateMe` | Update user profile details / avatar | ✅ Protected (JWT) | ✅ Available |
| `PATCH` | `/updateMyPassword` | Change user password | ✅ Protected (JWT) | ✅ Available |
| `POST` | `/forgotPassword` | Request password reset email | ✅ Public | ✅ Available |
| `PATCH` | `/resetPassword/:token`| Reset password using token | ✅ Public | ✅ Available |
| `POST` | `/newAccommodation` | Create a new property listing | ✅ Protected (JWT) | ✅ Available |
| `GET` | `/myAccommodation` | Fetch all accommodations owned by host | ✅ Protected (JWT) | ✅ Available |
| `POST` | `/generateDescription` | Generate AI description for a listing | ✅ Protected (JWT) | ✅ Available |

### 🏡 Property Listings (`/api/v1/rent/listing`)

| Method | Endpoint | Description | Access | Status |
| :--- | :--- | :--- | :--- | :---: |
| `GET` | `/` | Get all properties (supports search, filter, paginate) | ✅ Public | ✅ Available |
| `GET` | `/:id` | Get detailed information for a single property | ✅ Public | ✅ Available |

### 💳 Bookings & Payments (`/api/v1/rent/user/booking`)

| Method | Endpoint | Description | Access | Status |
| :--- | :--- | :--- | :--- | :---: |
| `GET` | `/` | List all bookings made by the logged-in user | ✅ Protected (JWT) | ✅ Available |
| `GET` | `/:bookingId` | Get detailed invoice & receipt for a booking | ✅ Protected (JWT) | ✅ Available |
| `POST` | `/create-order` | Initialize booking order calculation | ✅ Protected (JWT) | ✅ Available |
| `POST` | `/verify-payment` | Verify transaction and confirm reservation | ✅ Protected (JWT) | ✅ Available |

### ✈️ AI Trip Planner (`/api/v1/rent/trip`)

| Method | Endpoint | Description | Access | Status |
| :--- | :--- | :--- | :--- | :---: |
| `POST` | `/` | Generate structured AI trip itinerary | ✅ Public | ✅ Available |

---

## 🔑 Environment Variables

### Backend Configuration (`backend/.env`)

Create a `.env` file inside the `backend/` directory:

```env
# Server
PORT=8080
NODE_ENV=development
ORIGIN_ACCESS_URL=http://localhost:5173

# Database Connection
# Local: mongodb://127.0.0.1:27017/homelyhub
# Atlas: mongodb+srv://<username>:<password>@cluster0.mongodb.net/homelyhub?retryWrites=true&w=majority
MONGO_URI=mongodb://127.0.0.1:27017/homelyhub

# JWT Authentication
JWT_SECRET=your_super_secret_jwt_key_here
JWT_EXPIRES_IN=90d
JWT_COOKIE_EXPIRES_IN=90

# ImageKit (Image hosting for user avatars and property photos)
IMAGEKIT_PUBLICKEY=your_imagekit_public_key
IMAGEKIT_PRIVATEKEY=your_imagekit_private_key
IMAGEKIT_URLENDPOINT=https://ik.imagekit.io/your_id/

# Mailtrap / SMTP (Password recovery emails)
MAILTRAP_SMTP_HOST=sandbox.smtp.mailtrap.io
MAILTRAP_SMTP_PORT=2525
MAILTRAP_SMTP_USER=your_mailtrap_user
MAILTRAP_SMTP_PASS=your_mailtrap_pass

# Groq Cloud (AI Description and AI Trip Planner)
GROQ_API_KEY=your_groq_api_key
```

### Frontend Configuration (`Frontend/.env` - Optional)

By default, Vite's proxy automatically forwards `/api` requests to `http://localhost:8080` in local development. For production deployments (e.g., Netlify), you can set:

```env
VITE_API_BASE_URL=https://homelyhubinternshipbatch8-1.onrender.com/api
```

---

## 🚀 Local Development Setup

### 1. Clone the Repository

```bash
git clone https://github.com/richajha903/HomelyHubInternshipBatch8.git
cd HomelyHubInternshipBatch8
```

### 2. Configure & Start the Backend

1. Navigate to the `backend` directory:
   ```bash
   cd backend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
   *(On Windows PowerShell, use `npm.cmd install` if script execution is restricted)*
3. Create your `backend/.env` file with your **`MONGO_URI`** and secrets.
4. Start the backend server:
   ```bash
   npm run dev
   ```
   - Server runs on: **`http://localhost:8080`**
   - Health check: **`http://localhost:8080/`** (responds with `"Homelyhub server is running"`)

### 3. Start the Frontend Client

Open a **second terminal window**:

1. Navigate to the `Frontend` directory:
   ```bash
   cd Frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
   *(On Windows PowerShell, use `npm.cmd install`)*
3. Start the Vite development server:
   ```bash
   npm run dev
   ```
4. Open your browser and navigate to:
   **[http://localhost:5173](http://localhost:5173)**

---

## 🚢 Deployment Guide

### Deploy Frontend to Netlify

1. Link your GitHub repository to [Netlify](https://www.netlify.com/).
2. Set the build settings:
   - **Base directory**: `Frontend`
   - **Build command**: `npm run build`
   - **Publish directory**: `dist`
3. In **Site Configuration > Environment Variables**, add:
   ```env
   VITE_API_BASE_URL=https://homelyhubinternshipbatch8-1.onrender.com/api
   ```
4. The `Frontend/public/_redirects` file guarantees that direct route navigation (e.g. `/login`, `/listing/:id`) resolves properly without 404s.

### Deploy Backend to Render

1. Create a new **Web Service** on [Render](https://render.com/) linked to your repository.
2. Set the service settings:
   - **Root Directory**: `backend`
   - **Runtime**: `Node`
   - **Build Command**: `npm install`
   - **Start Command**: `node src/index.js`
3. In **Environment Variables**, add all keys from `backend/.env`:
   - `PORT=8080`
   - `NODE_ENV=production`
   - `ORIGIN_ACCESS_URL=https://homelyhubbatch8.netlify.app`
   - `MONGO_URI=<your-mongodb-atlas-uri>`
   - `JWT_SECRET`, `JWT_EXPIRES_IN`, `JWT_COOKIE_EXPIRES_IN`
   - `IMAGEKIT_PUBLICKEY`, `IMAGEKIT_PRIVATEKEY`, `IMAGEKIT_URLENDPOINT`
   - `MAILTRAP_SMTP_HOST`, `MAILTRAP_SMTP_PORT`, `MAILTRAP_SMTP_USER`, `MAILTRAP_SMTP_PASS`
   - `GROQ_API_KEY`

---

## 📄 License

This project is licensed under the [ISC License](LICENSE).
