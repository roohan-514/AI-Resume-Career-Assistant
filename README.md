# 🤖 AI Resume & Career Assistant

An intelligent AI-powered career assistant that leverages OpenAI's capabilities to help professionals build compelling resumes, prepare for interviews, discover career paths, and advance their careers. This full-stack application combines Python backend AI with a React frontend for an intuitive user experience.

## 🛠️ Tech Stack
- **Backend**: Python, Flask/FastAPI
- **Frontend**: React, Redux, Material-UI
- **AI Engine**: OpenAI GPT-4, Embedding Models
- **Database**: MongoDB, PostgreSQL
- **Authentication**: JWT, OAuth2
- **Deployment**: Docker, AWS/Heroku

## 📋 Features
✅ AI-powered resume builder with smart suggestions
✅ Interview preparation with Q&A generation
✅ Personalized career path discovery
✅ Cover letter generation
✅ Skills assessment & gap analysis
✅ Job matching recommendations
✅ Real-time AI-powered chat assistance
✅ Resume templates and formatting
✅ LinkedIn integration
✅ Portfolio builder
✅ Interview scheduling
✅ Performance analytics
✅ Multi-language support
✅ Export to PDF/DOCX

## 📁 Project Structure
```
AI-Resume-Career-Assistant/
├── backend/
│   ├── README.md
│   ├── requirements.txt
│   ├── config.py
│   ├── main.py
│   ├── .env.example
│   ├── app/
│   │   ├── __init__.py
│   │   ├── models/
│   │   │   ├── user.py
│   │   │   ├── resume.py
│   │   │   └── interview.py
│   │   ├── services/
│   │   │   ├── __init__.py
│   │   │   ├── openai_service.py
│   │   │   ├── resume_service.py
│   │   │   ├── interview_service.py
│   │   │   └── career_service.py
│   │   ├── utils/
│   │   │   └── helpers.py
│   │   └── middleware/
│   │       └── auth.py
│   └── tests/
│       ├── test_resume.py
│       ├── test_interview.py
│       └── test_career.py
├── frontend/
│   ├── README.md
│   ├── package.json
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── ResomeBuilder/
│   │   │   ├── InterviewPrep/
│   │   │   ├── CareerPath/
│   │   │   └── ChatAssistant/
│   │   ├── pages/
│   │   │   ├── Dashboard.js
│   │   │   ├── Resume.js
│   │   │   ├── Interview.js
│   │   │   └── Career.js
│   │   ├── services/
│   │   │   ├── api.js
│   │   │   └── auth.js
│   │   └── App.js
│   └── .env
└── docker-compose.yml
```

## 🚀 Installation

### Prerequisites
- Python 3.9+
- Node.js 16.x+
- MongoDB or PostgreSQL
- OpenAI API Key
- npm or yarn

### Backend Setup

#### Step 1: Clone Repository
```bash
git clone https://github.com/roohan-514/AI-Resume-Career-Assistant.git
cd AI-Resume-Career-Assistant/backend
```

#### Step 2: Create Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

#### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

#### Step 4: Configure Environment
```bash
cp .env.example .env
```

Edit `.env`:
```env
OPENAI_API_KEY=sk-...
OPENAI_MODEL=gpt-4
DATABASE_URL=mongodb://localhost:27017/career-assistant
SECRET_KEY=your-secret-key
JWT_EXPIRATION=30d
FLASK_ENV=development
```

#### Step 5: Run Backend
```bash
python main.py
```

Backend runs on: `http://localhost:5000`

### Frontend Setup

#### Step 1: Navigate to Frontend
```bash
cd ../frontend
```

#### Step 2: Install Dependencies
```bash
npm install
```

#### Step 3: Configure Environment
```bash
cp .env.example .env
```

Edit `.env`:
```env
REACT_APP_API_URL=http://localhost:5000/api
REACT_APP_ENV=development
```

#### Step 4: Start Frontend
```bash
npm start
```

Frontend runs on: `http://localhost:3000`

## 📦 Backend Dependencies
```
flask==2.3.3
flask-cors==4.0.0
flask-jwt-extended==4.4.4
python-dotenv==1.0.0
openai==0.27.8
pymongo==4.4.1
psycopg2-binary==2.9.7
sqlalchemy==2.0.20
pydantic==2.0.0
requests==2.31.0
PyPDF2==3.0.1
python-docx==0.8.11
pytest==7.4.0
pytest-cov==4.1.0
```

## 📦 Frontend Dependencies
```json
{
  "react": "^18.2.0",
  "react-dom": "^18.2.0",
  "react-router-dom": "^6.11.0",
  "axios": "^1.4.0",
  "redux": "^4.2.1",
  "react-redux": "^8.1.1",
  "@mui/material": "^5.13.0",
  "@mui/icons-material": "^5.13.0",
  "formik": "^2.4.2",
  "yup": "^1.2.0"
}
```

## 🎯 API Endpoints

### Authentication
```bash
POST /api/auth/register
POST /api/auth/login
POST /api/auth/refresh-token
POST /api/auth/logout
```

