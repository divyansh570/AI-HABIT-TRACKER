# AI Habit Tracker

An AI-powered habit tracking platform that helps users build consistency, monitor progress, and gain actionable insights from their daily routines.

The application combines traditional habit tracking with AI-generated recommendations, weekly reports, streak analysis, and performance analytics to help users develop sustainable habits.

---

## Features

### Habit Management
- Create, edit, and delete habits
- Categorize habits by type
- Track daily completion status
- Monitor active and completed habits

### Analytics Dashboard
- Daily, weekly, and monthly progress tracking
- Habit completion statistics
- Visual performance charts
- Category-wise habit distribution
- Consistency monitoring

### AI-Powered Insights
- Personalized habit recommendations
- Weekly performance summaries
- Habit improvement suggestions
- Streak recovery guidance
- AI chat assistant for productivity support

### User Experience
- Secure authentication
- Responsive design
- Dark/Light theme support
- Mobile-friendly navigation
- Interactive data visualization

---

# Tech Stack

## Frontend

- React
- Vite
- React Router
- Axios
- Tailwind CSS
- Recharts
- Context API

## Backend

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT Authentication
- bcrypt

## AI Integration

- LLM-powered habit analysis
- Weekly report generation
- Personalized recommendations

---

# Project Structure

```text
AIHABITTRACKER
│
├── backend
│   │
│   ├── config
│   │   └── db.js
│   │
│   ├── controllers
│   │   ├── aiController.js
│   │   ├── authController.js
│   │   ├── habitController.js
│   │   └── logController.js
│   │
│   ├── middleware
│   │   ├── auth.js
│   │   └── errorHandler.js
│   │
│   ├── models
│   │   ├── AIInsight.js
│   │   ├── Habit.js
│   │   ├── HabitLog.js
│   │   └── User.js
│   │
│   ├── routes
│   │   ├── ai.js
│   │   ├── auth.js
│   │   ├── habits.js
│   │   └── logs.js
│   │
│   ├── config
│   ├── package.json
│   └── server.js
│
├── frontend
│   │
│   ├── public
│   │
│   ├── src
│   │   │
│   │   ├── api
│   │   │   └── axios.js
│   │   │
│   │   ├── assets
│   │   │   ├── hero.png
│   │   │   ├── react.svg
│   │   │   └── vite.svg
│   │   │
│   │   ├── components
│   │   │   ├── AIChat.jsx
│   │   │   ├── AIWeeklyReport.jsx
│   │   │   ├── HabitForm.jsx
│   │   │   ├── HabitStatsCard.jsx
│   │   │   ├── HeatmapChart.jsx
│   │   │   ├── ProgressRing.jsx
│   │   │   ├── Sidebar.jsx
│   │   │   ├── TodayHabitCard.jsx
│   │   │   ├── WeeklyGrid.jsx
│   │   │   └── ...
│   │   │
│   │   ├── context
│   │   │   ├── AuthContext.jsx
│   │   │   └── ThemeContext.jsx
│   │   │
│   │   ├── pages
│   │   │   ├── Landing.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Habits.jsx
│   │   │   ├── Weekly.jsx
│   │   │   ├── Stats.jsx
│   │   │   ├── Insights.jsx
│   │   │   ├── Login.jsx
│   │   │   └── Register.jsx
│   │   │
│   │   ├── utils
│   │   │   ├── confetti.js
│   │   │   ├── constants.js
│   │   │   └── dateHelpers.js
│   │   │
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   │
│   ├── package.json
│   └── vite.config.js
│
└── README.md
```

---

# Architecture Overview

The application follows a standard MERN architecture.

```text
React Frontend
      │
      ▼
Axios Requests
      │
      ▼
Express API
      │
      ▼
Controllers
      │
      ▼
MongoDB Database
      │
      ▼
AI Processing Layer
```

---

# Frontend Structure

## api/

Contains API configuration and reusable Axios instances used to communicate with the backend.

### Example

```javascript
axios.get("/api/habits");
```

---

## components/

Reusable UI building blocks.

### Core Components

| Component | Purpose |
|------------|----------|
| AIChat | AI conversation interface |
| AIWeeklyReport | AI-generated weekly summaries |
| HabitForm | Habit creation and editing |
| HabitStatsCard | Habit metrics display |
| HeatmapChart | Activity heatmap visualization |
| ProgressRing | Circular progress indicator |
| Sidebar | Application navigation |
| TodayHabitCard | Daily habit tracking |
| WeeklyGrid | Weekly completion overview |

---

## pages/

Route-level components representing complete screens.

### Available Pages

| Page | Description |
|--------|-------------|
| Landing | Marketing homepage |
| Dashboard | Main user dashboard |
| Habits | Habit management |
| Weekly | Weekly tracking view |
| Stats | Analytics and reports |
| Insights | AI-generated insights |
| Login | User authentication |
| Register | Account creation |

---

## context/

Global state management using React Context API.

### AuthContext
Manages:

- Authentication state
- User session
- JWT handling

### ThemeContext
Manages:

- Dark mode
- Light mode
- Theme persistence

---

## utils/

Contains helper functions used across the application.

Examples:

- Date calculations
- Animation utilities
- Global constants
- Chart transformations

---

# Backend Structure

## routes/

Defines API endpoints.

### Authentication

```http
POST /api/auth/register
POST /api/auth/login
```

### Habits

```http
GET    /api/habits
POST   /api/habits
PUT    /api/habits/:id
DELETE /api/habits/:id
```

### Logs

```http
GET  /api/logs
POST /api/logs
```

### AI

```http
POST /api/ai/chat
POST /api/ai/weekly-report
POST /api/ai/insights
```

---

## controllers/

Contains business logic.

### authController

Responsible for:

- Registration
- Login
- Token generation

### habitController

Responsible for:

- Habit CRUD operations
- Habit management workflows

### logController

Responsible for:

- Habit completion logging
- Progress tracking

### aiController

Responsible for:

- AI requests
- Weekly reports
- Personalized insights

---

## models/

MongoDB schema definitions.

### User

Stores:

- User profile
- Credentials
- Preferences

### Habit

Stores:

- Habit details
- Categories
- Goals

### HabitLog

Stores:

- Daily completion records
- Progress history

### AIInsight

Stores:

- Generated reports
- Recommendations
- AI analysis history

---

## middleware/

### auth.js

Protects private routes using JWT authentication.

### errorHandler.js

Centralized error handling middleware.

---

# Environment Variables

## Backend

Create:

```bash
backend/.env
```

Example:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GEMINI_API_KEY=your_api_key
```

---

## Frontend

Create:

```bash
frontend/.env
```

Example:

```env
VITE_API_URL=http://localhost:5000
```

---

# Installation

## Clone Repository

```bash
git clone <repository-url>
cd AIHABITTRACKER
```

---

## Backend Setup

```bash
cd backend
npm install
npm run dev
```

Server starts on:

```text
http://localhost:5000
```

---

## Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

Frontend starts on:

```text
http://localhost:5173
```

---

# Security Notes

- Never commit `.env` files.
- Rotate any exposed API keys immediately.
- Add `.env` to `.gitignore`.
- Use `.env.example` for public repositories.

---

# Author

**Divyansh Raj**
