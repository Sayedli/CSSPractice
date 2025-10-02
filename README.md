# CSSPractice

A collection of small front-end exercises and a simple full‑stack CRUD tutorial used for practicing HTML/CSS and basic web app concepts.

**Contents**
- `Exercise1/` – Static HTML + CSS layout practice
- `Exercise2/` – Static HTML with images and styles
- `Exercise 3/` – Tutorial 5 CRUD app (frontend + Node/Express backend with MySQL)
- `pageOne.html`, `pageTwo.html`, `styleSheet.css` – Standalone assignment pages styled with CSS

## Quick Start

- Static pages: open any `.html` file directly in a browser (e.g., `Exercise1/exercise1.html`, `Exercise2/exercise2.html`, `pageOne.html`, `pageTwo.html`).
- Exercise 3 frontend: serve with a simple static server.
  - From `Exercise 3/`, run: `npm install` then `npm run start` to launch `http-server` on `http://localhost:8000`.
- Exercise 3 backend: run the Express API after configuring MySQL (see below).
  - From `Exercise 3/backend/`, run: `npm install` then `node index.js` (or `npx nodemon index.js`) to start on port `2000`.

## Exercise 3: Backend + DB Setup

- Prerequisites
  - Node.js 18+ and npm
  - MySQL server running locally (default port `3306`)

- Database
  - Create a database named `tut5-db` and import the schema/data from `Exercise 3/tut5-db.sql`.
  - Ensure a MySQL user exists matching the credentials in `Exercise 3/backend/config.js`:
    - host: `localhost`, port: `3306`
    - user: `testuser`
    - password: `mypassword`
    - database: `tut5-db`
  - Update `Exercise 3/backend/config.js` if your local credentials differ.

- Start services
  - Backend API: `cd "Exercise 3/backend" && npm install && node index.js`
  - Frontend static pages: `cd "Exercise 3" && npm install && npm run start`

- API Endpoints (port `2000`)
  - `GET /` – list all rows in `population`
  - `GET /:city` – get one row by `CITY`
  - `POST /:city` – insert a new row using JSON body
  - `PUT /:city` – update an existing row using JSON body
  - `DELETE /:city` – delete by `CITY`

## Repo Structure

- `Exercise1/`
  - `exercise1.html`, `exercise1.css`
- `Exercise2/`
  - `exercise2.html`, `styles.css`, `images/`
- `Exercise 3/`
  - `frontend/` – CRUD views (`create.html`, `read.html`, `update.html`, `delete.html`, `view.html`)
  - `backend/` – Express API (`index.js`, CRUD handlers, `config.js`)
  - `package.json` – scripts (uses `http-server` for frontend)
  - `tut5-db.sql` – MySQL schema + seed data
- Root assignment pages
  - `pageOne.html`, `pageTwo.html`, `styleSheet.css`

## Notes

- The backend enables CORS, so the frontend on port `8000` can call the API on port `2000` during local development.
- If ports are occupied, adjust `Exercise 3/backend/index.js` (port `2000`) or the frontend `npm start` port (`8000`) as needed.

## Author

- Hassan Ali
