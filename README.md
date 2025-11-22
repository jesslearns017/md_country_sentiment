# 🏢 Miami-Dade County Small Business Sentiment Intelligence

An AI-powered platform combining sentiment analysis and interactive resource recommendations for Miami-Dade County small businesses.

**Live Demo:** [https://mdcountysentiment.netlify.app](https://mdcountysentiment.netlify.app)

---

## 🎯 What This Platform Does

This capstone project combines two MDC/Miami-Dade County initiatives:

1. **📊 Sentiment Analysis** (Project #2): Monitors and analyzes social media sentiment from small business owners
2. **🤖 AI Chatbot Assistant** (Project #8): Provides personalized resource recommendations based on business needs

**Result:** An intelligent system that understands business concerns and connects owners to relevant County resources.

---

## ✨ Key Features

### 1. Interactive AI Chatbot
- 💬 Conversational interface with natural language understanding
- 🎯 Detects sentiment and topics automatically
- 📋 Recommends relevant County resources
- 🚀 8 quick-reply buttons for common questions
- 📱 Mobile-optimized chat experience

### 2. Real-Time Sentiment Analysis
- 🧠 AI-powered sentiment detection using TextBlob
- 📈 Sentiment scoring (-1 to +1 scale)
- 🏷️ Automatic topic extraction
- 📊 Supports 13 business categories

### 3. Social Media Dashboard
- 📱 Displays analyzed posts from small business owners
- 📊 Sentiment breakdown statistics
- 🎨 Color-coded sentiment indicators
- 📈 Satisfaction rate calculations

---

## 🌐 Live Deployment

### Frontend (Netlify)
**URL:** https://mdcountysentiment.netlify.app

- Interactive chatbot interface
- Sentiment analysis demo
- Social media dashboard
- Miami-Dade County branding

### Backend API (Render)
**URL:** https://md-county-sentiment.onrender.com

- RESTful API endpoints
- AI sentiment analysis engine
- Resource recommendation system
- Real-time processing

---

## 🎮 How to Use

### Chat with the AI Assistant

**Quick Reply Buttons:**
- 📋 Permits - Business licenses and approvals
- 💰 Funding - Grants and loans
- 📚 Training - Workshops and courses
- 💵 Taxes - Tax filing and credits
- ⚖️ Legal - Attorneys and contracts
- 🛡️ Insurance - Business coverage
- 📢 Marketing - Advertising and branding
- 🏢 Real Estate - Office space and leases

**Or Type Freely:**
```
"I need help with guardianship planning"
"Looking for business insurance"
"How do I market my bakery?"
"Need help hiring employees"
```

The AI understands natural language and provides relevant resources!

---

## 🧠 AI Capabilities

### 13 Topic Categories

The platform recognizes and provides resources for:

1. **Permits** - Licenses, certificates, approvals, zoning
2. **Funding** - Grants, loans, capital, investment
3. **Training** - Workshops, courses, bootcamps, education
4. **Taxes** - Filing, credits, deductions, obligations
5. **Legal** - Attorneys, contracts, guardianship, LLC/Corp structure
6. **Insurance** - Liability, health, workers comp, coverage
7. **Marketing** - Advertising, websites, social media, SEO
8. **Technology** - IT, software, cybersecurity, e-commerce
9. **Real Estate** - Property, leases, zoning, office space
10. **HR** - Hiring, payroll, benefits, compliance
11. **Export** - International trade, customs, shipping
12. **Networking** - Events, chambers, industry groups
13. **Certification** - MBE, WBE, SBE certifications

### 43 County Resources

Each category contains 3-4 specific County resources with:
- Resource name and description
- Direct URL links
- Relevance scoring
- Keyword matching

---

## 🛠️ Tech Stack

### Backend
- **Language:** Python 3.11
- **Framework:** Flask (REST API)
- **NLP Engine:** TextBlob
- **Server:** Gunicorn
- **Hosting:** Render.com

### Frontend
- **Languages:** HTML5, CSS3, JavaScript
- **Styling:** Custom CSS with Miami-Dade branding
- **API Integration:** Fetch API
- **Hosting:** Netlify

### AI/ML
- **Sentiment Analysis:** TextBlob polarity scoring
- **Topic Extraction:** Keyword matching with 100+ keywords
- **Recommendation Engine:** Relevance scoring algorithm

### Deployment
- **Version Control:** GitHub
- **CI/CD:** Automatic deployment on push
- **Backend:** Render (free tier)
- **Frontend:** Netlify (free tier)

---

## 📡 API Documentation

### Base URL
```
https://md-county-sentiment.onrender.com
```

### Endpoints

#### 1. Health Check
```http
GET /api/health
```

**Response:**
```json
{
  "status": "healthy",
  "version": "1.0.0",
  "timestamp": "2025-11-21T05:41:18.804004"
}
```

#### 2. Analyze Sentiment
```http
POST /api/analyze
Content-Type: application/json

{
  "text": "Just got my business license approved! So easy!"
}
```

**Response:**
```json
{
  "text": "Just got my business license approved! So easy!",
  "sentiment": {
    "score": 0.85,
    "sentiment": "positive",
    "subjectivity": 0.9
  },
  "topics": ["permits"]
}
```

#### 3. Get Recommendations
```http
POST /api/recommend
Content-Type: application/json

{
  "query": "I need help with guardianship planning"
}
```

**Response:**
```json
{
  "query": "I need help with guardianship planning",
  "sentiment": {
    "score": 0.0,
    "sentiment": "neutral",
    "subjectivity": 0.4
  },
  "topics": ["legal"],
  "recommendations": [
    {
      "id": 19,
      "name": "Guardianship & Estate Planning",
      "description": "Business succession and guardianship planning resources",
      "url": "https://business.miamidade.gov/guardianship",
      "relevance_score": 2
    },
    {
      "id": 16,
      "name": "Legal Aid Services",
      "description": "Free and low-cost legal assistance",
      "url": "https://business.miamidade.gov/legal-aid",
      "relevance_score": 1
    }
  ]
}
```

#### 4. Get Social Media Posts
```http
GET /api/posts?count=10
```

**Response:**
```json
{
  "posts": [
    {
      "id": "real_001",
      "text": "Finally got my Miami-Dade business license renewed online!",
      "sentiment": "positive",
      "topic": "permits",
      "source": "twitter",
      "timestamp": "2025-11-15T10:30:00Z"
    }
  ],
  "total": 10,
  "data_source": "real"
}
```

#### 5. Get Statistics
```http
GET /api/statistics
```

**Response:**
```json
{
  "total_posts": 25,
  "sentiment_breakdown": {
    "positive": 15,
    "negative": 6,
    "neutral": 4
  },
  "positive_percentage": 60.0,
  "topics": ["permits", "funding", "training", "taxes", "legal"]
}
```

---

## 🚀 Local Development

### Prerequisites
```bash
# Python 3.11+
python --version

# Install dependencies
pip install flask flask-cors textblob gunicorn --break-system-packages

# Download NLP data
python -m textblob.download_corpora
```

### Run Backend Locally
```bash
# Clone the repository
git clone https://github.com/jesslearns017/md_county_sentiment.git
cd md_county_sentiment

# Run the API
python backend_api.py

# API runs on http://localhost:5000
```

### Test the API
```bash
# Health check
curl http://localhost:5000/api/health

# Analyze text
curl -X POST http://localhost:5000/api/analyze \
  -H "Content-Type: application/json" \
  -d '{"text": "I love the new permit portal!"}'

# Get recommendations
curl -X POST http://localhost:5000/api/recommend \
  -H "Content-Type: application/json" \
  -d '{"query": "I need help with taxes"}'

# Get posts
curl http://localhost:5000/api/posts?count=5
```

### Run Frontend Locally
```bash
# Simply open index.html in a browser
open index.html

# Or use a local server
python -m http.server 8000
# Visit http://localhost:8000
```

---

## 📁 Project Structure

```
md_county_sentiment/
├── backend_api.py              # Flask API with sentiment analysis
├── index.html                  # Interactive chatbot interface
├── real_data.json              # Sample Miami-Dade business posts
├── data_scraper.py             # Social media data collection tool
├── requirements.txt            # Python dependencies
├── render.yaml                 # Render deployment config
├── README.md                   # This file
└── sentiment_platform_prototype.jsx  # Original React prototype
```

---

## 🎨 Features in Detail

### Chatbot Interface

**Design:**
- Clean, conversational chat bubbles
- User messages on right (blue)
- Bot messages on left (white)
- Typing animation while processing
- Resource cards with relevance scores

**Functionality:**
- Natural language understanding
- Context-aware responses
- Multi-topic detection
- Ranked recommendations
- Follow-up question support

### Sentiment Analysis

**Algorithm:**
- TextBlob polarity scoring
- Range: -1 (very negative) to +1 (very positive)
- Classification: positive (>0.1), negative (<-0.1), neutral (±0.1)
- Subjectivity measurement (0-1)

**Topic Extraction:**
- Keyword matching across 13 categories
- 100+ keywords recognized
- Multi-topic detection
- Priority ordering

### Recommendation Engine

**Matching:**
- Query analysis → sentiment + topics
- Resource scoring → keyword relevance
- Ranking → highest relevance first
- Filtering → top 3-5 results per category

---

## 🔄 Project Evolution

### Phase 1: MVP ✅ COMPLETE
- [x] Backend API with sentiment analysis
- [x] Interactive chatbot interface
- [x] 13 topic categories
- [x] 43 County resources
- [x] Deployed to Render + Netlify
- [x] Sample data integration (real_data.json)
- [x] Miami-Dade branding

### Phase 2: Real Data 🚧 IN PROGRESS
- [ ] Twitter/X API integration
- [ ] Facebook API integration
- [ ] Instagram API integration
- [ ] Reddit API integration
- [ ] Real-time data collection
- [ ] Database storage (PostgreSQL)

### Phase 3: Advanced Features 📋 PLANNED
- [ ] Trend detection and alerts
- [ ] Spanish language support
- [ ] Admin dashboard
- [ ] Email notifications
- [ ] Mobile app
- [ ] County CRM integration

---

## 🧪 Testing

### Manual Testing
1. Visit https://mdcountysentiment.netlify.app
2. Click quick reply buttons
3. Type custom questions
4. Verify relevant resources appear
5. Test all 13 categories

### Test Cases

**Legal Category:**
```
Input: "I need help with guardianship"
Expected: Legal Aid Services, Guardianship Planning
```

**Insurance Category:**
```
Input: "Looking for business insurance"
Expected: Business Insurance Guide, Insurance Providers
```

**Marketing Category:**
```
Input: "How do I advertise my bakery?"
Expected: Digital Marketing Bootcamp, Website Development
```

**Multi-topic:**
```
Input: "I'm opening a restaurant and need permits and funding"
Expected: Resources for both permits AND funding
```

---

## 📊 Data Sources

### Current: Sample Data
- **File:** `real_data.json`
- **Posts:** 25 realistic Miami-Dade scenarios
- **Topics:** All 13 categories covered
- **Sentiment:** Mix of positive, negative, neutral

### Future: Live APIs
- **Twitter/X:** Business mentions, hashtags
- **Facebook:** Public business pages
- **Instagram:** Business account posts
- **Reddit:** r/Miami, r/smallbusiness

---

## 🎓 Educational Value

### Learning Outcomes
- ✅ Full-stack development (frontend + backend)
- ✅ Natural Language Processing (NLP)
- ✅ REST API design and implementation
- ✅ Cloud deployment (Render + Netlify)
- ✅ Git workflow and version control
- ✅ AI/ML integration
- ✅ User interface design

### Technologies Learned
- Python Flask framework
- TextBlob sentiment analysis
- JavaScript fetch API
- CSS animations and responsive design
- GitHub CI/CD
- Cloud platform deployment

---

## 💡 Customization Guide

### Add More Resources

Edit `backend_api.py`:
```python
RESOURCES = {
    'your_category': [
        {
            'id': 44,
            'name': 'Your Resource Name',
            'description': 'What it does',
            'url': 'https://...',
            'keywords': ['word1', 'word2']
        }
    ]
}
```

### Add New Categories

1. Add to `RESOURCES` dict
2. Update `extract_topics()` with keywords
3. Optionally add quick reply button in `index.html`

### Customize Styling

Edit `index.html`:
```css
/* Miami-Dade Blue */
--primary-color: #0075C9;

/* County Green */
--secondary-color: #6B8E23;
```

---

## 🐛 Troubleshooting

### Backend Not Responding
```bash
# Check if Render service is live
curl https://md-county-sentiment.onrender.com/api/health

# If down, check Render dashboard
# Free tier may sleep after inactivity
```

### Chatbot Not Loading
```bash
# Check browser console for errors
# Clear browser cache (Ctrl+F5)
# Verify Netlify deployment status
```

### CORS Errors
```python
# Ensure flask-cors is enabled in backend_api.py
from flask_cors import CORS
app = Flask(__name__)
CORS(app)  # This should be present
```

### Topics Not Detected
```python
# Check if keywords match
# Topics detected in extract_topics() function
# Add more keywords if needed
```

---

## 📸 Screenshots

*Add screenshots after deployment to showcase:*
1. Full chatbot interface
2. Quick reply buttons in action
3. Chat conversation example
4. Resource recommendation display
5. Social media dashboard
6. Sentiment analysis demo
7. Mobile responsive view
8. API response examples

---

## 🤝 Contributing

This is an active capstone project! Contributions welcome:

1. **Fork the repository**
2. **Create a feature branch:** `git checkout -b feature/new-category`
3. **Make your changes:** Add resources, improve algorithm, enhance UI
4. **Test thoroughly:** Verify all endpoints work
5. **Submit a pull request:** Describe your changes

---

## 📝 Capstone Presentation Tips

### What to Demo (5 minutes)
1. **Show the chatbot** - Type a question, show recommendations
2. **Click quick replies** - Demonstrate all 8 categories
3. **Show the dashboard** - Sentiment breakdown, posts
4. **Explain the AI** - How sentiment analysis works
5. **Mention future** - Phase 2 with real APIs

### Key Talking Points
- ✅ Combines two capstone projects (#2 + #8)
- ✅ Uses real AI/ML (TextBlob NLP)
- ✅ Deployed and accessible online
- ✅ 13 categories, 43 resources
- ✅ Solves real County need
- ✅ Scalable architecture

### Impact Statement
> "This platform could help Miami-Dade County automatically monitor sentiment from thousands of small business owners, identify concerns before they escalate, and connect entrepreneurs to the right resources instantly. Instead of manually reading social media, County staff would see: '45% of permit posts were negative this week, suggesting process issues.'"

---

## 📞 Support & Resources

### Documentation
- [TextBlob Docs](https://textblob.readthedocs.io/) - Sentiment analysis
- [Flask Docs](https://flask.palletsprojects.com/) - Backend API
- [Render Docs](https://render.com/docs) - Backend deployment
- [Netlify Docs](https://docs.netlify.com/) - Frontend deployment

### Help Needed?
- **API Issues:** Check Flask error logs in Render dashboard
- **Frontend Issues:** Check browser console (F12)
- **Deployment Issues:** Check GitHub Actions and Render/Netlify logs
- **Feature Requests:** Open an issue on GitHub

---

## 🎉 Acknowledgments

**Miami Dade College**
- Dr. Ernesto Lee - Natural Language Processing
- Capstone Project Coordinators

**Miami-Dade County**
- Small Business Development Team
- County Technology Innovation

**Built with:**
- Flask + TextBlob
- HTML/CSS/JavaScript
- Render + Netlify
- Lots of ☕ and 💻

---

## 📄 License

This project is built for educational purposes as part of the Miami Dade College capstone program in collaboration with Miami-Dade County.

---

## 🚀 Ready to Explore?

**Live Demo:** [https://mdcountysentiment.netlify.app](https://mdcountysentiment.netlify.app)

**Backend API:** [https://md-county-sentiment.onrender.com/api/health](https://md-county-sentiment.onrender.com/api/health)

**GitHub:** [https://github.com/jesslearns017/md_county_sentiment](https://github.com/jesslearns017/md_county_sentiment)

---

**Built with ❤️ for Miami-Dade County Small Businesses**

*"It's not what you know but how you think" - Dr. Ernesto Lee*
