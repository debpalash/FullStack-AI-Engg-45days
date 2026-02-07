## Week 1: Foundations and Payroll Core

---

### Day 1: Dev Environment and React Basics

#### 📚 Learning Goals
- Set up development environment (Linux/WSL, Git, Node.js, VS Code)
- Understand React fundamentals: JSX, components, props
- Learn basic terminal commands
- Install and configure Cursor/GitHub Copilot

#### ✅ Tasks & Checklist
- [ ] Install WSL2/Linux or set up Linux environment
- [ ] Install Node.js (v18+), npm/yarn
- [ ] Install VS Code + extensions (ESLint, Prettier, Tailwind)
- [ ] Set up Git and GitHub account
- [ ] Install Cursor AI or GitHub Copilot
- [ ] Create first React app with Vite
- [ ] Build 3 simple components (Header, Card, Button)
- [ ] Learn useState hook with a counter example

#### 🛠️ Project Work
**Project 1 Start: Payroll and HR Software**

**Setup:**
```bash
npm create vite@latest payroll-app -- --template react
cd payroll-app
npm install
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

**Features to Build Today:**
- [ ] Basic React app structure
- [ ] Navigation sidebar for HR/Employee views
- [ ] Employee list table placeholder
- [ ] Simple login form UI

#### 📝 Notes & Learnings - Day 1

**General Learnings Today:**
- 
- 

**Challenges Faced:**
- 
- 

**AI Prompts That Worked Well:**
- 
- 

**Questions to Research:**
- 
- 

#### 🔗 Resources
- React Docs: https://react.dev
- Tailwind CSS: https://tailwindcss.com
- Vite Guide: https://vitejs.dev

#### 🎯 End of Day Goal
Working React app with a form that captures user input and displays it

---

### Day 2: Advanced React and Core UI Layout

#### 📚 Learning Goals
- React hooks: useState, useEffect
- Component composition and props drilling
- Tailwind CSS styling
- Deploy to Vercel
- Environment variables

#### ✅ Tasks & Checklist
- [ ] Learn useEffect for side effects
- [ ] Implement conditional rendering
- [ ] Style components with Tailwind CSS
- [ ] Create reusable component library (Button, Input, Card)
- [ ] Set up Anthropic API account and get API key
- [ ] Integrate Claude API for text generation
- [ ] Deploy to Vercel
- [ ] Set up environment variables in Vercel

#### 🛠️ Project Work
**Project 1 Continue: Employee Management UI**

**Features to Build Today:**
- [ ] Implement `useState` for employee record management
- [ ] Create a modal for "Add Employee"
- [ ] Build a reusable `Table` component for HR listings
- [ ] Add basic client-side validation for employee info
- [ ] Responsive dashboard layout for desktop/mobile
- [ ] Theme switching (Light/Dark mode) for premium feel

**API Integration:**
```javascript
// Example structure - build with AI help
const generateLandingPage = async (productDescription) => {
  // Call Claude API
  // Parse response
  // Update state
}
```

#### 📝 Notes & Learnings

**Key Concepts:**
- 
- 

**API Integration Notes:**
- 
- 

**Deployment Issues:**
- 
- 

**Code Snippets to Remember:**
```javascript
// Paste useful code here
```

#### 🔗 Resources
- Anthropic API Docs: https://docs.anthropic.com
- Vercel Deployment: https://vercel.com/docs

#### 🎯 End of Day Goal
Deployed landing page generator that uses AI to create marketing copy

---

### Day 3: Python and FastAPI Basics

#### 📚 Learning Goals
- Python virtual environments
- FastAPI framework basics
- REST API concepts (GET, POST, PUT, DELETE)
- Request/response models with Pydantic
- CORS configuration
- API testing with curl/Postman

#### ✅ Tasks & Checklist
- [ ] Install Python 3.11+
- [ ] Learn virtual environment (venv)
- [ ] Install FastAPI and Uvicorn
- [ ] Create first API endpoint
- [ ] Understand route decorators
- [ ] Learn Pydantic models for validation
- [ ] Set up CORS for React frontend
- [ ] Test API with Postman/curl

#### 🛠️ Project Work
**Project 1 Continue: Backend foundations with FastAPI**

**Setup:**
```bash
mkdir waitlist-api
cd waitlist-api
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install fastapi uvicorn python-dotenv
```

**Features to Build Today:**
- [ ] Create FastAPI project structure
- [ ] Build POST /api/employees endpoint
- [ ] Build GET /api/employees endpoint
- [ ] Add basic field validation (Email, Department)
- [ ] In-memory storage for rapid prototyping

**API Endpoints:**
```python
# Structure with AI assistance
# POST /api/waitlist
# GET /api/waitlist
```

#### 📝 Notes & Learnings

**Key Concepts:**
- 
- 

**Python/FastAPI Gotchas:**
- 
- 

**API Design Decisions:**
- 
- 

#### 🔗 Resources
- FastAPI Docs: https://fastapi.tiangolo.com
- Python Docs: https://docs.python.org

#### 🎯 End of Day Goal
Working REST API that can accept and return waitlist signups

**Test Command:**
```bash
# Add your test curl commands here
```

---

### Day 4: PostgreSQL and Database Integration

#### 📚 Learning Goals
- PostgreSQL basics
- SQL queries (SELECT, INSERT, UPDATE, DELETE)
- Database design and schemas
- SQLAlchemy ORM
- Database migrations with Alembic
- Supabase setup

#### ✅ Tasks & Checklist
- [ ] Create Supabase account (free tier)
- [ ] Set up PostgreSQL database
- [ ] Learn basic SQL queries
- [ ] Install SQLAlchemy and psycopg2
- [ ] Create database models
- [ ] Set up Alembic for migrations
- [ ] Connect FastAPI to PostgreSQL
- [ ] Write CRUD operations

#### 🛠️ Project Work
**Project 2 Continue: Employee Database Schema**

**Database Schema:**
```sql
CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    first_name VARCHAR(100) NOT NULL,
    last_name VARCHAR(100) NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    department VARCHAR(100),
    role VARCHAR(100),
    salary_basis DECIMAL(12, 2),
    joining_date DATE DEFAULT CURRENT_DATE,
    status VARCHAR(50) DEFAULT 'active'
);
```

**Features to Build Today:**
- [ ] Create employees table in Supabase
- [ ] Set up SQLAlchemy models
- [ ] Migrate from in-memory to database storage
- [ ] Add GET /api/employees/:id endpoint
- [ ] Add UPDATE/DELETE for employee records
- [ ] Add duplicate email handling
- [ ] Test all CRUD operations for HR data

**SQLAlchemy Model:**
```python
# Build with AI assistance
class Waitlist(Base):
    # Define model
    pass
