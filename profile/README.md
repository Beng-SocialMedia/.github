<div align="center">

# 📸 Beng — Social Media Platform

An Instagram-like social network with **feed, stories, real-time messaging, and audio/video calls** — a full-stack project built end to end.

<br/>

[![Live Demo](https://img.shields.io/badge/▶_LIVE_DEMO-Open_App-FF2D55?style=for-the-badge&logo=vercel&logoColor=white)](https://social-media-blush-theta.vercel.app/)
[![API Docs](https://img.shields.io/badge/⚙️_API_DOCS-Swagger-0B7285?style=for-the-badge&logo=railway&logoColor=white)](https://backend-production-0ce99.up.railway.app/docs/)

**🌐 Frontend** · [social-media-blush-theta.vercel.app](https://social-media-blush-theta.vercel.app/)
**⚙️ Backend API** · [backend-production-0ce99.up.railway.app/docs](https://backend-production-0ce99.up.railway.app/docs/)

<br/>

![Status](https://img.shields.io/badge/status-live-success?style=flat-square)
![Frontend](https://img.shields.io/badge/frontend-Vercel-black?style=flat-square&logo=vercel)
![Backend](https://img.shields.io/badge/backend-Railway-0B0D0E?style=flat-square&logo=railway)
![TypeScript](https://img.shields.io/badge/TypeScript-end--to--end-3178C6?style=flat-square&logo=typescript&logoColor=white)

</div>

---

## ✨ Features

- 🏠 **Feed** — posts, image carousel (≤5) & video, nested comments with @mentions, likes, follow. Mixed ranking algorithm blends followed users with relevant public posts.
- 📖 **Stories** — 24h auto-expiry, text/emoji overlays, viewer with gestures, view counts, archive.
- 💬 **Messaging** — 1-1 & group chat over WebSocket: typing indicators, presence, read receipts, reactions, voice notes, image/video, emoji/sticker/GIF, message recall, reply-to.
- 📞 **Calls** — 1-1 & group audio/video calls via WebRTC SFU, with managed signaling, TURN, and noise cancellation.
- 🔔 **Notifications & Search** — in-app + browser notifications with sound; Postgres full-text search across users and posts.
- 🔐 **Auth** — JWT with access token in memory + refresh token in an httpOnly cookie.

## 🛠️ Tech Stack

| Layer       | Technologies                                                        |
| ----------- | ------------------------------------------------------------------- |
| Frontend    | React 18 · Vite · TypeScript · Tailwind CSS · Zustand               |
| Backend     | Node.js · Express · TypeScript                                      |
| Database    | PostgreSQL 16 · Prisma ORM                                          |
| Real-time   | Socket.IO (chat, presence, read receipts)                          |
| Calls       | LiveKit Cloud (WebRTC SFU)                                          |
| Storage     | S3-compatible object storage · presigned uploads                   |
| API Docs    | Swagger UI · OpenAPI 3.1 (schema-first from Zod)                    |
| Auth        | JWT · httpOnly refresh cookie                                       |
| Deployment  | Vercel (frontend) · Railway (backend) · Cloudflare (S3-compatible)                              |

## 🔍 Engineering Highlights

- **Type-safe end to end** — shared TypeScript types from database through API to UI.
- **Schema-first APIs** — Zod is the single source of truth for both runtime validation and the OpenAPI docs.
- **Real-time architecture** — Socket.IO powers live messaging, typing, presence, and read receipts.
- **WebRTC calls** — group audio/video built on a managed SFU, surfaced as call events inside chat threads.
- **Search** — Postgres full-text search using `ts_vector` + GIN indexes with relevance ranking.
- **Clean structure** — feature-based modules, thin routes / thick services, versioned Prisma migrations.

## 🚦 Quick Start

**Prerequisites:** Node.js 20+, Docker Desktop.

```bash
# Backend
cd backend
npm install
cp .env.example .env        # set JWT secrets, GIPHY + LIVEKIT keys
docker compose up -d        # Postgres + object storage
npx prisma migrate dev
npm run dev                 # → http://localhost:3000  (Swagger at /docs)

# Frontend (in a second terminal)
cd frontend
npm install
npm run dev                 # → http://localhost:5173
```

## 📦 Repositories

Split into two repos under the [Beng-SocialMedia](https://github.com/Beng-SocialMedia) organization:

[![Backend](https://img.shields.io/badge/⚙️_Backend-Express_+_Prisma-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Beng-SocialMedia/Backend)
[![Frontend](https://img.shields.io/badge/💻_Frontend-React_+_Vite-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Beng-SocialMedia/Fontend)
