# 🧠 ElpisHR – AI-Powered Recruitment App

> 🏆 **Award:** 2nd Best Graduation Project Poster
> 🎓 **Bachelor of Computer Science – Umm Al-Qura University**

![Flutter](https://img.shields.io/badge/Flutter-3.0-blue?logo=flutter)
![Python](https://img.shields.io/badge/Python-3.9-blue?logo=python)
![Flask](https://img.shields.io/badge/Flask-2.0-black?logo=flask)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--3.5-green?logo=openai)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Supabase-blue?logo=postgresql)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 📌 Overview

**ElpisHR** is an AI-powered recruitment platform designed to modernize the hiring process through intelligent automation. The platform streamlines recruitment by automatically sorting resumes using Natural Language Processing (NLP), conducting AI-powered preliminary interviews, and providing HR professionals with data-driven insights for more objective hiring decisions.

By integrating advanced AI technologies into a single platform, ElpisHR reduces manual effort, improves recruitment efficiency, and supports the digital transformation goals of **Saudi Vision 2030**.

---

## 📄 Documentation

- **Final Report:** [Final Report](https://drive.google.com/file/d/18xrQSiriiAXdydM0kRyID8Saak0Sy51e/view?usp=sharing)
- **Award Certificate:** [`Award_Certificate.pdf`](./assets/Award_Certificate.pdf) 

---

## 🎥 Demo

▶️ **Watch the project demo here:**  
[Demo Video](https://drive.google.com/file/d/1nXlrnkcmSo6qZpXQeLMEt_KCw3q8SnuN/view?usp=sharing)

---

## ✨ Key Features

### 👩‍💼 HR Portal

- 📊 Interactive dashboard with recruitment analytics
- 🤖 AI-powered resume ranking using Sentence-BERT and Cosine Similarity
- 📅 Interview management and candidate tracking
- 📝 Create, edit, and close job postings
- 📄 Review AI-generated interview summaries
- 📈 Data-driven hiring recommendations

---

### 👤 Candidate Portal

- 🔍 Browse available job opportunities
- 📄 Upload resumes (PDF or scanned images)
- 💬 Complete AI-powered chatbot interviews
- 📊 Track application status in real time
- 👤 Manage profile and application history

---

### 🔐 Authentication & Security

- User registration and login
- JWT Authentication
- Role-Based Access Control (RBAC)
- Email verification
- Forgot Password functionality

---

## 🛠️ Technology Stack

| Category | Technologies | Purpose |
|----------|--------------|---------|
| **Frontend** | Flutter (Dart) | Cross-platform mobile & web application |
| **Backend** | Python, Flask | RESTful API and business logic |
| **Database** | Supabase (PostgreSQL) | Data storage and authentication |
| **Resume Ranking AI** | Sentence-BERT (all-MiniLM-L6-v2), Cosine Similarity | Semantic resume matching |
| **Interview AI** | OpenAI GPT-3.5 Turbo, SpaCy, NLTK | Conversational interviews |
| **OCR** | pdfplumber, pdf2image, pytesseract | Extract text from PDFs and scanned resumes |
| **Version Control** | Git & GitHub | Source code management |

---

## 📁 Project Structure

```text
ElpisHR/
│
├── android/                 # Android project
├── ios/                     # iOS project
├── lib/                     # Flutter application
├── backend/
│   ├── app.py
│   ├── requirements.txt
│   └── ...
├── assets/                  # Images & certificates
├── docs/                    # Documentation
├── test/                    # Flutter tests
├── web/
├── windows/
├── linux/
├── macos/
├── .devcontainer/
└── README.md
```

---

## 🧠 AI Implementation

### 1️⃣ Resume Ranking (Sentence-BERT)

#### Workflow

- Extract text from uploaded resumes
- Convert resumes and job descriptions into embeddings using Sentence-BERT
- Calculate semantic similarity using Cosine Similarity
- Rank applicants based on similarity score
- Display the best candidates to HR personnel

#### Supported Resume Formats

- PDF
- Scanned PDFs
- Image-based resumes (OCR)

---

### 2️⃣ AI Interview Chatbot

Powered by **OpenAI GPT-3.5 Turbo**

#### Features

- Dynamic interview conversations
- Context-aware follow-up questions
- Candidate response evaluation
- Communication and experience assessment
- Automatic interview summary generation
- Job-fit scoring for HR review

---

### 3️⃣ AI Performance

| Module | Metric | Result |
|---------|--------|--------|
| Resume Ranking | Accuracy | **81.50%** |
| Resume Ranking | F1 Score | **0.7945** |
| Resume Ranking | Loss | **0.0865** |
| AI Interview | Overall Accuracy | **64.7%** |
| AI Interview | Average Response Speed | **~73 ms/token** |

---

## 🔗 REST API

| Category | Method | Endpoint | Description |
|----------|--------|----------|-------------|
| Authentication | POST | `/signup` | Register a new user |
| Authentication | POST | `/login` | Authenticate user and return JWT |
| Jobs | POST | `/add_job` | Create a new job posting |
| Jobs | GET | `/get_open_jobs` | Retrieve all available jobs |
| Applications | POST | `/save_application` | Submit a job application |
| AI Ranking | GET | `/sort_applications/<jobID>` | Rank applicants using AI |
| AI Interview | POST | `/start_interview` | Start AI interview |
| AI Interview | POST | `/send_message` | Continue chatbot conversation |
| HR | GET | `/get_candidate_summary` | Retrieve AI interview report |

---

## 🚀 Running the Project

### Prerequisites

- Flutter SDK
- Python 3.9+
- Supabase Account (or PostgreSQL)
- Git

---

### Backend Setup

```bash
cd backend

python -m venv venv

# Windows
venv\Scripts\activate

# Linux / macOS
source venv/bin/activate

pip install -r requirements.txt

python app.py
```

Backend will run at:

```text
http://localhost:5000
```

---

### Frontend Setup

```bash
cd ..

flutter pub get

flutter run
```

Choose your preferred device:

- Android
- iOS
- Web

---

### Environment Variables

Create a `.env` file inside the `backend/` directory.

```env
OPENAI_API_KEY=your_openai_api_key

SUPABASE_URL=your_supabase_url

SUPABASE_ANON_KEY=your_supabase_anon_key

JWT_SECRET=your_jwt_secret
```

---

## 🧪 Testing

### Functional Testing

Validated the following modules against the system requirements:

- Authentication
- Resume Ranking
- AI Interview Chatbot
- Job Management
- Application Submission

### Usability Testing

Conducted usability evaluations with:

- HR professionals
- Job seekers

### Dataset

Training and evaluation were performed using the **Kaggle Resume Dataset**, containing:

- 2,400+ resumes
- 853 job descriptions

---

## 🏆 Awards & Recognition

🥈 **2nd Best Graduation Project Poster**

**College of Computer Science**  
**Umm Al-Qura University**

Recognized for applying Artificial Intelligence to optimize recruitment processes in alignment with **Saudi Vision 2030**.

---

## 👩‍💻 My Contributions

As the **Core Developer**, I contributed to:

- Designing the system architecture
- Developing the Flask backend
- Building RESTful APIs
- Integrating OpenAI GPT-3.5
- Implementing Sentence-BERT resume ranking
- Designing the PostgreSQL database using Supabase
- Connecting the Flutter frontend with backend services
- Performing functional and usability testing
- Writing the final project documentation
- Presenting the project to the evaluation committee

---

## 🔮 Future Improvements

- 📊 Employee performance analytics
- 🎓 AI-powered training recommendations
- 🔗 Integration with SAP and Oracle HR systems
- 📱 Offline application support with synchronization
- 🌍 Multi-language support (Arabic, English, French)

---

## 📫 Contact

- **GitHub:** [YaraAlansari-CS](https://github.com/YaraAlansari-CS)
- **LinkedIn:** [Yara Alansari](https://www.linkedin.com/in/yara-alansari-64b17a317)
- **Email:** [yara.alansari01@gmail.com](mailto:yara.alansari01@gmail.com)

---

⭐ **If you found this project interesting or helpful, consider giving it a star on GitHub.**

🙏🏻 **Thank you for taking the time to explore this project!**
