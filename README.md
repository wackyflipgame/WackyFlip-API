# 🔗 WackyFlip-API

Public API Gateway for the [Wacky Flip](https://wackyflip.com) Universe
A centralized and scalable RESTful API for accessing player data, leaderboards, metadata, and game-related content across all Wacky Flip frontends and services.

---

## 📌 Overview

`WackyFlip-API` powers the backbone of **WackyFlip.com**, providing unified access to essential game data for web, mobile, and third-party services. Whether you're fetching player stats, submitting scores, loading leaderboards, or syncing metadata across mini-games — this is the core gateway.

---

## ⚙️ Key Features

* 🧠 **Player Profiles API**
  Retrieve and manage public-facing player data, including usernames, avatars, high scores, and achievements.

* 🏆 **Leaderboard Access**
  Query global and game-specific leaderboards by period, score type, or game mode.

* 🎮 **Game Metadata API**
  Serve metadata about games, categories, difficulty levels, and release info to frontends.

* 📥 **Score Submission Endpoint**
  Secure endpoints for submitting, verifying, and recording gameplay session data.

* 🔐 **Token-Based Auth Support**
  JWT and OAuth2 support for secure access and third-party integrations.

* 🌍 **CORS & Rate Limiting**
  API security and throttling policies for public consumption.

---

## 🧱 Tech Stack

* **Node.js + Express** – Lightweight and scalable API framework
* **MongoDB** – Persistent storage for player profiles and session data
* **Redis** – Leaderboard caching and rate limiting
* **JWT** – Authentication and token validation
* **Swagger** – Auto-generated interactive API documentation

---

## 📁 Directory Structure

```
WackyFlip-API/
├── src/
│   ├── controllers/      # Business logic per route (profiles, scores, games)
│   ├── routes/           # Express route definitions
│   ├── models/           # Mongoose schemas
│   ├── middleware/       # Auth, validation, rate limiting
│   └── services/         # Leaderboard logic, metadata fetchers
├── config/
│   └── db.js             # Mongo + Redis connection logic
├── docs/
│   └── swagger.yaml      # OpenAPI schema for Swagger UI
├── tests/                # API test suite
├── .env                  # Environment variables
├── app.js                # Main API entry point
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/wackyflipgame/WackyFlip-API.git
cd WackyFlip-API
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment

Create a `.env` file based on `.env.example` and fill in your database credentials, JWT secret, and CORS policy.

### 4. Run the Server

```bash
npm start
```

The API will be available at `http://localhost:5000`

---

## 📚 Example Endpoints

| Method | Endpoint                    | Description                         |
| ------ | --------------------------- | ----------------------------------- |
| `GET`  | `/api/leaderboards/global`  | Top scores across all games         |
| `GET`  | `/api/leaderboards/:gameId` | Scores for a specific game          |
| `GET`  | `/api/users/:userId`        | Public user profile and stats       |
| `POST` | `/api/scores/submit`        | Submit a new score (auth required)  |
| `GET`  | `/api/games`                | List all available [Wacky Flip](https://wackyflip.com) games |
| `GET`  | `/api/status`               | Server health and metadata info     |

---

## 🧪 Testing

```bash
npm run test
```

Uses Jest and Supertest for endpoint validation and response integrity.

---

## 🔐 Authentication

* Use `Bearer <JWT>` in the `Authorization` header for authenticated endpoints.
* Guest access is allowed for public leaderboard and game metadata queries.

---

## 📘 API Docs

Swagger UI available at:

```
http://localhost:5000/api-docs
```

Auto-generated from `docs/swagger.yaml`.

---

## 🤝 Contributing

We welcome contributions for:

* New data endpoints
* Score integrity checks
* Third-party integrations
* GraphQL support (future)

Fork the repo → create a feature branch → open a PR!

---

## 📜 License

MIT License © Wacky Flip Studios

---

## 🔗 Related Repositories

* [`WackyFlip-Web`](https://github.com/wackyflipgame/WackyFlip-Web) – Game frontend using this API
* [`WackyFlip-Stats`](https://github.com/wackyflipgame/WackyFlip-Stats) – Backend data store for scores and analytics
* [`WackyFlip-Mobile`](https://github.com/wackyflipgame/WackyFlip-Mobile) – Mobile client consuming API endpoints
