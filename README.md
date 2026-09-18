# 🎓 Campus Connect

**Campus Connect** is a campus community platform that provides a centralized place for students, faculty, and administrators to interact with campus activities and information.

The application includes secure authentication, a protected dashboard, campus events, Lost & Found management, recent activities, notifications, and campus statistics.

---

## 🚀 Features

### 🔐 Authentication

* User registration and login
* Role-based registration

  * Student
  * Faculty
  * Admin
* JWT-based authentication
* Protected routes
* Token-based API authorization
* Automatic logout on `401 Unauthorized` responses

### 📊 Dashboard

* Centralized campus dashboard
* Campus statistics
* Recent activities
* Quick actions
* Events
* Lost & Found
* Notifications
* Logout functionality

### 📅 Campus Events

* View campus events
* Create events
* Delete events
* Event title and description

### 🔎 Lost & Found

* View lost items
* View found items
* Report lost items
* Report found items
* Filter Lost and Found records
* Store item details including:

  * Title
  * Description
  * Location
  * Type
  * Reporter
  * Creation date

### 📈 Campus Statistics

The dashboard displays campus statistics such as:

* Enrolled students
* Online users
* Total events
* Lost & Found records

---

## 🛠️ Tech Stack

### Frontend

* **React 19**
* **JavaScript (ES6+)**
* **React Router DOM 7**
* **Vite 7**
* **Axios**

### UI & Styling

* **Tailwind CSS**
* **Bootstrap 5**
* **Bootstrap Icons**
* Custom CSS

### Development Tools

* **ESLint**
* **Git**
* **GitHub**
* **npm**

---

## 🏗️ Application Architecture

```text
                        ┌───────────────┐
                        │     User      │
                        └───────┬───────┘
                                │
                                ▼
                     ┌────────────────────┐
                     │   React Frontend   │
                     │                    │
                     │ Landing Page       │
                     │ Login / Register   │
                     │ Dashboard          │
                     └─────────┬──────────┘
                               │
                               ▼
                     ┌────────────────────┐
                     │   React Router     │
                     │  Protected Routes  │
                     └─────────┬──────────┘
                               │
                               ▼
                     ┌────────────────────┐
                     │   Axios API Layer  │
                     │                    │
                     │ JWT Authorization  │
                     │ Request Interceptor│
                     │ Response Interceptor
                     └─────────┬──────────┘
                               │
                               ▼
                     ┌────────────────────┐
                     │    REST API        │
                     │     Backend        │
                     └────────────────────┘
```

---

## 📁 Project Structure

```text
CampusConnectFrontend/
│
├── public/
│
├── src/
│   ├── api/
│   │   └── axiosConfig.js
│   │
│   ├── assets/
│   │
│   ├── Components/
│   │   └── ProtectedRoute.jsx
│   │
│   ├── pages/
│   │   ├── Dashboard.jsx
│   │   ├── LandingPage.jsx
│   │   ├── Login.jsx
│   │   └── Register.jsx
│   │
│   ├── App.jsx
│   ├── App.css
│   ├── index.css
│   └── main.jsx
│
├── .gitignore
├── eslint.config.js
├── index.html
├── LICENSE
├── package.json
├── package-lock.json
├── postcss.config.js
├── tailwind.config.js
├── vite.config.js
└── README.md
```

---

## 🔗 Application Routes

| Route        | Description       | Access    |
| ------------ | ----------------- | --------- |
| `/`          | Landing Page      | Public    |
| `/login`     | User Login        | Public    |
| `/register`  | User Registration | Public    |
| `/dashboard` | Main Dashboard    | Protected |

---

## 🔌 API Integration

The frontend communicates with the backend using **Axios** and REST APIs.

### Authentication

```http
POST /api/auth/login
POST /api/auth/register
```

### Events

```http
GET    /api/events
POST   /api/events
DELETE /api/events/:id
```

### Lost & Found

```http
GET  /api/lostfound
POST /api/lostfound
```

### Campus Statistics

```http
GET /api/user/enrolled-count
```

---

## 🔑 Authentication Flow

```text
User
 │
 ▼
Login / Register
 │
 ▼
Backend Authentication
 │
 ▼
JWT Token
 │
 ▼
Browser Storage
 │
 ▼
ProtectedRoute
 │
 ▼
Dashboard
```

For authenticated API requests, the JWT token is sent using:

```http
Authorization: Bearer <JWT_TOKEN>
```

Axios interceptors are used to manage authentication headers and handle unauthorized responses.

When the backend returns a `401 Unauthorized` response, the authentication state is cleared and the user is redirected to the login page.

---

## ⚙️ Getting Started

### Prerequisites

Make sure you have the following installed:

* Node.js
* npm
* Git
* Campus Connect Backend API

### 1. Clone the Repository

```bash
git clone https://github.com/amitkamiya/CampusConnectFrontend.git
```

### 2. Navigate to the Project

```bash
cd CampusConnectFrontend
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Configure Environment Variables

Create a `.env` file in the project root:

```env
VITE_API_URL=http://localhost:8080
```

Make sure the Campus Connect backend is running on the configured URL.

### 5. Start the Development Server

```bash
npm run dev
```

The application will be available at:

```text
http://localhost:5173
```

---

## 📦 Available Scripts

### Development

```bash
npm run dev
```

Starts the Vite development server.

### Production Build

```bash
npm run build
```

Creates an optimized production build.

### Preview

```bash
npm run preview
```

Runs the production build locally.

### Lint

```bash
npm run lint
```

Checks the project for ESLint issues.

---

## 🔮 Future Enhancements

* Real-time notifications
* Student-to-student messaging
* User profile management
* Event registration
* Image upload for Lost & Found
* Advanced search and filtering
* Pagination
* Course management
* Campus library integration
* Granular role-based permissions

---

## 👨‍💻 Author

**Amit Kumar**

Computer Science & Engineering Student

[GitHub](https://github.com/amitkamiya)

---

## 📄 License

This project is licensed under the **BSD 2-Clause License**.

See the [LICENSE](LICENSE) file for details.
