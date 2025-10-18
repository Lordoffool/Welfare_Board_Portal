# Welfare Board Portal

A comprehensive web application for managing and showcasing student welfare board activities, clubs, events, and resources.

## 📋 Overview

The Welfare Board Portal is a full-stack web application built to provide a centralized platform for student welfare activities. It features an admin panel for content management and a responsive frontend for end-users to explore clubs, events, resources, and connect with counselors.

## ✨ Features

- **Club Management**: Browse and manage student clubs with detailed information
- **Event Management**: View and manage upcoming events and activities
- **Admin Panel**: AdminJS-powered dashboard for easy content management
- **User Authentication**: Secure login and authentication system
- **Contact Management**: Store and manage contact inquiries
- **Resource Library**: Access to resources and student welfare information
- **Counselor Directory**: Directory of available counselors
- **Food Court Information**: Information about campus food facilities
- **Responsive Design**: Mobile-friendly interface with Tailwind CSS
- **File Upload**: Support for image and document uploads

## 🏗️ Architecture

This is a **full-stack MERN-like application** with the following structure:

```
Welfare_Board_Portal/
├── backend/          # Node.js + Express backend
└── frontend/         # React.js frontend
```

### Backend Stack
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB with Mongoose ODM
- **Admin Panel**: AdminJS
- **Authentication**: bcrypt for password hashing
- **Session Management**: Express Session with MongoDB Store
- **File Upload**: Multer
- **CORS**: Enabled for frontend communication

### Frontend Stack
- **Framework**: React.js 18
- **Styling**: Tailwind CSS
- **Routing**: React Router DOM v6
- **HTTP Client**: Axios
- **Animations**: Animate.css, React Animate On Scroll
- **Carousel**: React Responsive Carousel
- **Icons**: React Icons

## 📁 Project Structure

### Backend (`/backend`)

```
backend/
├── controllers/           # Business logic controllers
│   ├── auth.controller.js
│   ├── club.controller.js
│   ├── contact.controller.js
│   ├── event.controller.js
│   ├── homePage.controller.js
│   └── upload.controller.js
├── models/               # MongoDB schemas
│   ├── aboutUs.js
│   ├── clubMain.js
│   ├── contact.js
│   ├── event.js
│   ├── facilities.js
│   ├── general.js
│   └── teamMember.js
├── routes/               # API endpoints
│   ├── auth.routes.js
│   ├── upload.route.js
│   └── user.routes.js
├── views/                # EJS templates
│   ├── index.ejs
│   └── login.ejs
├── admin_panel/          # AdminJS configuration
│   └── admin-config.js
├── docs/                 # Documentation
├── index.js              # Entry point
├── package.json          # Dependencies
├── Dockerfile            # Docker configuration
└── docker-compose.yml    # Docker Compose setup
```

### Frontend (`/frontend`)

```
frontend/
├── src/
│   ├── components/       # Reusable React components
│   │   ├── AllClubsHeroSection.js
│   │   ├── ClubCard.js
│   │   ├── Event.js
│   │   ├── Footer.js
│   │   ├── Header.js
│   │   ├── HeroSection.js
│   │   ├── Layout.js
│   │   ├── RoundedDiv.js
│   │   └── ZigZagLine.js
│   ├── pages/            # Page components
│   │   ├── AllClubsPage.js
│   │   ├── ClubPage.js
│   │   ├── ContactsPage.js
│   │   ├── Counsellors.js
│   │   ├── EventPage.js
│   │   ├── FoodCourt.js
│   │   ├── HomePage.js
│   │   └── SWB.js
│   ├── hooks/            # Custom React hooks
│   │   ├── useEventPageData.js
│   │   ├── useHomePageData.js
│   │   ├── useRoundedStyle.js
│   │   └── useScrollDirection.js
│   ├── assets/           # Images and PDFs
│   │   ├── images/
│   │   └── pdfs/
│   ├── App.js            # Main App component
│   ├── index.js          # Entry point
│   ├── index.css         # Global styles
│   └── setupTests.js     # Test configuration
├── public/               # Static assets
│   ├── index.html
│   ├── manifest.json
│   ├── robots.txt
│   └── images/
├── package.json          # Dependencies
├── tailwind.config.js    # Tailwind CSS configuration
├── Dockerfile            # Docker configuration
├── docker-compose.yml    # Docker Compose setup
└── .env                  # Environment variables (gitignored)
```

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or cloud instance)
- npm or yarn package manager

### Installation

#### 1. Clone the Repository
```bash
git clone https://github.com/Lordoffool/Welfare_Board_Portal.git
cd Welfare_Board_Portal
```

#### 2. Setup Backend

```bash
cd backend
npm install
```

