# 📚 Exam Booking System

```
███████╗██╗  ██╗ █████╗ ███╗   ███╗    ██████╗  ██████╗  ██████╗ ██╗  ██╗██╗███╗   ██╗ ██████╗ 
██╔════╝╚██╗██╔╝██╔══██╗████╗ ████║    ██╔══██╗██╔═══██╗██╔═══██╗██║ ██╔╝██║████╗  ██║██╔════╝ 
█████╗   ╚███╔╝ ███████║██╔████╔██║    ██████╔╝██║   ██║██║   ██║█████╔╝ ██║██╔██╗ ██║██║  ███╗
██╔══╝   ██╔██╗ ██╔══██║██║╚██╔╝██║    ██╔══██╗██║   ██║██║   ██║██╔═██╗ ██║██║╚██╗██║██║   ██║
███████╗██╔╝ ██╗██║  ██║██║ ╚═╝ ██║    ██████╔╝╚██████╔╝╚██████╔╝██║  ██╗██║██║ ╚████║╚██████╔╝
╚══════╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝     ╚═╝    ╚═════╝  ╚═════╝  ╚═════╝ ╚═╝  ╚═╝╚═╝╚═╝  ╚═══╝ ╚═════╝ 
                                                                                                  
    A Modern Full-Stack Exam Booking & Management Platform
    Built with React.js & Django REST Framework
```

---

## 📋 Table of Contents

```
├── 🎯 Overview
├── ✨ Key Features
├── 🛠️ Technology Stack
├── 📁 Project Structure
├── 🔌 API Endpoints
│   ├── Authentication
│   ├── User Management
│   ├── Exam Management
│   └── Payment Processing
├── 🗺️ Frontend Routes
├── 🏗️ System Architecture
├── 💳 Payment Integration
│   ├── eSewa Gateway
│   └── Flywire API
├── 🔐 Authentication Flow
└── 📊 Technical Details
```

---

## 🎯 Overview

```plaintext
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│  A comprehensive web application designed for seamless exam     │
│  booking and management. This platform bridges students,        │
│  administrators, and payment systems to create a smooth         │
│  examination enrollment experience.                             │
│                                                                 │
│  ✓ JWT Token Authentication                                     │
│  ✓ Role-Based Access Control                                    │
│  ✓ Dual Payment Gateway (eSewa + Flywire)                       │
│  ✓ Email Notification System                                    │
│  ✓ Admin Dashboard                                              │
│  ✓ Currency Conversion Support                                  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**User Flow:**
```
User → Register/Login → JWT Auth → Browse Exams → Enroll → Payment Gateway
                                                              ├── eSewa (Local)
                                                              └── Flywire (International)
                                                                   ↓
Admin → Dashboard → Monitor Bookings → Manage Users → Verify Payments
```

---

## ✨ Key Features

```
┌─────────────────────┬─────────────────────┬─────────────────────┬─────────────────────┐
│  🔐 Authentication  │   👥 User Mgmt      │   📋 Exam Booking   │   💳 Payments       │
├─────────────────────┼─────────────────────┼─────────────────────┼─────────────────────┤
│                     │                     │                     │                     │
│ ✓ JWT Tokens        │ ✓ User Profiles     │ ✓ Enrollment        │ ✓ eSewa Gateway     │
│ ✓ Role-Based Access │ ✓ Profile Editing   │ ✓ CRUD Operations   │ ✓ Flywire API       │
│ ✓ Token Refresh     │ ✓ Admin Creation    │ ✓ Expiry Checking   │ ✓ Multi-Currency    │
│ ✓ Password Reset    │ ✓ Bulk Operations   │ ✓ Booking History   │ ✓ Verification      │
│ ✓ Email Recovery    │ ✓ Role Assignment   │ ✓ Status Tracking   │ ✓ Webhooks          │
│ ✓ Custom Decorators │ ✓ User Listing      │ ✓ Pagination        │ ✓ Transaction Logs  │
│                     │                     │                     │                     │
└─────────────────────┴─────────────────────┴─────────────────────┴─────────────────────┘
```



---

## 🛠️ Technology Stack

### Backend Stack

```python
# requirements.txt
"""
┌─────────────────────────────────────────────────────────────┐
│ Core Framework & API                                        │
├─────────────────────────────────────────────────────────────┤
"""
Django==5.2.5                      # Web framework
djangorestframework==3.16.1        # REST API framework
asgiref==3.9.1                     # ASGI components

