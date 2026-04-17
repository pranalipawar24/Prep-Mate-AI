🚀 PrepMate AI – GenAI Job Preparation Platform
# 🚀 PrepMate AI

PrepMate AI is a **production-ready full stack GenAI web application** designed to help users prepare for jobs intelligently.  

It enables users to upload resumes, analyze job descriptions, identify skill gaps, and generate **AI-powered interview questions and ATS-optimized resumes**.

This project simulates a **real-world job preparation platform** using modern technologies like React, Node.js, JWT authentication, and Gemini AI.

---

## ✨ Key Features

- 🔐 **Secure Authentication**
  - JWT-based authentication
  - Token blacklisting for logout security

- 📄 **Resume Upload & Parsing**
  - Extracts skills and information from resumes

- 🧠 **AI-Powered Analysis (Gemini)**
  - Job description analysis
  - Skill gap detection
  - Smart recommendations

- 🎯 **Interview Preparation**
  - AI-generated interview questions based on skills & job role

- 📊 **Skill Gap Detection**
  - Compares resume vs job description
  - Suggests missing skills

- 📑 **ATS-Optimized Resume Generation**
  - Improves resume for better job matching

- 📄 **Dynamic PDF Generation**
  - Uses Puppeteer for professional resume export

---

## 🏗️ Tech Stack

### Frontend
- React.js

### Backend
- Node.js
- Express.js

### Authentication
- JWT (JSON Web Token)
- Token Blacklisting

### AI Integration
- Gemini API (Google GenAI)

### Other Tools
- Puppeteer (PDF generation)
- MongoDB (Database)

---

## 🧩 System Architecture


Client (React)
↓
API Layer (Express.js)
↓
Authentication (JWT + Blacklist)
↓
Business Logic
↓
AI Layer (Gemini API)
↓
Database (MongoDB)


---

## 📂 Project Structure


PrepMate_AI/
│
├── client/ # React frontend
├── server/ # Backend (Node + Express)
│ ├── controllers/
│ ├── routes/
│ ├── models/
│ ├── middleware/
│ └── utils/
│
├── uploads/ # Resume files
├── config/ # DB & environment config
├── .env
├── package.json
└── README.md


---

## ⚙️ Installation & Setup

### 1️⃣ Clone the repository
```bash
git clone https://github.com/your-username/PrepMate_AI.git
cd PrepMate_AI
2️⃣ Install dependencies
Backend
cd server
npm install
Frontend
cd client
npm install
3️⃣ Setup Environment Variables

Create a .env file in the server folder:

PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
GEMINI_API_KEY=your_gemini_api_key
4️⃣ Run the Application
Start backend
cd server
npm run dev
Start frontend
cd client
npm start
🚀 How It Works
User registers/login securely using JWT
Uploads resume
System extracts skills from resume
User provides job description
AI analyzes both inputs using Gemini
Platform:
Detects skill gaps
Suggests improvements
Generates interview questions
User can download ATS-optimized resume as PDF
🔒 Security Features
JWT Authentication
Token Blacklisting (prevents reuse after logout)
Secure environment variables
Protected API routes
🧪 Pre-Launch Checks
✅ API testing (Postman)
✅ Resume parsing accuracy validation
✅ AI response testing
✅ JWT security validation
📈 Future Enhancements
🔊 Voice-based interview practice
📱 Mobile responsive / app version
📊 Advanced analytics dashboard
🌍 Multi-language support
🤝 Real-time mentor feedback
🤝 Contributing

Contributions are welcome!
Fork the repo and submit a pull request 🚀

👩‍💻 Author

Pranali Pawar

GitHub: https://github.com/pranalipawar24
