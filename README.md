# Pastebin
# Pastebin-Lite

Pastebin-Lite is a simple web app where users can create a text paste and share it using a link.  
Each paste can expire after a certain time or after a number of views.

---

## Features

- Create a text paste
- Get a shareable URL
- View paste in browser or API
- Optional expiry:
  - Time-based (TTL)
  - View limit
- Paste becomes unavailable after expiry
- Safe text rendering

---

## Tech Used

- Next.js
- Node.js
- Upstash Redis (for data storage)
- Vercel (for deployment)

---

## Persistence Layer

This project uses **Upstash Redis** to store pastes.  
Redis is used because it works well with serverless platforms like Vercel and data is not lost between requests.

---

## How to Run Locally

1. Clone the repository
```bash
git clone https://github.com/your-username/pastebin-lite.git
cd pastebin-lite
Install dependencies

npm install
Create .env.local file

UPSTASH_REDIS_REST_URL=your_upstash_url
UPSTASH_REDIS_REST_TOKEN=your_upstash_token
NEXT_PUBLIC_BASE_URL=http://localhost:3000
Start the app

npm run dev
Open:

http://localhost:3000
API Routes
GET /api/healthz → health check

POST /api/pastes → create a paste

GET /api/pastes/:id → fetch paste (counts as a view)

GET /p/:id → view paste in browser

Notes
In-memory storage is not used

No secrets are committed

Works in serverless environment

Designed to pass automated tests
