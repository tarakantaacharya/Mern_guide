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

Run both servers:

```bash
npm start
```
