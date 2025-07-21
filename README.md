# 🍎 E-Commerce API (Backend)

A modular, scalable backend for an e-commerce platform following a modern **Next.js-style architecture** with TypeScript and PostgreSQL. Built for maintainability and clean separation between user/admin roles.

---

## 📁 Project Structure

Follows **controller → route → service → type** pattern per endpoint:

```
src/
├── features
|   ├── admin/
│        ├── analutics/(controller → route → service → type).ts
│        ├── auth/(controller → route → service → type).ts
│        ├── blog/(controller → route → service → type).ts
|        ├── product/(controller → route → service → type).ts
|        ├── security/(controller → route → service → type).ts
│        └── images/(controller → route → service → type).ts
|   ├── session/          ← session (creation,validation, decoding) 
|   ├── admin/
│        ├── controllers/
│        ├── routes/
│        ├── services/
│        └── types/
├── login/            ← logic, no public route
├── routes/           ← handles logic for landing page i.e public files 
├── config/
│   └── db.ts         ← PostgreSQL connection pool
├── middleware/       ← middleman to handle api session validation and payload size
├── routes/           ← public routes for fetching all priducts for user and admin 
|__ index.ts          ← function initialization
└── app.ts            ← Express app init
```

---

## 🚀 Features

* PostgreSQL with `pg` and `pg-pool`
* Graceful shutdown handling for signals and errors
* Modular file structure (routes, controllers, services, types)
* Type-safe request validation
* User/Admin role separation
* Centralized error handling
* Session and login logic without public routes

---

## ⚙️ Setup & Installation

1. **Clone the repo**

```bash
git clone (https://github.com/CodeComrade001/e_commerce-_api)
cd e-commerce-api
```

2. **Install dependencies**

```bash
npm install
```

3. **Create `.env` file**

Include your PostgreSQL and app configs:

```env
PORT=3000
DATABASE_URL=postgresql://username:password@localhost:5432/your_db
```

4. **Start the development server**

```bash
npm start
```

If successful, you’ll see:

```
✅ Ready to accept queries (pool created).
🚀 Server running on http://localhost:3000
```

---

## 🧠 Internal Logic

* `app.ts`: Initializes middleware, routes, and the Express app.
* `server.ts`:

  * Connects the database pool
  * Handles graceful shutdown on `SIGINT`, `SIGTERM`, `uncaughtException`, `unhandledRejection`

---

## 🚩 Known Issues

* ❌ No Docker integration yet.
* ❌ Not yet connected to production-ready DB (e.g., Supabase).
* ❌ Image upload functionality pending.
* ❌ caching mechanism to reduce database load.

---

## 🧪 Tests (Coming Soon)

* [ ] Unit tests for services
* [ ] Integration tests for API routes

---

## 🗃️ Tech Stack

* **Node.js** + **Express**
* **TypeScript**
* **PostgreSQL**
* **pg-pool** (for connection pooling)

---

## 🙌 Contributions

WIP project, still in local development. Contributions welcome after v1 base release.

---

## 📃 License

MIT
