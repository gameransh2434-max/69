# QWE Community — Railway Deployment

Full-stack deployment: Express API + WebSocket world chat + React frontend,
all in one pre-built bundle. **Drag-and-drop ready.**

## What's inside

| File | Purpose |
|------|---------|
| `server.mjs` | Express API + WebSocket + serves frontend |
| `setup.mjs` | Creates DB tables + seeds all data + creates admin |
| `public/` | Pre-built React frontend |
| `railway.json` | Railway auto-config |
| `.env` | Pre-filled with SMTP & admin credentials |

## Deploy in 4 steps

### Step 1 — Create Railway project
1. Go to [railway.app](https://railway.app) → New Project
2. Choose **Deploy from local directory** (or upload ZIP)
3. Drag and drop this folder

### Step 2 — Add PostgreSQL
- In Railway dashboard → **+ New Service** → **Database** → **PostgreSQL**
- Railway automatically sets `DATABASE_URL` as a variable ✅

### Step 3 — Set environment variables
Go to your service → **Variables** tab and add everything from `.env`:

| Variable | Value |
|----------|-------|
| `SESSION_SECRET` | Change to a long random string |
| `SMTP_USER` | `gameransh2434@gmail.com` (pre-filled) |
| `SMTP_PASS` | `gtaz pwid otcm hqsk` (pre-filled) |
| `ADMIN_EMAIL` | `gameransh2434@gmail.com` |
| `ADMIN_PASSWORD` | `gameransh2434@gmail.com` |
| `NODE_ENV` | `production` |

> `DATABASE_URL` is set automatically when you add the PostgreSQL service.

### Step 4 — Run one-time DB setup
In Railway → your service → **Terminal** (or via Railway CLI):
```bash
node setup.mjs
```

This creates all database tables and seeds:
- All 11 reward categories
- 70+ rewards across all categories
- Admin account (gameransh2434@gmail.com)

The server then starts automatically and stays running.

---

## Admin Login
- **URL:** `https://your-app.railway.app`
- **Email:** `gameransh2434@gmail.com`
- **Password:** `gameransh2434@gmail.com`

## Features
- ✅ Full REST API (`/api/*`)
- ✅ Live WebSocket world chat (`/api/chat/ws`)
- ✅ JWT authentication + OTP email verification
- ✅ Admin panel
- ✅ Claims, tickets, notifications system
- ✅ Reward categories & leaderboard

## Notes
- Railway auto-assigns PORT — the server reads it automatically
- SMTP is pre-configured for OTP emails (Gmail App Password)
- The server serves the React frontend from `public/` on all non-API routes
