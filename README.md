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

# 🔌 API Endpoints

## Authentication
| Endpoint | Method | Auth | Description |
|----------|--------|------|-------------|
| `/api/token/` | POST | ❌ | Get JWT token pair |
| `/api/token/refresh/` | POST | ❌ | Refresh access token |
| `/login/` | POST | ❌ | User authentication |
| `/register/` | POST | ❌ | User registration |
| `/api/send-email/` | POST | ❌ | Password reset email |
| `/api/reset-password/` | POST | ❌ | Reset password |

## User Management
| Endpoint | Method | Auth | Description |
|----------|--------|------|-------------|
| `/api/createUser/` | POST | 🔑 Admin | Create new user |
| `/api/get-user/{id}/` | GET | 🔑 User | Get user details |
| `/api/getAlluser/` | GET | 🔑 Admin | List all users |
| `/api/Update-user/{id}/` | PUT | 🔑 User | Update profile |
| `/api/Chnagepassword/{id}/` | POST | 🔑 User | Change password |

## Exam Management
| Endpoint | Method | Auth | Description |
|----------|--------|------|-------------|
| `/enroll/` | POST | 🔑 User | Enroll in exam |
| `/api/get-Exam/{id}/` | GET | 🔑 User | Get booking details |
| `/api/getData/` | GET | 🔑 Admin | List all bookings |
| `/api/Update-Exam/{id}/` | PUT | 🔑 User | Update booking |
| `/api/Delete-Exam/{id}/` | DELETE | 🔑 User | Delete booking |
| `/api/Checkexpiry/` | GET | 🔑 User | Check expiry status |

## Payment Processing
| Endpoint | Method | Auth | Description |
|----------|--------|------|-------------|
| `/Payment/` | POST | 🔑 User | Initiate eSewa payment |
| `/esewa/verify/` | POST | 🔑 User | Verify eSewa payment |
| `/flywire/payment/` | POST | 🔑 User | Initiate Flywire payment |
| `/flywire/verify/` | POST | 🔐 Signature | Verify Flywire payment |

## System
| Endpoint | Method | Auth | Description |
|----------|--------|------|-------------|
| `/test/` | GET | ❌ | Health check |
| `/admin/` | GET | 🔑 Admin | Admin panel |

---

### 🔐 Authentication Levels:
- **❌** - Public access
- **🔑 User** - Authenticated users
- **🔑 Admin** - Admin users only  
- **🔐 Signature** - Webhook signature verification

*All endpoints return appropriate HTTP status codes and standardized error responses.*
---

# 🗺️ Frontend Routes

## Route Configuration
| Route | Component | Access | Description |
|-------|-----------|--------|-------------|
| `/` | `Home` | 🌐 Public | Landing page & platform overview |
| `/login` | `Login` | 🌐 Public | User authentication |
| `/register` | `Register` | 🌐 Public | New user registration |
| `/forgot-password` | `Fp` | 🌐 Public | Password recovery |
| `/reset` | `Reset` | 🌐 Public | Password reset |

## User Routes
| Route | Component | Access | Description |
|-------|-----------|--------|-------------|
| `/Exam` | `Exam` | 🔐 User | Exam booking & enrollment |
| `/Profile` | `Profile` | 🔐 User | Profile management |
| `/payfee` | `UniPayment` | 🔐 User | Payment processing |
| `/Checklist` | `Checklist` | 🔐 User | Exam preparation |
| `/top-Uni` | `Topuni` | 🔐 User | University information |

## Admin Routes
| Route | Component | Access | Description |
|-------|-----------|--------|-------------|
| `/admin/dashboard` | `Admin` | ⚡ Admin | Administrative dashboard |
| `/admin/users/all` | `UserM` | ⚡ Admin | User management |
| `/admin/users/add` | `Add` | ⚡ Admin | Add new users |

## Utility Routes
| Route | Component | Access | Description |
|-------|-----------|--------|-------------|
| `/comp` | `Component` | 🛠️ Dev | Component library |
| `/404` | `NotFound` | ❓ All | 404 error page |
| `*` | `NotFound` | ❓ All | Catch-all route |

---

### 🔐 Access Levels:
- **🌐 Public** - Accessible without authentication
- **🔐 User** - Requires user login
- **⚡ Admin** - Requires admin privileges  
- **🛠️ Dev** - Development & testing
- **❓ All** - Accessible from any route

*All protected routes automatically redirect unauthenticated users to login page.*

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

```
## ✨ Platform Overview
A modern, full-stack exam booking platform built with React.js and Django REST Framework, providing seamless exam enrollment and management experience for students and administrators.
# 🌐 Live Website Preview

## 🚀 Live Demo
**Website URL:** [merotestbooking.com](https://merotestbooking.com)

## 📱 Website Screenshot
![Image](Images/Screenshot_4.png)
![Image](Images/Screenshot_5.png)
### 🎯 Key Highlights
- **Secure JWT Authentication**
- **Dual Payment Gateway Integration** (eSewa + Flywire)
- **Role-Based Access Control**
- **Real-time Booking Management**
- **Multi-Currency Support**
- **Admin Dashboard & Analytics**

### 🛠️ Tech Stack
- **Frontend:** React.js, React Router, Modern CSS
- **Backend:** Django REST Framework, JWT Authentication
- **Payment:** eSewa & Flywire Integration
- **Database:** PostgreSQL/SQLite
- **Deployment:** Production-ready hosting

---

*Experience the platform live at [merotestbooking.com](https://merotestbooking.com)*
