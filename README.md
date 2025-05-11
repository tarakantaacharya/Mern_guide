# MERN Stack Starter Setup

This guide outlines how to create and start a MERN (MongoDB, Express, React, Node.js) stack project using basic folder structure and command-line steps.


## 📁 Folder Structure

```
mern-app/
├── backend/         # Node.js + Express + MongoDB API
│   └── node_modules
│   └── package.json  
├── frontend/        # React frontend
│   └── node_modules  
│   └── src/
│   └── public/
│   └── .gitignore
│   └── package.json
```

## 🧰 Tech Stack

- **MongoDB** – Database
- **Express.js** – Web framework for Node.js
- **React.js** – Frontend UI
- **Node.js** – Runtime environment


## 🛠️ Setup Instructions

### 1. Create the Project Root

```bash
mkdir mern-app
cd mern-app
````

---

### 2. Setup Backend

```bash
mkdir backend
cd backend
npm init -y
npm install express mongoose cors dotenv
cd ..
```

---

### 3. Setup Frontend

```bash
npx create-react-app frontend
cd frontend
npm install axios react-router-dom
cd ..
```

---

### 4. (Optional) Run Both Servers Together

Install concurrently in root or backend:

```bash
npm install -g concurrently  # Or: npm install concurrently
```

In a root-level `package.json`:

```json
"scripts": {
  "start": "concurrently \"npm run dev --prefix backend\" \"npm start --prefix frontend\""
}
```

In `backend/package.json`:

```json
"scripts": {
  "dev": "nodemon index.js"
}
```

## Frontend Folder 

### ✅ `public/` folder (mostly static stuff)

* Contains files that **don’t get processed by Webpack**.
* Mostly used for:

  * `index.html` – The single HTML page where your React app is injected.
  * `favicon.ico`, logos – Browser tab icon and static branding assets.
  * Any publicly accessible static files (e.g., manifest, images, etc.).
* **You rarely edit this folder except maybe the HTML title or favicon.**

---

### ✅ `src/` folder (main development area)

This is where **95% of your work** happens.

Key areas include:

| File/Folder             | Purpose                                                        |
| ----------------------- | -------------------------------------------------------------- |
| `index.js`              | Entry point – renders your app into `index.html`.              |
| `App.js`                | Main app component – acts as a container for all routes/pages. |
| `components/`           | Reusable UI components (buttons, cards, navbars, etc.).        |
| `pages/` or `views/`    | Full pages/screens of the app (like Home, Dashboard, Login).   |
| `assets/`               | Custom images, styles, or icons used in components.            |
| `services/`             | API calls via Axios (for backend communication).               |
| `context/` or `store/`  | State management using Context API, Redux, etc.                |
| `App.css` / `index.css` | Global stylesheets (can be customized).                        |

---

### 🛠️ What You Typically Update in `src/`:

* Add routes to new pages (`React Router`).
* Create and update components.
* Connect to backend APIs using Axios.
* Manage global or local state.
* Apply styling or animations.

---

```
🗂️ MERN Stack Folder Structure (Most Commonly Used)
bash
Copy
Edit
mern-app/
├── backend/
│   ├── config/             # DB config, environment setup
│   │   └── db.js
│   ├── controllers/        # Business logic for routes
│   │   └── authController.js
│   ├── models/             # Mongoose schemas/models
│   │   └── User.js
│   ├── middleware/         # Auth, error handlers, etc.
│   │   └── authMiddleware.js
│   ├── routes/             # API routes
│   │   └── authRoutes.js
│   ├── utils/              # Helper functions (e.g., sendEmail.js, validators.js)
│   ├── .env                # Environment variables
│   ├── server.js           # Express app entry point
│   └── package.json
│
├── frontend/
│   ├── public/             # Static HTML, favicon, manifest
│   │   └── index.html
│   ├── src/
│   │   ├── assets/         # Images, CSS, logos
│   │   ├── components/     # Reusable UI components
│   │   │   └── Navbar.js
│   │   ├── pages/          # Full pages/screens (Login, Dashboard)
│   │   │   └── Login.js
│   │   ├── services/       # Axios API services (e.g., api.js)
│   │   ├── context/        # React Context or Redux for global state
│   │   ├── App.js          # Main app component
│   │   ├── index.js        # Entry point
│   │   └── App.css / index.css
│   └── package.json
│
├── .gitignore
├── README.md
```
