\# 🎓 Campus Connect



Campus Connect is a \*\*campus community platform\*\* designed to connect students, faculty, and administrators through a centralized web application.



The platform provides secure authentication, a protected dashboard, campus events management, lost-and-found reporting, recent activities, and campus statistics.



\## 🚀 Features



\### 🔐 Authentication



\* User registration and login

\* Role-based registration:



&#x20; \* Student

&#x20; \* Faculty

&#x20; \* Admin

\* JWT-based authentication

\* Token storage using `localStorage`

\* Protected routes for authenticated users

\* Automatic logout and redirect when a `401 Unauthorized` response is received



\### 🏠 Landing Page



\* Responsive navigation

\* Platform introduction

\* Hero section with call-to-action buttons

\* Campus platform statistics

\* Feature highlights

\* Authentication navigation



\### 📊 Dashboard



After authentication, users can access a protected dashboard containing:



\* Quick actions

\* Recent activities

\* Campus events

\* Lost \& found items

\* Campus statistics

\* Notifications

\* Logout functionality



\### 📅 Campus Events



Users can interact with campus events through the backend API:



\* View events

\* Create events

\* Delete events



Each event contains:



\* Title

\* Description



\### 🔎 Lost \& Found



The platform provides a dedicated lost-and-found section where users can:



\* View lost items

\* View found items

\* Report lost items

\* Report found items

\* Filter items using Lost and Found tabs



Each report can contain:



\* Item title

\* Description

\* Location

\* Type (`LOST` / `FOUND`)

\* Reporter information

\* Creation date



\### 📈 Campus Statistics



The dashboard displays campus-related statistics such as:



\* Enrolled students

\* Online users

\* Number of events

\* Lost-and-found records



\---



\## 🛠️ Tech Stack



\### Frontend



\* \*\*React 19\*\*

\* \*\*JavaScript (ES6+)\*\*

\* \*\*React Router DOM 7\*\*

\* \*\*Vite 7\*\*

\* \*\*Axios\*\*



\### Styling



\* \*\*Tailwind CSS 3\*\*

\* \*\*Bootstrap 5\*\*

\* \*\*Bootstrap Icons\*\*

\* Custom CSS

\* Inter Font



\### Development Tools



\* \*\*ESLint 9\*\*

\* \*\*Git\*\*

\* \*\*GitHub\*\*

\* \*\*npm\*\*



\---



\## 🏗️ Application Architecture



The frontend follows a component-based React architecture:



```text

User

&#x20; │

&#x20; ▼

React Frontend

&#x20; │

&#x20; ├── Landing Page

&#x20; ├── Login / Register

&#x20; └── Protected Dashboard

&#x20;         │

&#x20;         ├── Events

&#x20;         ├── Lost \& Found

&#x20;         ├── Activities

&#x20;         └── Campus Statistics

&#x20;         │

&#x20;         ▼

&#x20;    Axios API Layer

&#x20;         │

&#x20;         ▼

&#x20;     Backend REST API

```



\---



\## 📁 Project Structure



```text

CampusConnectFrontend/

│

├── public/

│   └── vite.svg

│

├── src/

│   │

│   ├── api/

│   │   └── axiosConfig.js

│   │

│   ├── assets/

│   │   └── react.svg

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

│   ├── App.css

│   ├── App.jsx

│   ├── index.css

│   └── main.jsx

│

├── eslint.config.js

├── index.html

├── package.json

├── package-lock.json

├── postcss.config.js

├── tailwind.config.js

├── vite.config.js

└── README.md

```



\---



\## 🔗 Application Routes



| Route        | Description       | Access    |

| ------------ | ----------------- | --------- |

| `/`          | Landing Page      | Public    |

| `/login`     | User Login        | Public    |

| `/register`  | User Registration | Public    |

| `/dashboard` | Main Dashboard    | Protected |



Unknown routes automatically redirect to the landing page.



\---



\## 🔌 Backend API



The frontend communicates with the backend using \*\*Axios\*\*.



The API base URL is configured through the `VITE\_API\_URL` environment variable.



\### Authentication



