# OctoFit Tracker - Multi-tier Application

A modern multi-tier application for fitness tracking with user authentication, activity logging, team management, leaderboards, and personalized workout suggestions.

## Architecture

```
octofit-tracker/
├── backend/          (Logic tier - Node.js + Express + TypeScript)
│   ├── src/
│   │   ├── index.ts          (Main server entry point)
│   │   ├── models/           (Mongoose models)
│   │   ├── controllers/      (Request handlers)
│   │   └── routes/           (API routes)
│   ├── tsconfig.json         (TypeScript configuration)
│   ├── package.json          (Backend dependencies)
│   └── .env.example          (Environment variables template)
│
└── frontend/         (Presentation tier - React 19 + Vite)
    ├── src/
    ├── vite.config.js        (Vite configuration)
    ├── package.json          (Frontend dependencies)
    └── index.html
```

## Tech Stack

### Frontend (Presentation Tier)
- **React 19** with **Vite** - Modern UI development
- **react-router-dom** - Client-side routing
- **Bootstrap** - Responsive UI styling
- Port: **5173**

### Backend (Logic Tier)
- **Node.js (LTS)** - JavaScript runtime
- **Express** - Web framework
- **TypeScript** - Type-safe JavaScript
- **Mongoose** - MongoDB data access layer
- Port: **8000**

### Database (Data Tier)
- **MongoDB** - NoSQL database
- **mongosh** - MongoDB client tool
- Port: **27017**

## Prerequisites

- Node.js LTS (v18+)
- MongoDB (`mongodb-org` package)
- npm or yarn

## Installation

### 1. Backend Setup

```bash
cd octofit-tracker/backend

# Install dependencies
npm install

# Create .env file from template
cp .env.example .env

# Start development server
npm run dev
```

The backend will be available at `http://localhost:8000`

### 2. Frontend Setup

```bash
cd octofit-tracker/frontend

# Dependencies are already installed
# Start development server
npm run dev
```

The frontend will be available at `http://localhost:5173`

## Available Commands

### Backend
- `npm run dev` - Start development server with hot reload
- `npm run build` - Build TypeScript to JavaScript
- `npm start` - Run compiled backend

### Frontend
- `npm run dev` - Start Vite development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint

## Environment Variables

### Backend (.env)
```
PORT=8000
MONGODB_URI=mongodb://localhost:27017/octofit-tracker
```

## API Endpoints

The frontend proxy automatically forwards API calls from `/api/*` to `http://localhost:8000`

### Health Check
- `GET /health` - Server health status
- `GET /` - API info

## MongoDB Connection

The backend automatically connects to MongoDB on startup. Ensure MongoDB is running:

```bash
# Check if MongoDB is running
ps aux | grep mongod

# Start MongoDB (if not running)
# On Windows: services or MongoDB.exe
# On macOS: brew services start mongodb-community
# On Linux: sudo systemctl start mongod
```

## Project Features (Planned)

- ✓ User authentication system
- ✓ User profile management
- ✓ Activity logging and tracking
- ✓ Team creation and management
- ✓ Competitive leaderboard
- ✓ Personalized workout suggestions

## Development Workflow

1. Frontend and backend run on different ports
2. Frontend development server includes proxy for API calls
3. Backend uses TypeScript with ts-node for development
4. Hot reload enabled on both frontend and backend

## Ports Summary

| Service    | Port  | Access       |
|-----------|-------|--------------|
| Frontend   | 5173  | Public       |
| Backend    | 8000  | Public       |
| MongoDB    | 27017 | Private      |

## Next Steps

1. Implement user authentication routes
2. Create API endpoints for activities, teams, and leaderboards
3. Build UI components for user dashboard
4. Add workout suggestion engine
5. Implement real-time leaderboard updates

---

**Created:** June 5, 2026  
**Branch:** build-octofit-app
