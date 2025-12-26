# Mini Chat App (Node + Express + EJS + MongoDB) 🔧

A small, educational chat/message app that demonstrates a full‑stack CRUD flow using Node.js, Express, EJS templates and MongoDB (via Mongoose). It's intentionally minimal and ideal as a learning project or starter template to extend.

---

## 🔍 Project Overview

- **Backend:** Node.js + Express
- **Database:** MongoDB (local) with Mongoose ODM
- **Views:** EJS templates (`views/index.ejs`, `views/new.ejs`, `views/edit.ejs`)
- **Styling:** `public/style.css`
- **Port:** 8080

Features:
- Create (POST) a chat message
- Read (GET) all chat messages
- Update (PUT) a chat message
- Delete (DELETE) a chat message
- Simple seed script to insert sample chats

---

## 🧩 Files & Structure

```
index.js            # App entry, routes and DB connection
init.js             # Seeds DB with example chats
models/chat.js      # Mongoose model for Chat
views/              # EJS templates (index, new, edit)
public/style.css    # Static styles
package.json
README.md
```

---

## ⚙️ Prerequisites

- Node.js (recommended v18+)
- npm (comes with Node.js)
- MongoDB running locally (default connection used: `mongodb://127.0.0.1:27017/whatsapp`)

> Note: If you use a managed MongoDB service or a different host/port, update the connection string in `index.js` and `init.js` accordingly.

---

## 🚀 Setup & Run

1. Clone the repo and change into the project directory:

```bash
cd MongowithExpress
```

2. Install dependencies:

```bash
npm install
```

3. Make sure MongoDB is running locally (on Windows you can start the MongoDB service or run `mongod` from your installation path).

4. (Optional) Seed the database with sample chats:

```bash
node init.js
```

5. Start the application:

```bash
node index.js
```

6. Open your browser to:

```
http://localhost:8080/chats
```

Tip: If you have `nodemon` installed you can run `nodemon index.js` for automatic reloads.

---

## 🔁 Routes & Usage

- GET  /chats — view all chat messages
- GET  /chats/new — form to create a new message
- POST /chats — submit new message
- GET  /chats/:id/edit — form to edit a message
- PUT  /chats/:id — update message (uses `method-override` via `_method`)
- DELETE /chats/:id — delete a message

Forms use `method-override` with the `_method` hidden field to allow PUT/DELETE from HTML forms.

---

## Model (for reference)

`models/chat.js` defines a `Chat` schema with fields:
- `from` (String, required)
- `to` (String, required)
- `message` (String, 50 char max)
- `created_at` (stored as a string in the current implementation)

---

## ✨ Improvements / Next steps

- Store `created_at` as a Date type in Mongoose (to enable sorting and formatting)
- Add validation and user-friendly error messages
- Add authentication or user profiles to tie messages to users
- Add pagination, search, or real-time updates (Socket.io)
- Add tests and CI workflows

---

## 📬 Contributing

This repo is a learning project — feel free to fork, open issues, or submit PRs. For quick changes, open an issue or send a PR with a brief description.

---

## 📄 License

Open source — use as you like.

---
