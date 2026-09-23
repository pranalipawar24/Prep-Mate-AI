# 🚀 PrepMate AI

**PrepMate AI** is a GenAI-powered job preparation platform that helps candidates analyze their resumes against job descriptions, identify skill gaps, generate personalized interview preparation plans, and create ATS-friendly resumes.

The platform uses **Google Gemini** to analyze the candidate's resume, self-description, and target job description and generate a structured interview preparation report.

---

## ✨ Features

- 🔐 Secure user registration and login
- 🔑 JWT-based authentication using HTTP cookies
- 🚪 Logout with token blacklisting
- 📄 Resume upload and PDF text extraction
- 🤖 AI-powered resume and job-description analysis
- 🎯 Resume-to-job skill gap detection
- 📊 Resume/job match score
- 💻 AI-generated technical interview questions
- 🧠 AI-generated behavioral interview questions
- 📚 Personalized day-wise interview preparation plan
- 📑 AI-generated ATS-friendly resume
- 📄 Resume PDF generation using Puppeteer
- 👤 User-specific interview reports
- 📂 Interview report history

---

## 🏗️ System Architecture

```text
                         ┌─────────────────────┐
                         │      User           │
                         │     Browser         │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ React + Vite        │
                         │ Frontend            │
                         └──────────┬──────────┘
                                    │
                              REST API
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ Node.js + Express   │
                         │ Backend             │
                         └──────┬──────┬───────┘
                                │      │
                    ┌───────────┘      └────────────┐
                    ▼                               ▼
             ┌─────────────┐                ┌─────────────┐
             │   MongoDB   │                │ Google      │
             │   Database  │                │ Gemini API  │
             └─────────────┘                └─────────────┘
                                                    │
                                                    ▼
                                             AI-generated
                                               Report
                                                    │
                                                    ▼
                                             ┌─────────────┐
                                             │ Puppeteer   │
                                             │ PDF Engine  │
                                             └─────────────┘
```

---

## 🧠 How It Works

### 1. User Authentication

A user can register or log in using their email and password.

Passwords are hashed using **bcryptjs**, and authenticated sessions use JWT tokens stored in cookies.

### 2. Resume Upload

The user uploads a resume in PDF format.

The backend:

- Receives the uploaded PDF
- Processes it using `pdf-parse`
- Extracts the resume text
- Keeps the uploaded file in memory during processing

The current upload limit is **3 MB**.

### 3. Job Description & Self Description

The user provides:

- Resume
- Job description
- Self description

These inputs are sent to the backend for AI analysis.

### 4. Gemini AI Analysis

The backend sends the candidate information to **Google Gemini**.

The AI generates a structured interview report containing:

- Match score
- Technical questions
- Behavioral questions
- Skill gaps
- Skill-gap severity
- Preparation plan
- Job title

The response is structured using **Zod schemas** and converted to a JSON schema for the Gemini response.

### 5. Interview Report

The generated report is stored in MongoDB and associated with the authenticated user.

Users can view:

- Individual interview reports
- Previous interview reports
- Detailed preparation information

### 6. ATS-Friendly Resume Generation

The application can generate a tailored resume based on:

- Existing resume content
- Job description
- Self description

Gemini generates structured HTML for the resume.

**Puppeteer** then converts the generated HTML into an A4 PDF.

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| Frontend | React.js |
| Build Tool | Vite |
| Backend | Node.js |
| API Framework | Express.js |
| Database | MongoDB |
| ODM | Mongoose |
| AI | Google Gemini API |
| Authentication | JWT |
| Password Hashing | bcryptjs |
| File Upload | Multer |
| PDF Parsing | pdf-parse |
| PDF Generation | Puppeteer |
| Validation | Zod |
| HTTP Client | Axios |
| Styling | SCSS |
| Version Control | Git & GitHub |

---

## 📁 Project Structure

```text
PrepMate_AI/
│
├── Backend/
│   ├── src/
│   │   ├── config/
│   │   │   └── database.js
│   │   │
│   │   ├── controllers/
│   │   │   ├── auth.controller.js
│   │   │   └── interview.controller.js
│   │   │
│   │   ├── middlewares/
│   │   │   ├── auth.middleware.js
│   │   │   └── file.middleware.js
│   │   │
│   │   ├── models/
│   │   │   ├── blacklist.model.js
│   │   │   ├── interviewReport.model.js
│   │   │   └── user.model.js
│   │   │
│   │   ├── routes/
│   │   │   ├── auth.routes.js
│   │   │   └── interview.routes.js
│   │   │
│   │   ├── services/
│   │   │   └── ai.service.js
│   │   │
│   │   └── app.js
│   │
│   ├── server.js
│   ├── package.json
│   └── .gitignore
│
├── Frontend/
│   ├── src/
│   │   ├── features/
│   │   │   ├── auth/
│   │   │   └── interview/
│   │   │
│   │   ├── app.routes.jsx
│   │   ├── App.jsx
│   │   └── main.jsx
│   │
│   ├── public/
│   ├── package.json
│   ├── vite.config.js
│   └── .gitignore
│
├── Screenshots/
│
├── Testing/
│   ├── PrepMate_Test_Plan.pdf
│   └── Test_Cases.xlsx
│
└── README.md
```

