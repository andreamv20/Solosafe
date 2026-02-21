<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f6781290-3180-466e-9e20-cc2536d6f676" /># SOLOSAFE - Smart Solo Travel Planner

## 📋 Project Description

SOLOSAFE is an intelligent web application designed to empower solo travelers by providing personalized travel planning, safety recommendations, budget tracking, and community features. The platform helps solo travelers plan their journeys confidently while connecting them with a supportive community of like-minded adventurers.

## 🛠️ Tech Stack

- **Frontend**: HTML5, CSS3, Tailwind CSS, JavaScript (ES6+)
- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **APIs**: Google Maps API, Weather API, Travel Recommendations API
- **Deployment**: Netlify / Vercel
- **Other**: Font Awesome Icons, Chart.js for analytics

## ✨ Features

- **Smart Itinerary Builder**: AI-powered travel itinerary generation based on preferences, budget, and time constraints
- **Safety Dashboard**: Real-time safety alerts, emergency contacts, and travel advisories by destination
- **Budget Tracker**: Track expenses, set budgets, and get spending recommendations
- **Community Forum**: Connect with other solo travelers, share experiences, and get recommendations
- **Destination Guides**: Comprehensive guides for popular solo travel destinations with insider tips
- **Local Experience Finder**: Discover authentic local experiences and hidden gems near your location

## 📦 Installation

### Prerequisites
- Node.js v16+ 
- npm or yarn
- MongoDB Atlas account (or local MongoDB)
- Modern web browser (Chrome, Firefox, Safari, Edge)

### Setup Instructions

```bash
# Clone the repository
git clone https://github.com/username/solosafe.git
cd solosafe

# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../frontend
npm install

# Setup environment variables
cp .env.example .env
# Edit .env with your API keys and database URL

# Setup database
# Add your MongoDB connection string to .env
```

## 🚀 Running the Project

### Development Mode

**Backend**:
```bash
cd backend
npm run dev
# Runs on http://localhost:5000
```

**Frontend**:
```bash
cd frontend
npm run dev
# Runs on http://localhost:3000
```

### Production Mode

```bash
npm run build
npm start
```

Access the application at `http://localhost:3000`

## 📸 Screenshots