```

#### 📝 Notes & Learnings

**Database Design:**
- 
- 

**SQL Queries I Learned:**
```sql
-- Paste useful queries
```

**SQLAlchemy Tips:**
- 
- 

**Connection Issues & Solutions:**
- 
- 

#### 🔗 Resources
- Supabase: https://supabase.com
- SQLAlchemy: https://www.sqlalchemy.org
- PostgreSQL Tutorial: https://www.postgresqltutorial.com

#### 🎯 End of Day Goal
API fully connected to PostgreSQL database with all CRUD operations working

---

### Day 5: Authentication and Role Management

#### 📚 Learning Goals
- Authentication vs Authorization
- JWT tokens (JSON Web Tokens)
- Password hashing with bcrypt
- OAuth 2.0 basics
- Session management
- Secure password storage

#### ✅ Tasks & Checklist
- [ ] Understand JWT structure and flow
- [ ] Install passlib, python-jose, bcrypt
- [ ] Create User model in database
- [ ] Build signup endpoint
- [ ] Build login endpoint (returns JWT)
- [ ] Implement password hashing
- [ ] Create middleware for protected routes
- [ ] Test authentication flow

#### 🛠️ Project Work
**Project 2 Continue: HR Auth System**

**Database Schema:**
```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    email VARCHAR(255) UNIQUE NOT NULL,
    hashed_password TEXT NOT NULL,
    full_name VARCHAR(255),
    created_at TIMESTAMP DEFAULT NOW()
);
```

**Features to Build Today:**
- [ ] Registration (restricted to HR/Admin)
- [ ] User login returns JWT
- [ ] Password hashing with bcrypt
- [ ] Protected route decorator
- [ ] Get current user profile
- [ ] Role-based access control basics (Admin vs Employee)
- [ ] Token validation middleware

**API Endpoints:**
```python
# POST /api/auth/signup
# POST /api/auth/login
# GET /api/auth/me (protected)
```

#### 📝 Notes & Learnings

**Authentication Flow:**


**Security Best Practices:**
- 
- 

**JWT Structure:**
- 
- 

**Debugging Notes:**
- 
- 

#### 🔗 Resources
- JWT.io: https://jwt.io
- OWASP Auth Guide: https://cheatsheetseries.owasp.org

#### 🎯 End of Day Goal
Working authentication system where users can sign up, log in, and access protected routes

---

### Day 6: Employee Dashboard and Onboarding

#### 📚 Learning Goals
- React Context API for auth state
- Protected routes in React
- LocalStorage for token management
- Axios/Fetch for API calls
- Form handling and validation
- React Router for navigation

#### ✅ Tasks & Checklist
- [ ] Install React Router
- [ ] Set up AuthContext
- [ ] Create login/signup forms
- [ ] Implement token storage
- [ ] Create protected route wrapper
- [ ] Build task creation form
- [ ] Display tasks list
- [ ] Add logout functionality

#### 🛠️ Project Work
**Project 2 Continue: Employee Dashboard Frontend**

**Features to Build Today:**
- [ ] HR/Admin Login Page
- [ ] Protected Admin Dashboard Layout
- [ ] Employee List and Search
- [ ] Employee Onboarding Form
- [ ] Protected Routes in React
- [ ] Auth State Management using Context API
- [ ] Auto-redirect based on login status

**Components to Create:**
```
/src
  /components
    - LoginForm.jsx
    - SignupForm.jsx
    - TaskList.jsx
    - TaskItem.jsx
    - CreateTaskForm.jsx
  /context
    - AuthContext.jsx
  /pages
    - Login.jsx
    - Dashboard.jsx
