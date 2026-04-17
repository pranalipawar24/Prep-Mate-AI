# 🚀 PrepMate AI – GenAI Job Preparation Platform

A smart **AI-powered job preparation platform** that helps users analyze resumes, detect skill gaps, and prepare for interviews using **GenAI**.

This project simulates a real-world system where users can upload resumes, compare them with job descriptions, and generate **ATS-optimized resumes and interview questions**.

---

## 📌 Features

* ✅ Secure user authentication using JWT
* 📄 Upload and process resumes
* 🤖 AI-powered resume analysis using Gemini
* 🎯 Skill gap detection (Resume vs Job Description)
* 🧠 AI-generated interview questions
* 📑 ATS-optimized resume generation
* 📄 PDF export using Puppeteer
* 🔐 Token blacklisting for enhanced security
* 🧩 Scalable full-stack architecture

---

## ⚙️ Tech Stack

| Component        | Technology               |
| ---------------- | ------------------------ |
| Frontend         | React.js                 |
| Backend          | Node.js + Express.js     |
| Authentication   | JWT + Token Blacklisting |
| Database         | MongoDB                  |
| AI Integration   | Gemini API               |
| PDF Generation   | Puppeteer                |
| Environment Mgmt | dotenv                   |

---

## 🧠 How It Works

1. User registers/login securely
2. Uploads resume
3. System extracts key information and skills
4. User inputs job description
5. AI (Gemini) analyzes:

   * Resume content
   * Job requirements
6. Platform:

   * Detects missing skills
   * Suggests improvements
   * Generates interview questions
7. User downloads ATS-optimized resume (PDF)

---

## 📁 Project Structure

```
PrepMate_AI/
│
├── client/                  # React frontend
├── server/                  # Backend (Node + Express)
│   ├── controllers/         # Business logic
│   ├── routes/              # API routes
│   ├── models/              # DB schemas
│   ├── middleware/          # Auth middleware
│   ├── utils/               # Helper functions (AI, parsing)
│
├── uploads/                 # Uploaded resumes
├── config/                  # DB & environment config
├── .env                     # Environment variables
├── package.json
├── README.md
```

---

## 🚀 Getting Started

### 🔧 1. Clone the Repo

```bash
git clone https://github.com/pranalipawar24/PrepMate_AI.git
cd PrepMate_AI
```

---

### 📦 2. Install Dependencies

#### Backend

```bash
cd server
npm install
```

#### Frontend

```bash
cd client
npm install
```

---

### 🔐 3. Setup .env File

Create a `.env` file inside the `server` folder:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
GEMINI_API_KEY=your_gemini_api_key
```

---

### ▶️ 4. Run the Application

#### Start Backend

```bash
cd server
npm run dev
```

#### Start Frontend

```bash
cd client
npm start
```

---

## 📤 API Endpoints (Sample)

### 📍 POST `/upload-resume`

Upload user resume.

**Response:**

```json
{ "message": "Resume uploaded successfully" }
```

---

### 📍 POST `/analyze`

Analyze resume + job description.

**Response:**

```json
{
  "missing_skills": ["Docker", "System Design"],
  "suggestions": ["Improve project descriptions"],
  "interview_questions": ["Explain REST APIs", "What is JWT?"]
}
```


---

## 🧠 Future Improvements

* 📱 Mobile-friendly UI
* 🔊 Voice-based interview practice
* 📊 Advanced analytics dashboard
* 🌍 Multi-language support
* 🤝 Real-time mentor feedback

---

## 👩‍💻 Author

**Pranali Pawar**
[GitHub Profile](https://github.com/pranalipawar24)
Computer Engineering Student

---

## 🛡 License

This project is licensed under the MIT License.

---
