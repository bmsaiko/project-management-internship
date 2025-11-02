# Project Management Internship 📊

A comprehensive project management system developed during an internship, designed to streamline project planning, tracking, and team collaboration. This web-based application provides robust tools for managing projects, tasks, teams, and deadlines efficiently.

## 📖 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technologies](#technologies)
- [Installation](#installation)
- [Usage](#usage)
- [API Documentation](#api-documentation)
- [Project Structure](#project-structure)
- [Database Schema](#database-schema)
- [Contributors](#contributors)
- [License](#license)

## 🎯 Overview

Project Management Internship is a full-stack web application developed as part of an internship program. The system facilitates complete project lifecycle management, from initial planning to final delivery, with features for task allocation, progress tracking, team collaboration, and reporting.

## ✨ Features

### 🎨 User Management
- **Role-based Access Control** - Admin, Project Manager, Team Member, Client
- **User Profiles** - Comprehensive user management with avatar support
- **Authentication & Authorization** - Secure login with JWT tokens
- **Profile Management** - Personal information, skills, and preferences

### 📋 Project Management
- **Project Creation** - Detailed project setup with objectives and scope
- **Project Timeline** - Gantt chart visualization and milestone tracking
- **Budget Management** - Cost estimation and expense tracking
- **Resource Allocation** - Team member assignment and workload management
- **Status Tracking** - Real-time project progress monitoring

### ✅ Task Management
- **Task Creation & Assignment** - Detailed task descriptions with assignees
- **Priority System** - Urgent, High, Medium, Low priority levels
- **Deadline Management** - Due date tracking with notifications
- **Progress Updates** - Percentage completion and status updates
- **Dependency Management** - Task relationships and prerequisites

### 👥 Team Collaboration
- **Team Creation** - Flexible team structures and member roles
- **Discussion Forums** - Project-specific communication channels
- **File Sharing** - Document upload and version control
- **Comment System** - Task-specific discussions and feedback
- **Notification Center** - Real-time updates and alerts

### 📊 Reporting & Analytics
- **Project Dashboards** - Overview of key metrics and KPIs
- **Progress Reports** - Detailed project status reports
- **Team Performance** - Individual and team productivity metrics
- **Time Tracking** - Hours logged and time allocation analysis
- **Export Capabilities** - PDF, Excel, and CSV report generation

### 🔔 Notification System
- **Email Notifications** - Automated email alerts for important events
- **In-app Notifications** - Real-time notification center
- **Reminder System** - Deadline reminders and follow-ups
- **Customizable Alerts** - User-configurable notification preferences

## 🛠️ Technologies

### Frontend
- **React 18+** - Modern React with hooks and functional components
- **TypeScript** - Type-safe JavaScript development
- **Tailwind CSS** - Utility-first CSS framework
- **React Router** - Client-side routing
- **Axios** - HTTP client for API calls
- **Chart.js** - Data visualization and charts
- **React Hook Form** - Form handling and validation

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web application framework
- **TypeScript** - Backend type safety
- **JWT** - JSON Web Token authentication
- **bcrypt** - Password hashing
- **CORS** - Cross-origin resource sharing

### Database
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling
- **Database Models** - User, Project, Task, Team, Notification

### Development Tools
- **Git** - Version control
- **npm/yarn** - Package management
- **ESLint** - Code linting
- **Prettier** - Code formatting
- **Nodemon** - Development server auto-restart

## 📥 Installation

### Prerequisites
- Node.js 16+ and npm
- MongoDB 5.0+
- Git

### Installation Steps

1. **Clone the Repository**
```bash
git clone https://github.com/BMSaiko/Project-Management-Internship.git
cd Project-Management-Internship
```
Install Dependencies

bash
# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../frontend
npm install
Environment Configuration

bash
# Backend environment (backend/.env)
MONGODB_URI=mongodb://localhost:27017/project-management
JWT_SECRET=your-jwt-secret-key
PORT=5000
NODE_ENV=development

# Frontend environment (frontend/.env)
REACT_APP_API_URL=http://localhost:5000/api
Database Setup

bash
# Make sure MongoDB is running
mongod

# Or using Docker
docker run -d -p 27017:27017 --name mongodb mongo:latest
Start the Application

bash
# Start backend server (from backend directory)
npm run dev

# Start frontend development server (from frontend directory)
npm start
Access the Application

Frontend: http://localhost:3000

Backend API: http://localhost:5000

🚀 Usage
Getting Started
Registration & Login

Create a new account or use demo credentials

Complete your user profile

Set up notification preferences

Project Creation

Click "New Project" from dashboard

Fill in project details, objectives, and timeline

Set up project team and assign roles

Task Management

Create tasks within projects

Assign tasks to team members

Set priorities and deadlines

Track progress and updates

Team Collaboration

Invite team members to projects

Use discussion boards for communication

Share files and documents

Monitor team progress

User Roles
Administrator
Full system access

User management

System configuration

Global reporting

Project Manager
Create and manage projects

Assign tasks to team members

Monitor project progress

Generate project reports

Team Member
View assigned tasks

Update task progress

Participate in discussions

Submit work deliverables

Client
View project progress

Access project documents

Provide feedback

Receive status updates

📚 API Documentation
Authentication Endpoints
text
POST /api/auth/register     - User registration
POST /api/auth/login        - User login
POST /api/auth/logout       - User logout
GET  /api/auth/me          - Get current user
PUT  /api/auth/profile     - Update user profile
Project Endpoints
text
GET    /api/projects        - List all projects
POST   /api/projects        - Create new project
GET    /api/projects/:id    - Get project details
PUT    /api/projects/:id    - Update project
DELETE /api/projects/:id    - Delete project
GET    /api/projects/:id/tasks - Get project tasks
Task Endpoints
text
GET    /api/tasks           - List all tasks
POST   /api/tasks           - Create new task
GET    /api/tasks/:id       - Get task details
PUT    /api/tasks/:id       - Update task
DELETE /api/tasks/:id       - Delete task
PUT    /api/tasks/:id/status - Update task status
Team Endpoints
text
GET    /api/teams           - List all teams
POST   /api/teams           - Create new team
GET    /api/teams/:id       - Get team details
PUT    /api/teams/:id       - Update team
POST   /api/teams/:id/members - Add team member
📁 Project Structure
text
project-management-internship/
├── backend/
│   ├── src/
│   │   ├── controllers/     # Route controllers
│   │   │   ├── auth.controller.ts
│   │   │   ├── project.controller.ts
│   │   │   ├── task.controller.ts
│   │   │   └── user.controller.ts
│   │   ├── models/          # Database models
│   │   │   ├── User.ts
│   │   │   ├── Project.ts
│   │   │   ├── Task.ts
│   │   │   └── Team.ts
│   │   ├── routes/          # API routes
│   │   │   ├── auth.routes.ts
│   │   │   ├── project.routes.ts
│   │   │   └── task.routes.ts
│   │   ├── middleware/      # Custom middleware
│   │   │   ├── auth.ts
│   │   │   └── validation.ts
│   │   ├── utils/           # Utility functions
│   │   │   ├── database.ts
│   │   │   └── helpers.ts
│   │   └── app.ts          # Express app configuration
│   ├── package.json
│   ├── tsconfig.json
│   └── .env
├── frontend/
│   ├── src/
│   │   ├── components/     # React components
│   │   │   ├── common/     # Reusable components
│   │   │   ├── auth/       # Authentication components
│   │   │   ├── dashboard/  # Dashboard components
│   │   │   ├── projects/   # Project management
│   │   │   └── tasks/      # Task management
│   │   ├── pages/          # Page components
│   │   │   ├── Login.tsx
│   │   │   ├── Dashboard.tsx
│   │   │   ├── Projects.tsx
│   │   │   └── Profile.tsx
│   │   ├── hooks/          # Custom React hooks
│   │   │   ├── useAuth.ts
│   │   │   └── useProjects.ts
│   │   ├── context/        # React context
│   │   │   └── AuthContext.tsx
│   │   ├── services/       # API services
│   │   │   ├── api.ts
│   │   │   ├── authService.ts
│   │   │   └── projectService.ts
│   │   ├── types/          # TypeScript type definitions
│   │   │   ├── user.types.ts
│   │   │   ├── project.types.ts
│   │   │   └── task.types.ts
│   │   ├── utils/          # Utility functions
│   │   │   ├── constants.ts
│   │   │   └── helpers.ts
│   │   └── App.tsx
│   ├── public/
│   ├── package.json
│   ├── tsconfig.json
│   └── tailwind.config.js
├── docs/                   # Documentation
├── .gitignore
└── README.md
🗃️ Database Schema
User Model
typescript
{
  _id: ObjectId,
  username: String,
  email: String,
  password: String,
  role: ['admin', 'project_manager', 'team_member', 'client'],
  profile: {
    firstName: String,
    lastName: String,
    avatar: String,
    bio: String,
    skills: [String]
  },
  isActive: Boolean,
  createdAt: Date,
  updatedAt: Date
}
Project Model
typescript
{
  _id: ObjectId,
  name: String,
  description: String,
  status: ['planning', 'active', 'on_hold', 'completed', 'cancelled'],
  priority: ['low', 'medium', 'high', 'urgent'],
  startDate: Date,
  endDate: Date,
  budget: Number,
  manager: ObjectId, // Reference to User
  team: [ObjectId], // References to User
  clients: [ObjectId], // References to User
  objectives: [String],
  createdAt: Date,
  updatedAt: Date
}
Task Model
typescript
{
  _id: ObjectId,
  title: String,
  description: String,
  project: ObjectId, // Reference to Project
  assignee: ObjectId, // Reference to User
  status: ['todo', 'in_progress', 'review', 'completed'],
  priority: ['low', 'medium', 'high', 'urgent'],
  dueDate: Date,
  estimatedHours: Number,
  actualHours: Number,
  dependencies: [ObjectId], // References to Task
  tags: [String],
  createdAt: Date,
  updatedAt: Date
}
👥 Contributors
Bruno Silva (@BMSaiko) - Full Stack Developer & Project Lead

Internship Team - Additional contributors and team members

Developed during the Software Engineering Internship program, focusing on real-world project management challenges and agile development methodologies.

📄 License
This project is developed for educational and internship purposes. All rights reserved by the contributors and the hosting organization.

🔧 Development
Scripts
Backend
bash
npm run dev          # Start development server with hot reload
npm run build        # Build for production
npm start           # Start production server
npm test            # Run tests
npm run lint        # Run ESLint
Frontend
bash
npm start           # Start development server
npm run build       # Build for production
npm test            # Run tests
npm run lint        # Run ESLint
Code Style
ESLint for code linting

Prettier for code formatting

TypeScript for type safety

Conventional commits for commit messages

Testing
bash
# Backend tests
cd backend && npm test

# Frontend tests
cd frontend && npm test
🚀 Deployment
Production Build
bash
# Build both frontend and backend
cd frontend && npm run build
cd ../backend && npm run build
Environment Variables for Production
bash
# Backend production environment
NODE_ENV=production
MONGODB_URI=your-production-mongodb-uri
JWT_SECRET=your-production-jwt-secret
PORT=5000
CORS_ORIGIN=your-frontend-domain
🤝 Contributing
Fork the repository

Create a feature branch (git checkout -b feature/amazing-feature)

Commit your changes (git commit -m 'Add amazing feature')

Push to the branch (git push origin feature/amazing-feature)

Open a Pull Request

🐛 Bug Reports
If you discover any bugs, please create an issue with:

Detailed description of the bug

Steps to reproduce

Expected behavior

Screenshots (if applicable)

🔮 Future Enhancements
Mobile Application - React Native companion app

Real-time Collaboration - WebSocket integration

Advanced Analytics - Machine learning insights

Integration APIs - Slack, GitHub, Jira integrations

Time Tracking - Automated time tracking features

Document Management - Advanced version control