"""
├─────────────────────────────────────────────────────────────┤
│ Authentication & Security                                   │
├─────────────────────────────────────────────────────────────┤
"""
djangorestframework_simplejwt==5.5.1  # JWT authentication
PyJWT==2.10.1                         # JWT implementation

"""
├─────────────────────────────────────────────────────────────┤
│ Payment Integrations                                        │
├─────────────────────────────────────────────────────────────┤
"""
django-esewa==1.0.9                # eSewa payment gateway
requests==2.32.5                   # HTTP library (Flywire API)

"""
├─────────────────────────────────────────────────────────────┤
│ Additional Features                                         │
├─────────────────────────────────────────────────────────────┤
"""
django-cors-headers==4.7.0         # CORS handling
Pillow==11.3.0                     # Image processing
python-dotenv==1.1.1               # Environment variables
CurrencyConverter==0.18.10         # Currency conversion
forex-python==1.9.2                # Forex rates
simplejson==3.20.2                 # JSON processing
sqlparse==0.5.3                    # SQL parsing
tzdata==2025.2                     # Timezone data

"""
├─────────────────────────────────────────────────────────────┤
│ Dependencies                                                │
├─────────────────────────────────────────────────────────────┤
"""
certifi==2025.8.3                  # SSL certificates
charset-normalizer==3.4.3          # Character encoding
idna==3.10                         # IDNA support
urllib3==2.5.0                     # HTTP client
```

### Frontend Stack

```javascript
// package.json (dependencies)
{
  "name": "exam-booking-frontend",
  "version": "1.0.0",
  "description": "Exam Booking System Frontend",
  "dependencies": {
    "react": "^18.x",              // UI framework
    "react-dom": "^18.x",          // React DOM
    "react-router-dom": "^6.x",   // Client-side routing
    "lucide-react": "latest"       // Icon library
  },
  "technologies": [
    "JavaScript ES6+",
    "Fetch API (async/await)",
    "Custom CSS",
    "Component-based Architecture"
  ]
}
```

---

## 📁 Project Structure

```
project-root/
│
├── 📂 backend/
│   ├── 📄 manage.py                      # Django management script
│   ├── 📋 requirements.txt               # Python dependencies
│   ├── 🔐 .env                           # Environment variables
│   │
│   ├── 📂 app/
│   │   ├── 🗃️ models.py                 # Database models
│   │   │   ├── User Model (auth, roles)
│   │   │   ├── Booking Model (exams)
│   │   │   ├── Payment Model (transactions)
│   │   │   └── Exam Model (exam details)
│   │   │
│   │   ├── 🎯 views.py                  # API views & logic
│   │   │   ├── Authentication views
│   │   │   ├── User management views
│   │   │   ├── Exam booking views
│   │   │   ├── Payment processing views
│   │   │   └── Email handling views
│   │   │
│   │   ├── 🔄 serializers.py            # Data serialization
│   │   │   ├── UserSerializer
│   │   │   ├── BookingSerializer
│   │   │   ├── PaymentSerializer
│   │   │   └── ExamSerializer
│   │   │
│   │   ├── 🎨 decorators.py             # Custom decorators
│   │   │   ├── @role_required
│   │   │   ├── @admin_only
│   │   │   └── @jwt_auth
│   │   │
│   │   └── 🛣️ urls.py                   # URL routing
│   │
│   └── 📂 config/
│       ├── ⚙️ settings.py               # Django settings
│       │   ├── CORS configuration
│       │   ├── JWT settings
│       │   ├── Email configuration
│       │   └── Payment gateway config
│       │
│       └── 🌐 urls.py                   # Main URL config
│
└── 📂 frontend/
    ├── 📦 package.json                   # Node dependencies
    │
    ├── 📂 public/                        # Static files
    │   ├── index.html
    │   ├── favicon.ico
    │   └── manifest.json
    │
    └── 📂 src/
        ├── 🖼️ assets/                    # Images, fonts, media
        │
        ├── 🧩 components/                # Reusable React components
        │   ├── Header.jsx
        │   ├── Footer.jsx
        │   ├── Navbar.jsx
        │   ├── Card.jsx
        │   ├── Form components
        │   └── ...
        │
        ├── 📄 pages/                     # Page components
        │   ├── Home.jsx
        │   ├── Login.jsx
        │   ├── Register.jsx
        │   ├── Profile.jsx
        │   ├── Exam.jsx
        │   ├── Admin/
        │   │   ├── Dashboard.jsx
        │   │   ├── UserManagement.jsx
        │   │   └── AddUser.jsx
        │   └── ...
        │
        ├── 🎨 css/                       # Stylesheets
        │   ├── App.css
        │   ├── components/
        │   └── pages/
        │
        ├── ⚛️ App.js                     # Main component
        └── 🚀 index.js                   # Entry point
