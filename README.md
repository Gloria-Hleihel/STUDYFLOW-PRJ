# StudyFlow 📚

A smart student productivity app that helps you organize courses, manage tasks, generate intelligent study schedules, and get personalized AI-powered academic guidance.

![Status](https://img.shields.io/badge/status-active-brightgreen)
![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 📖 Project Description

StudyFlow is a full-stack web application designed to solve the challenges students face when managing multiple courses, assignments, and deadlines. Instead of juggling multiple calendar apps and note-taking tools, StudyFlow provides:

- **Centralized Course Management** - Track all your courses, chapters, and progress in one place
- **Smart Task Organization** - Create, filter, and manage all assignments, quizzes, exams, and projects
- **Intelligent Study Planning** - Generate optimized study schedules based on deadlines and available time
- **AI Study Assistant** - Get personalized academic advice powered by OpenAI's GPT-4o-mini
- **Calendar & Deadline Tracking** - Never miss a deadline with visual calendars and notifications
- **Real-time Search** - Quickly find courses and tasks with live search

### Why StudyFlow?

✅ **One App for Everything** - No more switching between calendar, notes, and to-do apps  
✅ **AI-Powered Guidance** - Get study tips tailored to your actual workload  
✅ **Smart Scheduling** - Study plan respects your daily availability  
✅ **Progress Tracking** - See completion percentage for each course  
✅ **Notification Alerts** - Know what's due this week at a glance  

---

## 🛠 Tech Stack

### Frontend
- **React 19** - UI library
- **Vite** - Fast build tool & dev server
- **React Router v7** - Client-side routing
- **Axios** - HTTP client for API calls
- **CSS (Custom)** - Component styling

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web framework
- **MongoDB Atlas** - Cloud database
- **Mongoose** - MongoDB ODM
- **JWT** - Token-based authentication
- **bcryptjs** - Password hashing
- **OpenAI API** - AI chat completions
- **node-cron** - Scheduled tasks

---

## 📋 Requirements

### System Requirements
- **Node.js** v18.0 or higher ([Download](https://nodejs.org))
- **npm** v9.0 or higher (comes with Node.js)
- **MongoDB Atlas account** (free at [mongodb.com](https://mongodb.com))
- **OpenAI API key** (free tier available at [platform.openai.com](https://platform.openai.com))

### Recommended
- **VS Code** - Code editor
- **Git** - Version control (for cloning the repo)
- **Postman** - API testing (optional)

---

## 🚀 Installation & Setup

### Step 1: Clone or Download the Project

**Option A: Clone with Git**
```bash
git clone <repository-url>
cd StudyFlow
```

**Option B: Download ZIP**
- Download the project folder
- Extract it to your desktop or desired location

### Step 2: Set Up Backend

#### 2.1 Navigate to Backend Folder
```bash
cd backend
```

#### 2.2 Install Dependencies
```bash
npm install
```

#### 2.3 Create `.env` File
Create a new file named `.env` in the `backend/` folder with these variables:

```env
PORT=5000
NODE_ENV=development
MONGODB_URI=your_mongodb_connection_string_here
OPENAI_API_KEY=your_openai_api_key_here
```

**How to get MongoDB URI:**
1. Go to [cloud.mongodb.com](https://cloud.mongodb.com) and sign in
2. Click "Build a Database"
3. Choose free tier
4. Create a cluster
5. Click "Connect" → "Connection string" 
6. Copy the connection string and paste it in `.env`
7. Replace `<password>` with your actual password
8. Replace `myFirstDatabase` with `studyflow`

**How to get OpenAI API Key:**
1. Go to [platform.openai.com/api-keys](https://platform.openai.com/api-keys)
2. Sign in or create account
3. Click "Create new secret key"
4. Copy and paste into `.env`

#### 2.4 Verify Backend Setup
```bash
node server.js
```

You should see:
```
✅ Reminder job started — checking every minute.
Server is running on port 5000
```

If you get a port error, change `PORT=5000` to `PORT=3001` in `.env`

### Step 3: Set Up Frontend

#### 3.1 Open New Terminal Window and Navigate to Frontend
```bash
cd StudyFlow/studyflow-frontend
```

#### 3.2 Install Dependencies
```bash
npm install
```

#### 3.3 (Optional) Update API URL if You Changed Backend Port
If you changed the backend port to 3001, update this file:
- Open `src/api/axios.js`
- Change `baseURL: 'http://localhost:5000/api'` to `'http://localhost:3001/api'`
- Save the file

#### 3.4 Start Development Server
```bash
npm run dev
```

You should see:
```
VITE v5.x.x  ready in xxx ms

➜  Local:   http://localhost:5173/
```

### Step 4: Open in Browser

1. Open your browser
2. Go to `http://localhost:5173`
3. Create a new account or log in
4. Start using StudyFlow!

---

## 📁 Project Structure

```
StudyFlow/
│
├── backend/                          # Node.js/Express server
│   ├── models/                       # Database schemas
│   │   ├── User.js
│   │   ├── Course.js
│   │   ├── Task.js
│   │   ├── StudyPlan.js
│   │   └── ChatHistory.js
│   ├── routes/                       # API endpoints
│   │   ├── auth.js                  # Login & register
│   │   ├── courses.js               # Course CRUD
│   │   ├── tasks.js                 # Task CRUD
│   │   ├── studyPlans.js            # Study plan generation
│   │   ├── ai.js                    # AI chat endpoints
│   │   └── calendar.js              # Calendar queries
│   ├── middleware/
│   │   └── auth.js                  # JWT verification
│   ├── services/
│   │   └── aiService.js             # OpenAI integration
│   ├── utils/
│   │   ├── generateToken.js         # JWT creation
│   │   └── reminderJob.js           # Scheduled reminders
│   ├── server.js                    # Main app file
│   ├── package.json
│   ├── .env                         # Environment variables
│   └── node_modules/                # Dependencies (auto-created)
│
└── studyflow-frontend/              # React app
    ├── src/
    │   ├── pages/                   # Page components
    │   │   ├── dashboard.jsx        # Overview page
    │   │   ├── courses.jsx          # Courses page
    │   │   ├── tasks.jsx            # Tasks page
    │   │   ├── calendar.jsx         # Calendar page
    │   │   ├── studyplan.jsx        # Study plan page
    │   │   ├── settings.jsx         # Settings page
    │   │   ├── login.jsx            # Login page
    │   │   ├── register.jsx         # Register page
    │   │   └── *.css                # Page styles
    │   ├── components/
    │   │   ├── Sidebar.jsx          # Navigation sidebar
    │   │   └── Sidebar.css
    │   ├── api/
    │   │   └── axios.js             # HTTP client
    │   ├── App.jsx                  # Main app & routing
    │   ├── index.css                # Global styles
    │   └── main.jsx
    ├── package.json
    ├── vite.config.js
    └── node_modules/                # Dependencies (auto-created)
```

---

## 🎯 How to Use StudyFlow

### 1. Register & Login
- Click "Sign Up" on the login page
- Enter your email, name, and password
- You're now logged in! (token stored in browser)

### 2. Add Your Courses
- Go to **Courses** page
- Click "+ Add Course"
- Enter course name, instructor, difficulty
- Expand the course and add chapters
- Mark chapters complete as you study them

### 3. Create Tasks & Assignments
- Go to **Tasks** page
- Click "+ Add Task"
- Fill in: title, type, course, deadline, estimated hours
- Filter by type or status
- Mark complete when finished

### 4. Generate Smart Study Plan
- Go to **Study Plan** page
- Set how many hours/day you can study
- Click "✨ Generate Plan"
- See your personalized schedule
- Click on study plan to regenerate anytime

### 5. Check Calendar
- Go to **Calendar** page
- See all your deadlines visualized
- Click a date to see tasks due that day

### 6. Chat with AI
- Click the **💬 bubble** on any page
- Ask study questions
- Get personalized academic advice
- View chat history anytime

### 7. Get Notifications
- Click the **🔔 bell** on dashboard
- See all tasks due in the next 7 days
- Color-coded by task type

### 8. Search
- Use the **🔍 search bar** on dashboard
- Type course name or task title
- Click result to navigate

---

## 🔧 Troubleshooting

### Problem: Port 5000 Already in Use (EADDRINUSE)

**On Mac:**
- System Settings → General → AirDrop & Handoff → Turn off AirPlay Receiver
- OR change `PORT=5000` to `PORT=3001` in `backend/.env`

**On Windows/Linux:**
- Change `PORT=5000` to `PORT=3001` in `backend/.env`
- Update frontend: `src/api/axios.js` → `baseURL: 'http://localhost:3001/api'`

### Problem: npm is not recognized (Windows)
- Close and reopen Command Prompt completely (not PowerShell)
- If still failing, restart computer after Node.js installation

### Problem: "Database connection error"
- Check `.env` file exists in `backend/` folder
- Verify `MONGODB_URI` is set correctly
- Make sure MongoDB Atlas cluster is active
- Restart backend server

### Problem: AI Chat says "Invalid OpenAI API key"
- Go to [platform.openai.com/api-keys](https://platform.openai.com/api-keys)
- Create a new API key
- Update `.env` with new key
- Restart backend

### Problem: Can't log in (Invalid email or password)
- Go to MongoDB Atlas
- Find your user in `users` collection
- Delete the user document
- Re-register in the app

### Problem: Frontend doesn't show changes
- Stop frontend server (Ctrl+C)
- Hard refresh browser (Ctrl+Shift+R)
- Run `npm run dev` again

---

## 📱 Features Walkthrough

### Dashboard
- Quick overview of academic status
- Notification bell showing urgent deadlines
- AI chat assistant
- Live search for courses/tasks
- Weekly event calendar
- Course progress cards

### Courses Page
- Create/Edit/Delete courses
- Manage chapters per course
- Visual progress bar
- Difficulty badges

### Tasks Page
- Create/Edit/Delete tasks
- Filter by type (Exam/Assignment/Quiz/Project)
- Filter by status (Pending/Completed)
- Sort by deadline
- Color-coded task types

### Study Plan Page
- Set daily study hours
- Generate intelligent schedules
- See breakdown by date and course
- Regenerate anytime

### Calendar Page
- Monthly calendar grid
- Color-coded deadlines
- Click date to see tasks

### Settings Page
- View profile information
- Clear chat history
- Logout

---

## 📚 API Endpoints Reference

### Authentication
```
POST /api/auth/register
POST /api/auth/login
```

### Courses
```
GET /api/courses
POST /api/courses
PUT /api/courses/:id
DELETE /api/courses/:id
POST /api/courses/:id/chapters
PATCH /api/courses/:id/chapters/:chapterId
DELETE /api/courses/:id/chapters/:chapterId
```

### Tasks
```
GET /api/tasks
POST /api/tasks
PUT /api/tasks/:id
DELETE /api/tasks/:id
GET /api/tasks/calendar?date=YYYY-MM-DD
```

### Study Plans
```
POST /api/study-plans/generate
GET /api/study-plans/latest
```

### AI
```
POST /api/ai/suggest
GET /api/ai/history
DELETE /api/ai/history
```

---

## 🔐 Security Notes

- Passwords are hashed with bcryptjs (never stored in plain text)
- Authentication uses JWT tokens with 7-day expiry
- Each user can only access their own data
- API keys and database credentials stored in `.env` (never commit to Git)
- HTTPS recommended for production deployment

---

## 📦 Building for Production

### Frontend Build
```bash
cd studyflow-frontend
npm run build
```
Creates optimized `dist/` folder ready for deployment

### Backend Deployment
Host on platforms like:
- Heroku
- Railway
- Render
- AWS EC2
- DigitalOcean

Remember to:
- Set environment variables on hosting platform
- Never commit `.env` file to Git
- Use HTTPS in production

---

## 🐛 Found a Bug?

1. Note the steps to reproduce
2. Check the browser console (F12) for errors
3. Check backend terminal for error messages
4. Try clearing browser cache (Ctrl+Shift+R)
5. Restart both frontend and backend servers

---

## 📞 Support

If you encounter issues:

1. **Check Troubleshooting Section** above
2. **Verify Requirements** are met (Node.js v18+, MongoDB, OpenAI key)
3. **Check Terminal Output** for error messages
4. **Review .env File** for correct credentials

---

## 📄 License

This project is provided for educational purposes.

---

## 👨‍💻 Contributing

Feel free to fork this project and submit improvements!

---

## 🎓 Learning Resources

- [React Documentation](https://react.dev)
- [Express.js Guide](https://expressjs.com)
- [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
- [OpenAI API Docs](https://platform.openai.com/docs)
- [JWT Explanation](https://jwt.io/introduction)

---

## 📝 Version History

**v1.0.0** (Current)
- Dashboard with notifications and AI chat
- Course and task management
- Smart study plan generation
- Calendar view
- Real-time search
- User authentication and settings

---

**Happy Studying! 📚✨**
*Made with ❤️ for students everywhere*
```

