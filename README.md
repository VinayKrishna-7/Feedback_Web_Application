# OpenFeedback

A lightweight web app to collect anonymous feedback with zero signups or accounts.

Create a topic, share the link, and read responses through a private admin URL.

[Live Demo](https://openfeedback-t9mb.onrender.com)

> **Note:** The demo is hosted on Render's free tier. If the service has been idle, please allow 30–50 seconds for the server to spin up on your first visit.

## How it works

1. **Create a topic** — Enter what you need feedback on (e.g., "Presentation Feedback", "Sprint Retro").
2. **Share the public link** (`/f/:token`) — Anyone with the link can leave feedback. No login, emails, names, or IP addresses are collected.
3. **Use the secret link** (`/manage/:token`) — Keep this link to view responses on a private dashboard, filter by category (positive, improvement, general), search entries, or export everything to CSV.

## Features

- **Truly anonymous:** No cookies, accounts, or IP logging.
- **Two-link model:** A public link for submissions and a separate private link for management.
- **Categorization:** Responders can tag feedback as positive, improvement, or general.
- **Dashboard:** Live feedback feed with basic breakdown stats, keyword search, and CSV export.
- **Dark / Light mode:** Quick theme toggle that respects system preferences.

## Tech stack

- **Client:** React 19, Vite, Tailwind CSS
- **Server:** Node.js, Express
- **Database:** PostgreSQL, Prisma ORM

## Getting started

### Prerequisites

- Node.js (v18+)
- PostgreSQL (or use the built-in embedded runner for local dev)

### 1. Clone & install

```bash
git clone https://github.com/VinayKrishna-7/Feedback_Web_Application.git
cd Feedback_Web_Application
npm install
```

### 2. Environment setup

Create `server/.env`:
```env
PORT=5000
DATABASE_URL="postgresql://USER:PASSWORD@localhost:5432/openfeedback?schema=public"
CLIENT_URL="http://localhost:5173"
```

Create `client/.env`:
```env
VITE_API_URL=http://localhost:5000/api
```

### 3. Database & run

```bash
# Sync database schema
npm run prisma:push

# Start client and server concurrently
npm run dev
```

- Frontend: `http://localhost:5173`
- Backend: `http://localhost:5000`

## Tests

```bash
npm test
```

## License

[MIT](LICENSE)