```

---

## 🔌 Backend API Endpoints

### 🔐 Authentication Endpoints

```http
POST   /api/token/                    # Obtain JWT token pair
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request:
{
  "email": "user@example.com",
  "password": "securepassword"
}

Response:
{
  "access": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "refresh": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}


POST   /api/token/refresh/            # Refresh access token
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request:
{
  "refresh": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}

Response:
{
  "access": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}


POST   /login/                        # User login
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request Body:  { email, password }
Response:      { user_data, tokens }
Auth:          ❌ Not Required


POST   /register/                     # User registration
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request Body:  { email, password, name, ... }
Response:      { user_id, message }
Auth:          ❌ Not Required


POST   /api/send-email/               # Send password reset email
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request Body:  { email }
Response:      { message, token_sent }
Auth:          ❌ Not Required


POST   /api/reset-password/           # Reset password with token
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request Body:  { token, new_password }
Response:      { message }
Auth:          ❌ Not Required
```

### 👥 User Management Endpoints

```http
POST   /api/createUser/               # Create new user (Admin)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request Body:  { email, password, role, ... }
Response:      { user_id, created }
Auth:          ✅ Admin Token Required


GET    /api/get-user/<int:id>/        # Get user by ID
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Response:      { user_details }
Auth:          ✅ Token Required


GET    /api/getAlluser/               # Get all users (Admin)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Response:      { users: [...], pagination }
Auth:          ✅ Admin Token Required


PUT    /api/Update-user/<int:id>/     # Update user profile
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request Body:  { field: value, ... }
Response:      { updated_user }
Auth:          ✅ Token Required


POST   /api/Chnagepassword/<int:id>/  # Change password
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request Body:  { old_password, new_password }
Response:      { message }
Auth:          ✅ Token Required
```

### 📋 Exam Management Endpoints

```http
POST   /enroll/                       # Enroll in exam
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request Body:  { exam_id, user_id, ... }
Response:      { booking_id, status }
Auth:          ✅ Token Required


GET    /api/get-Exam/<int:booking_id>/ # Get exam booking details
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Response:      { booking_details, exam_info }
Auth:          ✅ Token Required


GET    /api/getData/                  # Get all exam bookings (Admin)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Response:      { bookings: [...], pagination }
Auth:          ✅ Admin Token Required


PUT    /api/Update-Exam/<int:booking_id>/ # Update exam booking
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request Body:  { field: value, ... }
Response:      { updated_booking }
Auth:          ✅ Token Required


DELETE /api/Delete-Exam/<int:booking_id>/ # Delete exam booking
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Response:      { message, deleted }
Auth:          ✅ Token Required


GET    /api/Checkexpiry/              # Check booking expiry status
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Response:      { expired: [...], active: [...] }
Auth:          ✅ Token Required
```

### 💳 Payment Endpoints

```http
POST   /Payment/                      # Initiate eSewa payment
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request Body:
{
  "booking_id": 123,
  "amount": 5000,
  "product_id": "EXAM-001"
}

Response:
{
  "payment_url": "https://esewa.com.np/epay/main",
  "transaction_id": "TXN123456",
  "status": "pending"
}

Auth:          ✅ Token Required
Gateway:       eSewa (Nepal)


POST   /esewa/verify/                 # Verify eSewa payment
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request Body:  { oid, amt, refId }
Response:      { verified, payment_details }
Auth:          ✅ Token Required
Gateway:       eSewa (Callback)


POST   /flywire/payment/              # Initiate Flywire payment
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request Body:
{
  "booking_id": 123,
  "amount": 100,
  "currency": "USD",
  "payer_details": {...}
}

Response:
{
  "payment_url": "https://flywire.com/pay/...",
  "transaction_id": "FW123456",
  "status": "pending"
}