```

#### 📝 Notes & Learnings

**React Router Setup:**
- 
- 

**State Management Strategy:**
- 
- 

**API Integration Patterns:**
```javascript
// Paste useful patterns
```

**Form Validation:**
- 
- 

#### 🔗 Resources
- React Router: https://reactrouter.com
- React Context: https://react.dev/reference/react/useContext

#### 🎯 End of Day Goal
Working frontend with login/signup that connects to backend API

---

### Day 7: AI Onboarding and First Deploy

#### 📚 Learning Goals
- Claude API integration in backend
- Background job processing basics
- Prompt engineering for task management
- Full stack deployment (frontend + backend)
- Environment variables in production

#### ✅ Tasks & Checklist
- [ ] Create tasks table in database
- [ ] Build task CRUD endpoints
- [ ] Integrate Claude API for task categorization
- [ ] Add AI priority suggestions
- [ ] Implement task filtering
- [ ] Add task completion toggle
- [ ] Deploy backend to Railway/Render
- [ ] Deploy frontend to Vercel
- [ ] Connect frontend to production API

#### 🛠️ Project Work
**Project 1 Continue: AI-Powered Payroll & HR Dashboard**

**Progress Tracker:**
- [ ] Employee CRUD with Postgres
- [ ] Role-based Access Control (RBAC)
- [ ] Protected Dashboard for HR
- [ ] Protected Dashboard for Employees
- [ ] Initial Database Schema for Payroll and Documents

#### 🏁 Week 1 Checkpoint:
- [ ] Development environment is fully set up.
- [ ] React frontend and FastAPI backend are communicating.
- [ ] User authentication (JWT) and roles are functional.
- [ ] Project 1 (Payroll) MVP structure is deployed.

#### 🎯 End of Day Goal
A functional MVP of the Payroll & HR Software where HR can manage employees and employees can log in to a personal dashboard.

[Back to index](README.md)
