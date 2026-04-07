# Simple Login Page

A simple full-stack login page example built with:

- **Frontend:** Next.js, React, Tailwind CSS, Framer Motion, Axios
- **Backend:** Express, MongoDB, Mongoose, JSON Web Tokens, bcrypt

This project includes a login page, registration page, and a backend API for authentication.

## Project Structure

- `backend/` - Express API server
  - `server.js` - app entry point
  - `config/db.js` - MongoDB connection helper
  - `models/User.js` - Mongoose user model
  - `routes/auth.js` - authentication routes: register and login

- `frontend/frontend/` - Next.js app
  - `app/` - application pages and UI components
  - `globals.css` - global styles and animations
  - `package.json` - frontend dependencies and scripts

## Features

- User registration with hashed password storage
- User login with JWT token issuance
- Beautiful animated login/register UI
- Local storage token persistence on login
- CORS enabled backend for local frontend integration

## Requirements

- Node.js (recommended v18+)
- npm
- MongoDB instance or MongoDB Atlas

## Setup

### Backend

1. Open a terminal in `backend/`
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file in `backend/` with:
   ```env
   MONGO_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret
   PORT=5000
   ```
4. Start the backend server:
   ```bash
   npm run dev
   ```

The backend will run on `http://localhost:5000` by default.

### Frontend

1. Open a terminal in `frontend/frontend/`
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the frontend app:
   ```bash
   npm run dev
   ```

The frontend will run on `http://localhost:3000` by default.

> If port `3000` is busy, Next.js will automatically choose another available port.

## API Endpoints

### Register

- URL: `POST /api/auth/register`
- Body:
  ```json
  {
    "name": "Your Name",
    "email": "you@example.com",
    "password": "securepassword"
  }
  ```

### Login

- URL: `POST /api/auth/login`
- Body:
  ```json
  {
    "email": "you@example.com",
    "password": "securepassword"
  }
  ```
- Response includes:
  - `token`
  - `user` object

## Notes

- The frontend stores the JWT token in `localStorage` after successful login.
- The backend uses `bcryptjs` to hash passwords and `jsonwebtoken` to sign tokens.
- The backend expects `MONGO_URI` to be configured in `.env`.

## Build

To create a production build for the frontend:

```bash
cd frontend/frontend
npm run build
```

## License

This is an example project and does not include a license.