Create a `.env` file in the backend directory:
```env
PORT=8000
MONGO_URI=mongodb://localhost:27017/welfare-board
NODE_ENV=development
```

#### 3. Setup Frontend

```bash
cd ../frontend
npm install
```

Create a `.env` file in the frontend directory:
```env
REACT_APP_BASEURL=/welfare-board
```

### Running the Application

#### Development Mode

**Terminal 1 - Backend:**
```bash
cd backend
npm start
```
The backend will start on `http://localhost:8000`

**Terminal 2 - Frontend:**
```bash
cd frontend
npm start
```
The frontend will start on `http://localhost:3000`

#### Production Build

**Build Frontend:**
```bash
cd frontend
npm run build
```

## 🐳 Docker Setup

### Using Docker Compose

```bash
# From project root
docker-compose -f backend/docker-compose.yml up
docker-compose -f frontend/docker-compose.yml up
```

Or build individual Docker images:

```bash
# Build Backend
cd backend
docker build -t welfare-board-backend .
docker run -p 8000:8000 welfare-board-backend

# Build Frontend
cd frontend
docker build -t welfare-board-frontend .
docker run -p 3000:3000 welfare-board-frontend
```

## 🔌 API Endpoints

### Authentication Routes
- `POST /image/login` - User login
- `POST /image/logout` - User logout

### User Routes
- `GET /` - Get home page data
- `GET /clubs` - Get all clubs
- `GET /club/:name` - Get specific club details
- `GET /events` - Get all events
- `GET /event/:id` - Get specific event details
- `POST /contacts` - Submit contact form
- `GET /counsellors` - Get counselor information
- `GET /resources` - Get resource information
- `GET /facilities` - Get facility information

### Upload Routes
- `POST /upload` - Upload images/files
- `GET /upload/:id` - Retrieve uploaded file

### Admin Panel
- Access AdminJS dashboard at `/admin`

## 📊 Database Models

- **About Us** (`aboutUs.js`) - Organization information
- **Clubs** (`clubMain.js`) - Club details and metadata
- **Contacts** (`contact.js`) - Contact form submissions
- **Events** (`event.js`) - Event information and schedules
- **Facilities** (`facilities.js`) - Campus facility information
- **General** (`general.js`) - General website configuration
- **Team Members** (`teamMember.js`) - Staff and team information

## 🎨 Frontend Pages

- **Home** - Landing page with overview
- **All Clubs** - Browse all student clubs
- **Club Details** - Individual club information
- **Events** - Upcoming events and activities
- **Event Details** - Detailed event information
- **Contacts** - Contact form and information
- **Counselors** - Counselor directory
- **Resources** - Student welfare resources (SWB)
- **Food Court** - Campus food court information

## 🔐 Authentication

- Password hashing with bcrypt
- Session-based authentication
- MongoDB session store for persistence
- Protected routes for admin functionality

## 📝 Environment Variables

### Backend (.env)
```env
PORT=8000
MONGO_URI=mongodb://localhost:27017/welfare-board
NODE_ENV=development
```

### Frontend (.env)
```env
REACT_APP_BASEURL=/welfare-board
```

## 📦 Key Dependencies

### Backend
- `express` - Web framework
- `mongoose` - MongoDB ORM
- `adminjs` - Admin panel
- `bcrypt` - Password hashing
- `multer` - File uploads
- `cors` - Cross-origin resource sharing
- `express-session` - Session management

### Frontend
- `react` - UI library
- `react-router-dom` - Routing
- `tailwindcss` - Styling
- `axios` - HTTP client
- `react-icons` - Icon library
- `react-responsive-carousel` - Carousel component
- `animate.css` - Animation effects

## 🔄 GitHub Workflows

The project includes CI/CD workflows for automated deployment:
- `.github/workflows/deploy-backend.yml` - Backend deployment
- `.github/workflows/deploy-frontend.yml` - Frontend deployment
- `.github/workflows/deploy.yml` - Main deployment workflow

## 📖 Documentation

Additional documentation is available in the `backend/docs/` directory:
- `overview.md` - Architecture overview
- `api-reference.md` - API endpoint reference
- `database.md` - Database schema documentation
- `structure.md` - Project structure details
- `logic-flow.md` - Business logic flow
- `deployment.md` - Deployment guidelines

## 🤝 Contributing

1. Create a feature branch (`git checkout -b feature/AmazingFeature`)
2. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
3. Push to the branch (`git push origin feature/AmazingFeature`)
4. Open a Pull Request

## 📄 License

This project is licensed under the ISC License.

## 👨‍💻 Author

**Lordoffool**

## 📧 Support

For support, please open an issue in the GitHub repository or contact the development team.

---

**Last Updated:** October 2025