### Resume
```bash
POST /api/resume - Create new resume
GET /api/resume/:id - Get resume
PUT /api/resume/:id - Update resume
DELETE /api/resume/:id - Delete resume
POST /api/resume/:id/export-pdf - Export as PDF
POST /api/resume/generate-suggestions - AI suggestions
```

### Interview Preparation
```bash
POST /api/interview - Create interview session
GET /api/interview/:id - Get interview prep
POST /api/interview/:id/generate-questions - Generate Q&A
POST /api/interview/:id/feedback - Get AI feedback
POST /api/interview/:id/practice - Practice interview
```

### Career Guidance
```bash
POST /api/career/path-discovery - Discover career paths
GET /api/career/recommendations - Get recommendations
POST /api/career/skills-gap - Analyze skills gap
POST /api/career/job-matches - Find job matches
GET /api/career/salary-insights - Salary data
```

### Chat Assistant
```bash
POST /api/chat/message - Send message
GET /api/chat/history - Get conversation history
DELETE /api/chat/history - Clear history
```

## 💻 Usage Examples

### Python Backend
```python
from app.services.openai_service import OpenAIService
from app.services.resume_service import ResumeService

# Initialize services
openai_service = OpenAIService()
resume_service = ResumeService()

# Generate resume suggestions
suggestions = openai_service.generate_resume_suggestions(
    skills=["Python", "React", "AWS"],
    experience_years=5
)

# Create resume
resume = resume_service.create_resume(
    user_id="user_123",
    data={
        "name": "John Doe",
        "email": "john@example.com",
        "summary": "Full-stack developer..."
    }
)
```

### API Request Examples

#### Register
```bash
curl -X POST http://localhost:5000/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{
    "email": "john@example.com",
    "password": "secure_password",
    "name": "John Doe"
  }'
```

#### Create Resume
```bash
curl -X POST http://localhost:5000/api/resume \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -d '{
    "name": "John Doe",
    "email": "john@example.com",
    "skills": ["Python", "React", "AWS"]
  }'
```

#### Get Resume Suggestions
```bash
curl -X POST http://localhost:5000/api/resume/generate-suggestions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -d '{
    "skills": ["Python", "React"],
    "experience_years": 5,
    "job_title": "Full Stack Developer"
  }'
```

#### Generate Interview Questions
```bash
curl -X POST http://localhost:5000/api/interview/generate-questions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -d '{
    "interview_id": "interview_123"
  }'
```

## 🤖 AI Features

### Resume Builder AI
- Smart content suggestions
- Grammar & spelling check
- ATS optimization
- Keyword recommendations
- Format consistency

### Interview Preparation
- STAR method training
- Behavioral question generation
- Technical question practice
- Mock interview with feedback
- Answer improvement suggestions

### Career Path Discovery
- Skills-to-career mapping
- Salary projections
- Industry trends
- Growth opportunities
- Transition paths

### Chat Assistant
- Real-time career advice
- Resume review
- Interview tips
- Job search guidance
- Professional development

## 🧪 Testing

### Backend Tests
```bash
pytest tests/test_resume.py
pytest tests/test_interview.py
pytest tests/test_career.py
pytest --cov=app tests/
```

### Frontend Tests
```bash
npm test
npm run test:coverage
npm run test:watch
```

## 🔐 Security
✅ JWT authentication
✅ Password hashing (bcrypt)
✅ CORS protection
✅ Input validation
✅ Rate limiting
✅ Environment variables
✅ Secure API keys storage

## 🚀 Deployment

### Docker
```bash
docker-compose up
```

### Heroku
```bash
heroku create your-app-name
heroku config:set OPENAI_API_KEY=sk-...
git push heroku main
```

### Environment Variables
```env
FLASK_ENV=production
DATABASE_URL=postgresql://user:pass@host/db
OPENAI_API_KEY=sk-your-key
JWT_SECRET_KEY=your-secret
```

## 📈 Features Roadmap
- [ ] Skill assessment tests
- [ ] Video interview practice
- [ ] Salary negotiation guide
- [ ] Remote job finder
- [ ] Freelance gig matcher
- [ ] Course recommendations
- [ ] Mentor matching
- [ ] Industry network

## 🤝 Contributing
Contributions welcome! See [CONTRIBUTING.md](CONTRIBUTING.md)

## 📄 License
MIT License - See [LICENSE](LICENSE)

## 📧 Support
- **Issues**: [GitHub Issues](https://github.com/roohan-514/AI-Resume-Career-Assistant/issues)
- **Email**: Contact via GitHub

## 🎯 Future Enhancements
- [ ] Mobile app (React Native)
- [ ] Voice-to-resume conversion
- [ ] Behavioral analytics
- [ ] Company database integration
- [ ] Real-time job alerts
- [ ] Network analysis tools
- [ ] Career milestone tracking
- [ ] 1-on-1 coaching platform

---

**Status**: 🚀 Production Ready

**Last Updated**: 2024

**Maintained By**: [@roohan-514](https://github.com/roohan-514)