| Feature | Screenshot | Description |
|---------|-----------|-------------|
| **Dashboard** | (https://drive.google.com/file/d/1uDboxrs4zYFWTuPC7WhUv5prkHi79o5P/view?usp=drive_link)) | Main travel dashboard with itinerary overview |
| **Safety Alerts** | (https://drive.google.com/file/d/1F9VCBx19WaoLBB4t2mwwPWamYSWEb7IV/view?usp=drive_link) | Real-time safety information and advisories |
| **Budget Tracker** |( https://drive.google.com/file/d/1zd7WtdJO68esRw1s5G4EnIx1wkx3Ina8/view?usp=drive_link) | Expense tracking and budget analytics |

## 🎥 Demo Video
https://drive.google.com/file/d/1Jtje_VfIX6LkMumV8fs_X1TC4IcPFrcd/view?usp=drive_link
 - Complete walkthrough of all features (2:45 minutes)

## 🏗️ Architecture

### System Architecture
![Architecture Diagram](docs/diagrams/architecture.png)

This application follows a modular architecture:
- **Frontend Layer**: Responsive UI built with HTML, CSS, Tailwind
- **Backend Layer**: RESTful API with Express.js
- **Database Layer**: MongoDB for data persistence
- **External Services**: Google Maps, Weather API integration

### User Flow
![User Flow Diagram](docs/diagrams/user-flow.png)

## 📚 API Documentation

### Base URL
```
https://api.solosafe.com/v1
```

### Authentication
JWT Token-based authentication. Include token in Authorization header:
```
Authorization: Bearer {token}
```

### Key Endpoints

#### Get User Itineraries
```http
GET /api/itineraries
Authorization: Bearer {token}
```

**Response**:
```json
{
  "status": "success",
  "data": [
    {
      "id": 1,
      "destination": "Tokyo",
      "startDate": "2026-03-01",
      "endDate": "2026-03-10",
      "budget": 2000,
      "activities": []
    }
  ]
}
```

#### Create New Itinerary
```http
POST /api/itineraries
Authorization: Bearer {token}
Content-Type: application/json

{
  "destination": "Bangkok",
  "startDate": "2026-04-01",
  "endDate": "2026-04-07",
  "budget": 1500,
  "interests": ["culture", "food", "nightlife"]
}
```

#### Get Safety Alerts
```http
GET /api/safety/alerts?destination=Paris
```

#### Track Expense
```http
POST /api/expenses
Authorization: Bearer {token}
Content-Type: application/json

{
  "itineraryId": 1,
  "category": "food",
  "amount": 45.50,
  "description": "Dinner at local restaurant"
}
```

## 💻 Usage Examples

### Basic Usage - Creating Your First Trip
```bash
1. Sign up for an account
2. Click "Create New Itinerary"
3. Enter destination and dates
4. Select your interests (culture, food, adventure, etc.)
5. Review AI-generated itinerary
6. Customize and save
```

### Advanced Usage - Budget Planning
```bash
1. Navigate to Budget Tracker
2. Set total budget for trip
3. Log expenses as you travel
4. View spending breakdown by category
5. Get alerts when approaching budget limit
```

### Community Features
```bash
1. Visit Community Forum
2. Browse destinations or start new discussion
3. Share photos and tips from your travels
4. Read recommendations from experienced solo travelers
5. Connect with travelers heading to same destination
```

## 🔧 Command Reference

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server |
| `npm run build` | Build for production |
| `npm start` | Start production server |
| `npm test` | Run test suite |
| `npm run lint` | Check code quality |
| `npm run migrate` | Run database migrations |

### Available Flags
- `--port`: Specify custom port
- `--env`: Set environment (development/production)
- `--verbose`: Enable detailed logging

## 📂 Project Structure

```
solosafe/
├── README.md
├── LICENSE
├── .gitignore
├── package.json
├── .env.example
│
├── frontend/
│   ├── index.html
│   ├── styles/
│   │   ├── main.css
│   │   └── tailwind.config.js
│   ├── js/
│   │   ├── app.js
│   │   ├── api.js
│   │   └── utils.js
│   └── assets/
│       ├── images/
│       └── icons/
│
├── backend/
│   ├── server.js
│   ├── routes/
│   │   ├── itineraries.js
│   │   ├── safety.js
│   │   ├── expenses.js
│   │   └── auth.js
│   ├── controllers/
│   ├── models/
│   │   ├── User.js
│   │   ├── Itinerary.js
│   │   └── Expense.js
│   ├── middleware/
│   └── config/
│
├── docs/
│   ├── diagrams/
│   │   ├── architecture.png
│   │   └── user-flow.png
│   ├── screenshots/
│   └── api-docs.md
│
└── tests/
    ├── unit/
    └── integration/
```

## 🧪 Testing

```bash
# Run all tests
npm test

# Run specific test file
npm test -- tests/unit/itinerary.test.js

# Run with coverage report
npm test -- --coverage
```

## 🚀 Deployment

### Live Link
🔗 [Visit SOLOSAFE](https://solosafe-travel.com)

**Features**: HTTPS enabled, optimized performance, no console errors

### Deployment Steps

1. **Build the project**
   ```bash
   npm run build
   ```

2. **Deploy to Netlify/Vercel**
   - Connect your GitHub repository
   - Set environment variables
   - Deploy with one click

3. **Verify deployment**
   - Test all features
   - Check mobile responsiveness
   - Verify API connections

## 📋 Git Commit Examples

- `feat: Add AI itinerary generator`
- `feat: Implement real-time safety alerts`
- `feat: Add budget tracker with analytics`
- `fix: Resolve mobile responsiveness issues`
- `docs: Update API documentation`
- `style: Format code with Prettier`

## 🤖 AI Tools Used

This project was developed with assistance from:
- **GitHub Copilot**: Code completion, function generation, and debugging suggestions
- **ChatGPT**: Architecture planning, feature brainstorming, and documentation writing
- **Claude**: Code review and optimization suggestions

## 👥 Team Members

| Name | Role | GitHub |
|------|------|--------|
| Andre | Full Stack Developer | @andredev |
| [Andrea M Vellanikkaran] | [Frontend & UI/UX Lead] | @andreamv20 |
| [Ashlyn Biju] | [Interactivity & Functionality Lead] | @ashlyn18b |

## 📄 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

**License Summary**:
- ✅ Free for personal and commercial use
- ✅ Can modify and distribute
- ⚠️ No warranty or liability
- 📋 Include license and copyright notice

## 🤝 Contributing

Contributions welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit changes (`git commit -m 'feat: Add new feature'`)
4. Push to branch (`git push origin feature/new-feature`)
5. Open a Pull Request

## 📞 Support

- 📧 Email: support@solosafe.com
- 🐛 [Report Issues](https://github.com/username/solosafe/issues)
- 💬 [Discussions](https://github.com/username/solosafe/discussions)

## 📝 Changelog

### Version 1.0.0 (2026-02-21)
- ✨ Initial release
- ✨ Itinerary builder
- ✨ Safety dashboard
- ✨ Budget tracker
- ✨ Community features

---

Made with ❤️ for solo travelers everywhere
