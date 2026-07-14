# Expense Management System

A full-stack web application designed to help users track and manage their daily expenses. This project features secure user authentication, protected routes, and a responsive frontend connected to a robust RESTful API backend.

## 🚀 Features

*   **User Authentication:** Secure registration and login flows.
*   **Protected Routing:** Dashboard and expense data are restricted to authenticated users via local storage validation.
*   **Concurrent Execution:** Seamlessly run both the frontend React client and the backend Node.js server simultaneously with a single command.
*   **REST API Integration:** Backend configured to handle client requests using Express and MongoDB.

## 🛠️ Tech Stack

**Frontend**
*   React
*   React Router DOM (for navigation and protected routes)

**Backend**
*   Node.js
*   Express.js
*   MongoDB (with Mongoose ORM)

**Key Dependencies**
*   `concurrently`: Runs both client and server concurrently in development.
*   `cors`: Enables Cross-Origin Resource Sharing.
*   `dotenv`: Manages environment variables securely.
*   `morgan`: HTTP request logger middleware.

---

## 📂 Project Structure

This project uses a standard full-stack structure where the frontend is nested within a `client` directory.

```text
📦 Expanse-Management-System
 ┣ 📂 client (React Frontend)
 ┃ ┣ 📂 src
 ┃ ┃ ┣ 📂 pages
 ┃ ┃ ┃ ┣ 📜 HomePage.js
 ┃ ┃ ┃ ┣ 📜 Login.js
 ┃ ┃ ┃ ┗ 📜 Register.js
 ┃ ┃ ┗ 📜 App.js (Routing setup)
 ┣ 📜 server.js (Backend entry point)
 ┗ 📜 package.json
```

---

## ⚙️ Installation & Setup

**1. Clone the repository**
```bash
git clone <your-repository-url>
cd Expanse-Management-System
```

**2. Install Root (Backend) Dependencies**
```bash
npm install
```

**3. Install Client (Frontend) Dependencies**
```bash
cd client
npm install
cd ..
```

**4. Environment Variables**
Create a `.env` file in the root directory and add your specific configuration (example below):
```env
PORT=8080
MONGO_URI=your_mongodb_connection_string
```

---

## 💻 Available Scripts

In the project directory, you can run the following scripts defined in the root `package.json`:

| Command | Description |
| :--- | :--- |
| `npm run dev` | **Recommended:** Runs both the Node server and the React client simultaneously using concurrently. |
| `npm run server` | Starts the backend server using nodemon for automatic restarts on file changes. |
| `npm run client` | Starts the React frontend on its own. |
| `npm start` | Starts the backend server using node (for production). |

---

## 🛣️ Application Routing

The frontend utilizes `react-router-dom` to manage navigation and protect authenticated views:

*   **`/` (Home):** The main dashboard. Wrapped in a `<ProtectedRoutes>` component that checks for a valid `user` object in `localStorage`. If unauthenticated, it redirects to the login screen.
*   **`/login`:** The user authentication page.
*   **`/register`:** The new user sign-up page.