Auth:          ✅ Token Required
Gateway:       Flywire (International)


POST   /flywire/verify/               # Verify Flywire payment (Webhook)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Request Body:  { signature, payload }
Response:      { verified, status }
Auth:          🔐 Signature Verification
Gateway:       Flywire (Webhook)
```

### 🔧 System Endpoints

```http
GET    /test/                         # API health check
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Response:      { status: "ok", timestamp }
Auth:          ❌ Not Required


GET    /admin/                        # Django admin panel
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Response:      Admin Interface
Auth:          ✅ Admin Credentials Required
```

---

## 🗺️ Frontend Routes

```javascript
// App.js - Route Configuration
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';

<Routes>
  {/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */}
  {/* PUBLIC ROUTES                                                */}
  {/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */}
  
  <Route path="/"                   element={<Home />}>
    {/* Landing page and application overview */}
  </Route>
  
  <Route path="/login"              element={<Login />}>
    {/* User authentication page */}
  </Route>
  
  <Route path="/register"           element={<Register />}>
    {/* New user registration form */}
  </Route>
  
  <Route path="/forgot-password"    element={<Fp />}>
    {/* Forgot password form */}
  </Route>
  
  <Route path="/reset"              element={<Reset />}>
    {/* Password reset page */}
  </Route>

  {/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */}
  {/* USER ROUTES (Authentication Required)                       */}
  {/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */}
  
  <Route path="/Exam"               element={<Exam />}>
    {/* Exam booking and enrollment interface */}
  </Route>
  
  <Route path="/Profile"            element={<Profile />}>
    {/* User profile view and edit */}
  </Route>
  
  <Route path="/payfee"             element={<UniPayment />}>
    {/* Payment processing page (eSewa/Flywire) */}
  </Route>
  
  <Route path="/Checklist"          element={<Checklist />}>
    {/* Exam preparation checklist */}
  </Route>
  
  <Route path="/top-Uni"            element={<Topuni />}>
    {/* Top universities information */}
  </Route>

  {/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */}
  {/* ADMIN ROUTES (Admin Role Required)                          */}
  {/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */}
  
  <Route path="/admin/dashboard"    element={<Admin />}>
    {/* Administrative dashboard with overview */}
  </Route>
  
  <Route path="/admin/users/all"    element={<UserM />}>
    {/* User management interface */}
  </Route>
  
  <Route path="/admin/users/add"    element={<Add />}>
    {/* Add new user form */}
  </Route>

  {/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */}
  {/* UTILITY ROUTES                                               */}
  {/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */}
  
  <Route path="/comp"               element={<Component />}>
    {/* Component demonstration page */}
  </Route>
  
  <Route path="/404"                element={<NotFound />}>
    {/* 404 error page */}
  </Route>
  
  <Route path="*"                   element={<NotFound />}>
    {/* Catch-all for undefined routes */}
  </Route>
</Routes>
```

### Route Summary Table

```
┌────────────────────────┬──────────────┬─────────────┬──────────────────────────┐
│ Route                  │ Component    │ Auth        │ Description              │
├────────────────────────┼──────────────┼─────────────┼──────────────────────────┤
│ /                      │ Home         │ Public      │ Landing page             │
│ /login                 │ Login        │ Public      │ Authentication           │
│ /register              │ Register     │ Public      │ User signup              │
│ /forgot-password       │ Fp           │ Public      │ Password recovery        │
│ /reset                 │ Reset        │ Public      │ Password reset           │
├────────────────────────┼──────────────┼─────────────┼──────────────────────────┤
│ /Exam                  │ Exam         │ User        │ Exam booking             │
│ /Profile               │ Profile      │ User        │ Profile management       │
│ /payfee                │ UniPayment   │ User        │ Payment processing       │
│ /Checklist             │ Checklist    │ User        │ Exam checklist           │
│ /top-Uni               │ Topuni       │ User        │ University info          │
├────────────────────────┼──────────────┼─────────────┼──────────────────────────┤
│ /admin/dashboard       │ Admin        │ Admin       │ Admin dashboard          │
│ /admin/users/all       │ UserM        │ Admin       │ User management          │
│ /admin/users/add       │ Add          │ Admin       │ Add new user             │
├────────────────────────┼──────────────┼─────────────┼──────────────────────────┤