---

## ⚙️ Prerequisites

Before running the project, make sure you have:

- Node.js
- npm
- MongoDB
- Google Gemini API key
- Git

---

# 🚀 Getting Started

## 1. Clone the Repository

```bash
git clone https://github.com/pranalipawar24/Prep-Mate-AI.git
cd Prep-Mate-AI
```

---

## 2. Backend Setup

Navigate to the backend:

```bash
cd Backend
```

Install dependencies:

```bash
npm install
```

---

## 3. Configure Environment Variables

Create a `.env` file inside the `Backend` directory:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GOOGLE_GENAI_API_KEY=your_gemini_api_key
```

### Important

Never commit your `.env` file or API keys to GitHub.

The backend `.gitignore` is configured to ignore `.env` and `node_modules`.

---

## 4. Start the Backend

Run:

```bash
npm run dev
```

The backend runs on:

```text
http://localhost:3000
```

---

## 5. Frontend Setup

Open another terminal and navigate to:

```bash
cd Frontend
```

Install dependencies:

```bash
npm install
```

Start the Vite development server:

```bash
npm run dev
```

The frontend runs on the Vite development URL, normally:

```text
http://localhost:5173
```

---

# 🔌 API Endpoints

## Authentication

### Register

```http
POST /api/auth/register
```

Creates a new user account.

### Login

```http
POST /api/auth/login
```

Authenticates a user and creates a JWT-based session.

### Logout

```http
GET /api/auth/logout
```

Logs out the current user and blacklists the authentication token.

### Get Current User

```http
GET /api/auth/get-me
```

Returns the currently authenticated user's details.

---

## Interview APIs

### Generate Interview Report

```http
POST /api/interview/
```

Requires authentication.

Accepts:

- Resume PDF
- Job description
- Self description

Generates and stores an AI-powered interview report.

---

### Get Interview Report

```http
GET /api/interview/report/:interviewId
```

Returns a specific interview report belonging to the authenticated user.

---

### Get All Interview Reports

```http
GET /api/interview/
```

Returns the authenticated user's interview report history.

---

### Generate Resume PDF

```http
POST /api/interview/resume/pdf/:interviewReportId
```

Generates an ATS-friendly resume PDF using the selected interview report.

---

# 🔐 Security

PrepMate AI implements several security mechanisms:

- Password hashing using `bcryptjs`
- JWT-based authentication
- Authentication through cookies
- Protected API routes
- Token blacklisting during logout
- User-specific interview reports
- Environment variables for sensitive configuration
- File upload size restriction
- Request authentication middleware

---

# 🧪 Testing

The project includes a dedicated testing directory containing:

```text
Testing/
├── PrepMate_Test_Plan.pdf
└── Test_Cases.xlsx
```

Testing covers important application functionality such as:

- Authentication
- Resume upload
- Interview report generation
- API behavior
- Report retrieval
- Resume PDF generation
- Invalid input handling

---

# 📸 Application Screenshots

Screenshots demonstrating the application are available in:

```text
Screenshots/
```

Current screenshots include:

- Registration page
- AI analysis results
- Interview preparation page
- Generated resume

---

# 🌐 Deployment

The application is being prepared for production deployment.

Planned deployment architecture:

```text
GitHub
   │
   ├───────────────┐
   ▼               ▼
Frontend         Backend
Vercel           Node.js Hosting
   │               │
   └───────┬───────┘
           ▼
       MongoDB
           +
      Google Gemini
```

The production frontend and backend URLs will be added here after deployment.

---

# 🔮 Future Improvements

- 📱 Improved mobile responsiveness
- 🎙️ Voice-based interview practice
- 📊 Advanced candidate analytics
- 🌍 Multi-language interview preparation
- 🤝 AI-powered mentor feedback
- 🧪 Automated API and end-to-end testing
- ⚡ Performance optimization
- ☁️ Production-grade file storage

---

# 👩‍💻 Author

**Pranali Pawar**

Computer Engineering Student

GitHub:  
https://github.com/pranalipawar24

---

## 📄 License

This project is licensed under the MIT License.