```http

POST /api/auth/login

POST /api/auth/register

```



\### Events



```http

GET    /api/events

POST   /api/events

DELETE /api/events/:id

```



\### Lost \& Found



```http

GET  /api/lostfound

POST /api/lostfound

```



\### Campus Statistics



```http

GET /api/user/enrolled-count

```



\---



\## ⚙️ Getting Started



\### Prerequisites



Make sure you have the following installed:



\* Node.js

\* npm

\* Git

\* Running Campus Connect backend API



\### 1. Clone the Repository



```bash

git clone https://github.com/amitkamiya/CampusConnectFrontend.git

```



\### 2. Navigate to the Project



```bash

cd CampusConnectFrontend

```



\### 3. Install Dependencies



```bash

npm install

```



\### 4. Configure Environment Variables



Create a `.env` file in the project root:



```env

VITE\_API\_URL=http://localhost:8080

```



The frontend will then communicate with:



```text

http://localhost:8080/api

```



Make sure your backend is running on the configured URL.



\### 5. Start the Development Server



```bash

npm run dev

```



The Vite development server will provide a local URL, typically:



```text

http://localhost:5173

```



\---



\## 📦 Available Scripts



\### Development



```bash

npm run dev

```



Starts the Vite development server.



\### Production Build



```bash

npm run build

```



Creates an optimized production build.



\### Preview Production Build



```bash

npm run preview

```



Runs the production build locally.



\### Lint



```bash

npm run lint

```



Checks the project for ESLint issues.



\---



\## 🔑 Authentication Flow



The application uses a token-based authentication flow:



```text

Login

&#x20; │

&#x20; ▼

Backend Authentication

&#x20; │

&#x20; ▼

JWT Token

&#x20; │

&#x20; ▼

localStorage

&#x20; │

&#x20; ▼

ProtectedRoute

&#x20; │

&#x20; ▼

Dashboard

```



Axios automatically attaches the token to API requests:



```http

Authorization: Bearer <token>

```



If the backend returns `401 Unauthorized`, the frontend clears the stored token and redirects the user to the login page.



\---



\## 🧩 Key Components



\### `ProtectedRoute.jsx`



Responsible for protecting authenticated routes.



It checks whether a valid authentication token exists before allowing access to protected pages.



\### `axiosConfig.js`



Centralizes API communication and handles:



\* API base URL

\* Authorization headers

\* Request interceptors

\* Response interceptors

\* Unauthorized responses



\### `Dashboard.jsx`



The main authenticated application interface containing:



\* Events

\* Lost \& Found

\* Statistics

\* Recent activities

\* Quick actions



\### `Login.jsx`



Handles user authentication and stores the returned token.



\### `Register.jsx`



Provides account creation with:



\* Full name

\* Username

\* Email

\* Password

\* Password confirmation

\* User role



\---



\## 🔮 Future Improvements



Potential improvements for future versions include:



\* Real-time notifications

\* Direct student-to-student messaging

\* Course management

\* Campus library integration

\* Event registration

\* Advanced search and filtering

\* Profile management

\* Role-based dashboard permissions

\* Image upload for lost-and-found items

\* Pagination for events and lost-and-found records

\* Responsive mobile-first improvements



\---



\## 👨‍💻 Author



\*\*Amit Kumar\*\*



Computer Science \& Engineering Student



GitHub: \[@amitkamiya](https://github.com/amitkamiya)



\---



\## 📄 License



This project is licensed under the \*\*BSD 2-Clause License\*\*.



See the `LICENSE` file for more information.



```



\### One important correction



Your GitHub repository currently says the frontend expects a backend API and documents `VITE\_API\_URL` as the backend base URL. So \*\*don't write that this is a complete full-stack application\*\* in this frontend repository's README unless you also document/link the backend repository.



Also, your current repo has only \*\*3 commits\*\*, so I would avoid adding fake sections such as "Contributors", "Production deployment", "CI/CD", or screenshots unless you actually have them.



\[Your CampusConnectFrontend repository](https://github.com/amitkamiya/CampusConnectFrontend?utm\_source=chatgpt.com)

```



