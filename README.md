# 🧠 ElpisHR – AI-Powered Recruitment Platform

> **🏆 Award: 2nd Best Graduation Project**  
> *Computer Scince, Umm Al-Qura University*

![Flutter](https://img.shields.io/badge/Flutter-3.0-blue?logo=flutter)
![Python](https://img.shields.io/badge/Python-3.9-blue?logo=python)
![Flask](https://img.shields.io/badge/Flask-2.0-black?logo=flask)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--3.5-green?logo=openai)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Supabase-blue?logo=postgresql)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 📌 Overview
**ElpisHR** is an AI-driven HR platform designed to revolutionize the recruitment process. It streamlines hiring by automating **CV sorting** using Natural Language Processing (NLP), conducting **initial interviews** via an intelligent AI chatbot (powered by OpenAI GPT-3.5), and providing HR teams with **data-driven analytics** for unbiased decision-making.

By integrating these features, ElpisHR enhances HR efficiency and aligns with the digital transformation goals of **Saudi Arabia's Vision 2030**.

> **📄 Final Report:** [Click here to view the full documentation](./docs/Final_Report.pdf)  !!!!!!!!
> **🏅 Award Certificate:** [View Certificate](./assets/Award_Certificate.pdf)  !!!!!!!!

---

## 🎯 Key Features
The platform serves two main user types with distinct, powerful interfaces:

### 👩‍💼 HR Interface (Recruiters & Managers)
- **Dashboard Analytics:** Real-time overview of job openings and applications.
- **AI-Powered Resume Sorting:** Automatically ranks candidates using **Sentence-BERT** and **Cosine Similarity**.
- **Interview Management:** Sends invitations and reviews AI-generated interview summaries.
- **Job Posting Management:** Create, edit, or close job listings effortlessly.

### 👤 Candidate Interface (Job Seekers)
- **Job Search & Apply:** Browse openings and apply with CV uploads (supports PDF & scanned images via OCR).
- **AI Chatbot Interview:** Engage in a dynamic, adaptive conversational interview powered by GPT-3.5.
- **Application Tracking:** Real-time status updates and personalized dashboard.
- **Profile Management:** Manage personal information and application history.

### 🔐 Common Features (Both Interfaces)
- Secure **Authentication** (Sign-up, Login, JWT Tokens) with Role-Based Access Control (RBAC).
- Email verification and "Forgot Password" recovery.

---

## 🛠️ Tech Stack

| **Category** | **Technology** | **Purpose** |

| **Frontend (Mobile)** | Flutter (Dart) | Cross-platform app (Android/iOS) with a smooth native-like UI. |
| **Backend Server** | Python, Flask | RESTful API handling authentication, job logic, and AI integration. |
| **Database** | Supabase (PostgreSQL) | Secure storage for users, jobs, applications, and interview results. |
| **AI / NLP (Sorting)** | Sentence-BERT (SBERT) + Cosine Similarity | Semantic matching and ranking of resumes against job descriptions. |
| **AI / NLP (Chatbot)** | OpenAI GPT-3.5, SpaCy, NLTK | Real-time conversational interviews and response evaluation. |
| **OCR (Text Extraction)** | pdfplumber, pdf2image, pytesseract | Extracts text from PDFs and scanned image resumes. |
| **Version Control** | Git & GitHub | Code management and collaboration. |

---

## 📁 Project Structure (Current Repository)
*This structure reflects the actual Flutter project layout:*
ElpisHR/
├── android/ # Android native build files
├── ios/ # iOS native build files
├── lib/ # Flutter frontend source code (Dart)
├── backend/ # Python Flask backend server
│ ├── app.py # Main entry point
│ ├── requirements.txt # Python dependencies
│ └── ... # API routes & AI logic
├── web/ # Flutter web build
├── windows/ & linux/ & macos/ # Desktop builds
├── test/ # Flutter unit tests
├── assets/ # Project images & certificate
├── docs/ # Documentation (Final Report, etc.)
├── .devcontainer/ # Dev container config
└── README.md # This file

---

## 🧠 AI Algorithms & Implementation Details

### 1. CV Sorting & Candidate Ranking (SBERT)
- **Approach:** Uses **Sentence-BERT (all-MiniLM-L6-v2)** to convert resumes and job descriptions into vector embeddings.
- **Matching:** Calculates **Cosine Similarity** between vectors to generate a score (0 to 1).
- **Ranking:** Sorts candidates by score, highlighting top matches for HR review.
- **Text Extraction:** Handles multiple formats (PDF, scanned images) using `pdfplumber` and `pytesseract` (OCR).

### 2. AI-Powered Interview Chatbot (OpenAI)
- **Approach:** Employs **GPT-3.5 Turbo** to simulate human-like interviews.
- **Interaction:** Asks predefined and adaptive follow-up questions based on candidate responses.
- **Evaluation:** Analyzes responses for relevance, clarity, and experience depth.
- **Summary:** Generates a structured report (strengths, weaknesses, job-fit score) stored for HR review.

### 3. Performance Metrics

| **Module** | **Metric** | **Result** |

| **Sorting Applications** | Accuracy / F1-Score | 81.50% / 0.7945 |
| **Sorting Applications** | Loss | 0.0865 |
| **Interview Chatbot** | Overall Accuracy (Risk Factor) | 64.7% |
| **Interview Chatbot** | Response Speed | ~73 ms per token |

---

## 🔗 API Endpoints (Flask Backend)

| **Category** | **Method** | **Endpoint** | **Description** |

| **Auth** | POST | `/signup` | Register new user (HR/Candidate). |
| **Auth** | POST | `/login` | Login & receive JWT token. |
| **Jobs** | POST | `/add_job` | HR adds a new job posting. |
| **Jobs** | GET | `/get_open_jobs` | Retrieve all available jobs. |
| **Applications** | POST | `/save_application` | Candidate applies with CV. |
| **AI Sorting** | GET | `/sort_applications/<jobID>` | AI ranks applicants using SBERT. |
| **AI Chatbot** | POST | `/start_interview` | Initiate AI interview. |
| **AI Chatbot** | POST | `/send_message` | Send response to chatbot. |
| **HR** | GET | `/get_candidate_summary` | Get AI-generated interview report. |

---

## 🚀 How to Run Locally

### Prerequisites
- **Flutter SDK** (for mobile/web)
- **Python 3.9+** (for backend)
- **Supabase Account** (or PostgreSQL)

### 1. Backend Setup (Flask)
```bash
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
python app.py

Server runs on http://localhost:5000

### 2. Frontend Setup (Flutter)
bash
cd ..  # Go to root folder (where pubspec.yaml is located)
flutter pub get
flutter run
Select your device (Android/iOS/Web).

### 3. Environment Variables
Create a .env file in the backend/ folder:

text
OPENAI_API_KEY=your_openai_key
SUPABASE_URL=your_supabase_url
SUPABASE_ANON_KEY=your_supabase_anon_key
JWT_SECRET=your_jwt_secret
****

🧪 Testing Methodology
Functional Testing: Validated core features (CV sorting, chatbot, authentication) against system requirements.

Usability Testing: Evaluated user experience (navigation, intuitiveness) with HR professionals and candidates.

Dataset: Trained AI models on the Kaggle Resume Dataset (2,400+ resumes, 853 job descriptions).


🏆 Awards & Recognition
2nd Best Graduation Project – [اسم جامعتك], [السنة].

Recognized for innovation in applying AI to optimize HR operations in line with Saudi Vision 2030.


👩‍💻 My Role
As the core developer and team lead, I was responsible for:

Designing the system architecture (Frontend + Backend + AI integration).

Building the Flask backend and all RESTful APIs.

Integrating OpenAI GPT-3.5 and Sentence-BERT for the AI features.

Designing the SQL database schema on Supabase.

Conducting functional and usability testing.

Writing the final project documentation and presenting to the judging panel.

🔮 Future Work
Employee Insights: Advanced analytics for employee performance and training recommendations.

Third-Party Integration: Connect with external HR tools (SAP, Oracle).

Offline Access: Allow candidates to apply without internet (sync later).

Multi-Language Support: Expand usability globally (Arabic, English, French).


📫 Connect with Me
LinkedIn: https://linkedin.com/in/[your-username]

GitHub: https://github.com/YaraAlansari-CS

Email: your-email@example.com

⭐ If you like this project, don't forget to give it a star!
## 📁 Project Structure (Current Repository)
*This structure reflects the actual Flutter project layout:*
