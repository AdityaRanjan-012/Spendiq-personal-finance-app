
Built SpendiQ, a full-stack personal finance web app to track expenses, categorize transactions, and visualize spending trends via an interactive dashboard.

Implemented backend REST APIs (Node.js + Express) with JWT authentication and MongoDB persistence to securely store multi-user transaction data.

Integrated receipt upload + OCR pipeline to automatically extract transaction details from images/PDFs, reducing manual entry time.

Created frontend dashboard (React) with charts and analytics for quick insights (category breakdowns, monthly trends) and implemented filtering & CSV export features.

Ready-to-use README (Markdown)

Copy the entire block below into README.md in your repo.

# SpendiQ — Personal Finance App

## Overview
SpendiQ is a full-stack personal finance web application that helps users track expenses, categorize transactions, upload receipts (OCR), and view spending analytics through an interactive dashboard.

## Key Features
- User signup / login with JWT-based authentication.
- Add, edit, delete transactions (amount, category, date, notes).
- Categorization of transactions and seeded default categories.
- Upload receipts / PDFs — OCR service extracts transaction details automatically.
- Dashboard with charts and analytics (spending by category, time-series trends).
- File management for uploaded receipts.
- Export transactions (CSV) and basic reporting.

## Tech Stack
- **Frontend:** React (client)  
- **Backend:** Node.js + Express  
- **Database:** MongoDB  
- **Auth:** JWT (token-based)  
- **Extras:** OCR & PDF processing services, analytics routes for chart data

## Repo structure (important paths)
- `backend/` — Node/Express server  
  - `backend/src/routes/` — API routes (`auth.js`, `transactions.js`, `analytics.js`, `categories.js`, `files.js`)  
  - `backend/src/services/` — OCR, PDF and external services (e.g. `ocrService.js`, `pdfService.js`, `geminiService.js`)  
  - `backend/src/utils/jwt.js` — JWT utility  
- `frontend/` — React client (static files, Chart components, transaction UI)

## Environment variables
Create a `.env` (example):


PORT=5000
MONGODB_URI=<your-mongo-connection-string>
JWT_SECRET=<secure-jwt-secret>
NODE_ENV=development
UPLOADS_DIR=./uploads

> Note: adjust names to match your backend code. `jwt.js` and other service files reference a JWT secret and DB connection.

## Installation & Running Locally

### 1. Backend
```bash
cd backend
# install dependencies
npm install

# create .env with MONGODB_URI and JWT_SECRET
# start server (example)
npm run dev
# or
node src/index.js

2. Frontend
cd frontend
npm install
npm start
# or build for production
npm run build

3. Typical workflow

Start MongoDB (local or cloud).

Start backend server.

Start frontend dev server and open the UI.

Sign up, add transactions or upload receipts, explore dashboard.

Notes on OCR / File upload

Uploaded receipts/PDFs are processed by the OCR service to extract date, merchant, and amount.

If OCR confidence is low, the UI allows manual correction before saving the transaction.

Contributing

Fork the repo, create feature branches, open PRs.

Run the linter and tests (if present) before submitting PRs.

License

Specify your preferred license (e.g., MIT).

Contact

Your Name — your.email@example.com


---

# Important repo files / evidence I inspected
I scanned the project and found the following key files & folders (I used these to infer features):

- `backend/src/routes/auth.js` — authentication endpoints  
- `backend/src/routes/transactions.js` — CRUD for transactions  
- `backend/src/routes/analytics.js` — endpoints serving chart/analytics data  
- `backend/src/routes/files.js` — upload / file endpoints  
- `backend/src/services/ocrService.js`, `pdfService.js`, `geminiService.js` — OCR and PDF handling / 3rd-party service integration  
- `backend/src/utils/jwt.js` — JWT helper utilities  
- `backend/src/utils/seedCategories.js` — seeded expense categories  
- `frontend/` — React client (many React files detected)  
- `frontend/package.json` and `backend/package.json` — npm projects

(If you want, I can paste specific snippets of these files or make the README reflect exact script names from `package.json`.)

---

# Likely environment variables / config to document in README
Based on the files I saw, include these in your README `.env` documentation:
- `MONGODB_URI` — MongoDB connection string  
- `JWT_SECRET` — secret used for signing auth tokens  
- `PORT` — backend port  
- `UPLOADS_DIR` — directory for storing uploaded receipts  
- Any API keys for external services (OCR/Gemini) if used — e.g. `OCR_API_KEY`, `GEMINI_API_KEY` (check `services/*` files for exact names)

---

# Small polish suggestions for README / GitHub
- Add screenshots or a short GIF of the dashboard + receipt upload to make the repo look professional.
- Add an examples/env file `env.example` listing required variables (but **do not** commit real secrets).
- Add a short demo video link or Steps-to-run quick-start at top.
- Add a LICENSE (MIT recommended if you want permissive).

---
