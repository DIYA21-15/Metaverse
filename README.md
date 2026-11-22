# 🌐 Metaverse 2D

A **real‑time 2D metaverse** where users can move around a shared space, see each other live, and interact through proximity‑based features like chat and requests. This project is focused on learning and building **full‑stack, real‑time systems** using modern web technologies.

![Animation](https://github.com/user-attachments/assets/f7f053b8-5e17-4a21-8b4c-17a8064315b2)

---

## ✨ Features

* 🧍‍♂️ **Real‑time multiplayer movement** (WebSockets)
* 🗺️ **2D tile‑based world** rendered on `<canvas>`
* 💬 **Proximity‑based chat system**
* 🤝 **User interaction system** (requests, accept / reject flows)
* 👥 **Remote & local player synchronization**
* 🔄 **Session‑based rooms / spaces**
* 🧠 Clean separation between **game logic**, **networking**, and **UI**

---

## 🛠️ Tech Stack

### Frontend

* **React** + **TypeScript**
* **Canvas API** (custom game engine logic)
* **Tailwind CSS** (UI & overlays)

### Backend

* **Node.js**
* **Express**
* **WebSockets (ws)** for real‑time communication

### Database

* **PostgreSQL**
* **Prisma ORM**

### Tooling

* **TurboRepo** (monorepo setup)
* **Docker** (local PostgreSQL)
* **ESLint + Prettier**

---

## 📁 Project Structure (Simplified)

```
metaverse-2d/
│
├── metaverse/
|    └── apps/
│    |    ├── http/        # Express HTTP server
│    |    ├── ws/          # WebSocket server
│    |    └── frontend/    # React frontend
│    |
|    ├── packages/
│        └── db/          # Prisma client & schema
│
├── tests/           
└── README.md
```

---

## 🚀 Getting Started

⚠️ At the moment, authentication is **automatic** for development purposes. Opening the app in **multiple browser windows or tabs** will create and connect different users to the same space.


### 1️⃣ Clone the repository

```bash
git clone https://github.com/navu545/metaverse-2d.git
cd metaverse-2d
```

### 2️⃣ Install dependencies

```bash
npm install
```

### 3️⃣ Setup Database

* Make sure **Docker** is installed and running
* Start a PostgreSQL container (example):

```bash
docker run --name metaverse-postgres \
  -e POSTGRES_PASSWORD=mysecretpassword \
  -p 5432:5432 \
  -d postgres
```

* Create a `.env` file and add:

```env
DATABASE_URL="postgresql://postgres:mysecretpassword@localhost:5432/postgres"
```

* Run Prisma migrations

```bash
npx prisma migrate dev
```

### 4️⃣ Start the project

This project runs **three separate services**:

* Frontend (React)
* HTTP server (Express)
* WebSocket server

From the root:

```bash
npm run dev
```

Or individually:

```bash
# Frontend
cd metaverse/apps/web && npm run dev

# HTTP server
cd metaverse/apps/http && npm run dev

# WebSocket server
cd metaverse/apps/ws && npm run dev
```

---

## 📚 Credits & Resources

This project is **not a direct clone**, but parts of the **HTTP server, WebSocket server, and database setup** were initially inspired by the following learning resources:

* **Harkirat Singh – 2D Metaverse**
  GitHub: [https://github.com/hkirat/2d-metaverse/tree/main/metaverse](https://github.com/hkirat/2d-metaverse/tree/main/metaverse)
  Used as a reference for:

  * Initial HTTP server structure
  * Initial WS server structure
  * Authentication & session flow

* **2D RPG Canvas Game (Learning Resource)**
  Drive link: [https://drive.google.com/file/d/1Lqkuc92ydqC6WIYAgq4YTU4K27w-1JIv/view](https://drive.google.com/file/d/1Lqkuc92ydqC6WIYAgq4YTU4K27w-1JIv/view)
  Reference material for:

  * Canvas-based rendering
  * Game loop & update cycles
  * Sprite handling and movement foundations

### How this project differs

* The **WebSocket server logic** has been **extensively rewritten** to support:
  
  * Real-time multiplayer movement
  * Proximity detection
  * Interaction state management (requests, accept/reject)
* The **database schema** has been modified and extended to support multiplayer sessions.
* The **game engine layer** is custom-built and adapted specifically for a shared multiplayer environment.
* The **HTTP server** remains closer to the original reference and is used mainly for authentication and bootstrapping.

This repository is maintained as an **independent learning project** that has evolved well beyond its original references.

---

## 🧠 Learning Goals Behind This Project

## 🧩 Current Limitations

* No avatar selector UI yet (single default sprite)
* No map / space selection UI (single shared space)
* Simple sprite-based movement system
* No jumping or advanced physics
* Grid-based positional logic
* Desktop-first experience (limited mobile optimization)

---

## 🔮 Planned Improvements

* 🗺️ Room / space–based interactions
* 🧍 Multiple avatar sprites & customization
* 🎮 Smoother movement interpolation
* 🧠 Cleaner state synchronization abstractions
* 🔊 Voice and video communication
* 📱 Improved mobile support

---

## 👨‍💻 Author

**Diya Bisht**

---

## 📜 License

This project currently does **not use a license**.

---

> ⚠️ This project is built primarily for **learning and experimentation** and is continuously evolving.
