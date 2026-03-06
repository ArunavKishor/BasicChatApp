# ChatApp - Project Documentation

## 📋 Table of Contents

1. [Overview](#overview)
2. [Project Structure](#project-structure)
3. [Technology Stack](#technology-stack)
4. [Getting Started](#getting-started)
5. [Frontend Setup](#frontend-setup)
6. [Backend Setup](#backend-setup)
7. [Authentication](#authentication)
8. [API Endpoints](#api-endpoints)
9. [Project Architecture](#project-architecture)
10. [Components Overview](#components-overview)
11. [Development Workflow](#development-workflow)
12. [Deployment](#deployment)
13. [Troubleshooting](#troubleshooting)

---

## Overview

**ChatApp** is a full-stack real-time chat application built with modern web technologies. It features user authentication with Google OAuth 2.0, a responsive UI with Tailwind CSS, and a robust backend API powered by Express.js and MongoDB.

### Key Features

- 🔐 User authentication (Register, Login, Google OAuth)
- 💬 Real-time chat messaging
- 👥 User profiles and contact management
- 🎨 Responsive UI with Tailwind CSS and FlyonUI components
- 🚀 RESTful API with Express.js
- 📦 MongoDB database for data persistence
- 🔒 JWT-based session management
- 📧 Email notifications via Nodemailer

---

## Project Structure

```
ChatApp/
├── client/                          # React frontend (Vite)
│   ├── public/                      # Static assets
│   ├── src/
│   │   ├── App.jsx                 # Main app component with routing
│   │   ├── main.jsx                # Entry point
│   │   ├── index.css               # Global styles
│   │   ├── assets/                 # Images, icons, media
│   │   ├── components/             # Reusable React components
│   │   │   ├── Navbar.jsx          # Navigation bar
│   │   │   └── chat/
│   │   │       ├── ChatWindow.jsx  # Chat message display
│   │   │       ├── ContactBar.jsx  # Contact list sidebar
│   │   │       └── QuickNavigation.jsx
│   │   ├── config/                 # Configuration files
│   │   │   ├── api.jsx             # API client setup (axios)
│   │   │   └── GoogleAuth.jsx      # Google OAuth configuration
│   │   └── pages/                  # Page components
│   │       ├── Home.jsx            # Landing page
│   │       ├── Login.jsx           # Login page
│   │       ├── Register.jsx        # Registration page
│   │       └── Chating.jsx         # Chat interface page
│   ├── package.json                # Frontend dependencies
│   ├── vite.config.js              # Vite configuration
│   ├── eslint.config.js            # ESLint configuration
│   └── README.md
│
├── server/                          # Express.js backend
│   ├── index.js                    # Server entry point
│   ├── src/
│   │   ├── config/
│   │   │   └── db.js               # MongoDB connection
│   │   ├── controllers/
│   │   │   └── authController.js   # Authentication logic
│   │   ├── middleware/
│   │   │   └── googleMiddleware.js # Google OAuth middleware
│   │   ├── models/
│   │   │   └── userModel.js        # User database schema
│   │   └── routers/
│   │       └── authRouter.js       # Authentication routes
│   └── package.json                # Backend dependencies
│
├── Google_Login_Guide.md           # Google OAuth setup guide
└── PROJECT_DOCUMENTATION.md        # This file
```

---

## Technology Stack

### Frontend

| Technology       | Purpose                     | Version |
| ---------------- | --------------------------- | ------- |
| React            | UI framework                | 19.2.0  |
| Vite             | Build tool & dev server     | 7.2.4   |
| Tailwind CSS     | Utility-first CSS framework | 4.1.18  |
| FlyonUI          | Component library           | 2.4.1   |
| React Router DOM | Client-side routing         | 7.13.0  |
| Axios            | HTTP client                 | 1.13.4  |
| React Hot Toast  | Notifications               | 2.6.0   |
| React Icons      | Icon library                | 5.5.0   |
| ESLint           | Code quality                | 9.39.1  |

### Backend

| Technology          | Purpose                | Version |
| ------------------- | ---------------------- | ------- |
| Express.js          | Web framework          | 4.19.2  |
| Node.js             | Runtime environment    | -       |
| MongoDB             | NoSQL database         | -       |
| Mongoose            | MongoDB ODM            | 9.1.5   |
| JWT                 | Authentication         | 9.0.3   |
| Bcrypt              | Password hashing       | 6.0.0   |
| CORS                | Cross-origin requests  | 2.8.5   |
| Nodemailer          | Email service          | 7.0.13  |
| Cloudinary          | Image hosting          | 2.9.0   |
| Google Auth Library | OAuth 2.0              | 10.5.0  |
| Multer              | File uploads           | 2.0.2   |
| Morgan              | HTTP logging           | 1.10.1  |
| Dotenv              | Environment variables  | 17.2.3  |
| Nodemon             | Dev server auto-reload | 3.1.11  |

---

## Getting Started

### Prerequisites

- **Node.js** (v14 or higher) and **npm**
- **MongoDB** (local or MongoDB Atlas cloud instance)
- **Git** for version control
- **Google Cloud Console** account (for OAuth setup)

### Initial Setup Steps

1. Clone the repository

   ```bash
   git clone <repository-url>
   cd ChatApp
   ```

2. Install frontend dependencies

   ```bash
   cd client
   npm install
   ```

3. Install backend dependencies

   ```bash
   cd ../server
   npm install
   ```

4. Configure environment variables (see sections below)

---

## Frontend Setup

### Installation

```bash
cd client
npm install
```

### Environment Variables

Create a `.env` file in the `client/` directory:

```env
VITE_GOOGLE_CLIENT_ID=your_google_client_id_here
VITE_API_URL=http://localhost:5000/api
```

### Development Server

Start the development server with hot-reload:

```bash
npm run dev
```

The app will be available at `http://localhost:5173`

### Build

Create a production build:

```bash
npm run build
```

### Preview

Preview the production build locally:

```bash
npm run preview
```

### Linting

Check code quality:

```bash
npm run lint
```

### Available Scripts

| Script            | Description              |
| ----------------- | ------------------------ |
| `npm run dev`     | Start development server |
| `npm run build`   | Build for production     |
| `npm run preview` | Preview production build |
| `npm run lint`    | Run ESLint               |

---

## Backend Setup

### Installation

```bash
cd server
npm install
```

### Environment Variables

Create a `.env` file in the `server/` directory:

```env
PORT=5000
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/chatapp
JWT_SECRET=your_jwt_secret_key_here
GOOGLE_CLIENT_ID=your_google_client_id_here
GOOGLE_CLIENT_SECRET=your_google_client_secret_here
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
NODEMAILER_EMAIL=your_email@gmail.com
NODEMAILER_PASSWORD=your_app_password_here
```

### Development Server

Start the backend server with auto-reload:

```bash
npm run dev
```

The API will be available at `http://localhost:5000`

### Production Server

Start the backend server in production:

```bash
npm start
```

### Available Scripts

| Script        | Description                             |
| ------------- | --------------------------------------- |
| `npm run dev` | Start development server (with nodemon) |
| `npm start`   | Start production server                 |

---

## Authentication

### Overview

The application uses two authentication methods:

1. **Traditional Login/Register** - Email and password-based
2. **Google OAuth 2.0** - Sign in with Google account

### JWT (JSON Web Tokens)

- Tokens are used for session management
- Stored in HTTP-only cookies (secure, not accessible via JavaScript)
- Token expiration and refresh mechanism implemented

### Google OAuth Flow

#### Setup Instructions

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project
3. Enable Google+ API and Google Identity API
4. Create OAuth 2.0 credentials (Web application)
5. Add authorized origins and redirect URIs
6. Store credentials in `.env` files

For detailed instructions, see [Google_Login_Guide.md](Google_Login_Guide.md)

#### Frontend Google Auth

- Configured in `client/src/config/GoogleAuth.jsx`
- Uses Google's official authentication library
- Handles token exchange with backend

#### Backend Google Auth

- Middleware in `server/src/middleware/googleMiddleware.js`
- Verifies Google tokens
- Creates or updates user records
- Issues JWT tokens for session management

---

## API Endpoints

### Authentication Routes

Base URL: `http://localhost:5000/auth`

| Method | Endpoint    | Description               | Auth Required |
| ------ | ----------- | ------------------------- | ------------- |
| POST   | `/register` | Register new user         | No            |
| POST   | `/login`    | Login with email/password | No            |
| POST   | `/google`   | Google OAuth login        | No            |
| POST   | `/logout`   | Logout user               | Yes           |
| GET    | `/me`       | Get current user profile  | Yes           |
| PUT    | `/profile`  | Update user profile       | Yes           |
| POST   | `/refresh`  | Refresh JWT token         | Yes           |

### Request/Response Examples

#### Register

```bash
POST /auth/register
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "securepassword123",
  "fullName": "John Doe"
}

Response:
{
  "success": true,
  "message": "User registered successfully",
  "user": {
    "id": "...",
    "email": "user@example.com",
    "fullName": "John Doe"
  }
}
```

#### Login

```bash
POST /auth/login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "securepassword123"
}

Response:
{
  "success": true,
  "message": "Login successful",
  "user": { ... }
}
```

#### Google OAuth

```bash
POST /auth/google
Content-Type: application/json

{
  "token": "google_id_token_here"
}

Response:
{
  "success": true,
  "message": "Google login successful",
  "user": { ... }
}
```

---

## Project Architecture

### Frontend Architecture

#### Component Hierarchy

```
App
├── Navbar
├── Routes
│   ├── Home (/)
│   ├── Login (/login)
│   ├── Register (/register)
│   └── Chating (/chatting)
│       ├── ChatWindow
│       ├── ContactBar
│       └── QuickNavigation
└── Toaster (notifications)
```

#### State Management

- **React Hooks** for component state (useState, useEffect)
- **Context API** for global state (if implemented)
- **Local Storage** for persistent data (tokens, preferences)

#### Styling

- **Tailwind CSS** for utility-based styling
- **FlyonUI** components for pre-built UI elements
- **Custom CSS** in `src/index.css` for global styles

### Backend Architecture

#### Request Flow

```
HTTP Request
    ↓
Express Middleware (CORS, JSON parser, Cookie parser)
    ↓
Routes (authRouter)
    ↓
Controllers (authController)
    ↓
Models (Mongoose schemas)
    ↓
MongoDB Database
    ↓
Response (JSON)
```

#### Database Schema

##### User Model

```javascript
{
  _id: ObjectId,
  email: String (unique),
  password: String (hashed),
  fullName: String,
  profilePicture: String,
  createdAt: Date,
  updatedAt: Date,
  isVerified: Boolean,
  googleId: String (optional)
}
```

---

## Components Overview

### Frontend Components

#### Navbar.jsx

- Navigation bar displayed on all pages
- Shows user profile/login options
- Responsive design

#### ChatWindow.jsx

- Displays chat messages
- Message input field
- Auto-scroll to latest messages
- Message styling and formatting

#### ContactBar.jsx

- Lists all contacts/users
- Search functionality
- User selection for chat
- Online/offline status indicators

#### QuickNavigation.jsx

- Quick access buttons
- Navigation shortcuts
- Settings/menu options

### Pages

#### Home.jsx

- Landing page
- Introduction to ChatApp
- Call-to-action buttons
- Feature highlights

#### Login.jsx

- Email/password login form
- Google OAuth button
- Link to register page
- Form validation

#### Register.jsx

- User registration form
- Email/password fields
- Form validation
- Terms and conditions

#### Chating.jsx

- Main chat interface
- Combines ChatWindow, ContactBar, QuickNavigation
- Message state management

---

## Development Workflow

### Local Development Setup

1. **Terminal 1 - Backend**

   ```bash
   cd server
   npm run dev
   ```

2. **Terminal 2 - Frontend**

   ```bash
   cd client
   npm run dev
   ```

3. **MongoDB**
   - Ensure MongoDB is running (local or Atlas connection)
   - Connection string in `.env`

### Code Structure Best Practices

#### Frontend

- Keep components small and focused
- Use descriptive component names
- Props validation with PropTypes or TypeScript
- Export components at bottom of file

#### Backend

- Separate business logic in controllers
- Use middleware for authentication/validation
- Consistent error handling
- Descriptive endpoint naming

### Git Workflow

```bash
# Create a feature branch
git checkout -b feature/feature-name

# Make changes and commit
git add .
git commit -m "Description of changes"

# Push to remote
git push origin feature/feature-name

# Create pull request on GitHub
```

---

## Deployment

### Frontend Deployment (Vercel/Netlify)

1. **Build the project**

   ```bash
   npm run build
   ```

2. **Connect to hosting platform**
   - Vercel: Sync GitHub repo
   - Netlify: Drag & drop or connect repo

3. **Set environment variables**
   - Add `VITE_GOOGLE_CLIENT_ID` in platform settings
   - Add `VITE_API_URL` (production backend URL)

4. **Deploy**
   - Automatic on push to main branch
   - Manual deployment available

### Backend Deployment (Heroku/Railway/Render)

1. **Prepare for deployment**

   ```bash
   # Ensure Procfile exists or use start script
   npm start
   ```

2. **Set environment variables**
   - All `.env` variables in platform settings
   - MongoDB connection string (Atlas recommended)
   - JWT secret
   - Credentials for third-party services

3. **Choose platform**
   - Heroku: `heroku create app-name`
   - Railway: Connect GitHub repo
   - Render: Connect GitHub repo

4. **Deploy**
   - Push to main branch (if connected)
   - Or use platform-specific deploy command

### Database Deployment

- Use **MongoDB Atlas** (recommended)
- Create cluster and connection string
- Whitelist IP addresses or allow all
- Use strong passwords

### SSL/HTTPS

- Frontend hosting provides SSL automatically
- Backend hosting provides SSL automatically
- Ensure all API calls use HTTPS in production

---

## Troubleshooting

### Common Issues

#### Frontend Issues

**Problem: Vite server not starting**

```bash
# Solution: Clear node_modules and reinstall
rm -r node_modules
npm install
npm run dev
```

**Problem: Environment variables not loading**

- Ensure `.env` file exists in client root
- Variables must start with `VITE_`
- Restart dev server after adding variables
- Check for typos in variable names

**Problem: Google OAuth not working**

- Verify `VITE_GOOGLE_CLIENT_ID` in .env
- Check Google Cloud Console OAuth settings
- Ensure localhost:5173 is in authorized origins
- Clear browser cache and cookies

**Problem: API calls returning 404**

- Verify backend server is running
- Check `VITE_API_URL` in .env
- Ensure CORS is configured correctly
- Check network tab in browser DevTools

#### Backend Issues

**Problem: MongoDB connection fails**

- Check connection string in `.env`
- Verify MongoDB is running (locally)
- Check IP whitelist in MongoDB Atlas
- Verify credentials are correct

**Problem: PORT already in use**

```bash
# Solution: Kill process or use different port
npm run dev -- --port 5001
```

**Problem: JWT token invalid/expired**

- Check JWT_SECRET in .env
- Token expiration settings in authController
- Clear cookies in browser
- Implement token refresh mechanism

**Problem: Google OAuth backend validation fails**

- Verify `GOOGLE_CLIENT_ID` and `GOOGLE_CLIENT_SECRET`
- Check Google OAuth middleware
- Ensure frontend token is sent in request
- Verify token hasn't expired

### Debugging Tips

1. **Enable logging**
   - Morgan middleware logs all requests
   - Use console.log in controllers
   - Check browser console for errors

2. **Use DevTools**
   - React Developer Tools browser extension
   - Network tab to inspect API calls
   - Application tab to check cookies/storage

3. **Check logs**
   - Terminal output for server errors
   - Browser console for client errors
   - Database logs for connection issues

4. **Database inspection**
   - Use MongoDB Compass for local database
   - Use MongoDB Atlas UI for cloud database
   - Query collections to verify data

---

## Future Enhancements

- [ ] Real-time messaging with Socket.io
- [ ] Message notifications
- [ ] User typing indicators
- [ ] Message read receipts
- [ ] Group chat functionality
- [ ] File sharing
- [ ] Voice/video calling
- [ ] Message search
- [ ] User blocking
- [ ] Admin dashboard
- [ ] Analytics and reporting
- [ ] Dark mode theme
- [ ] Mobile app (React Native)

---

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## License

This project is licensed under the ISC License - see the package.json for details.

---

## Contact & Support

**Project Author**: Arunav Kishor

For questions, issues, or suggestions, please open an issue in the repository or contact the project maintainers.

---

## Useful Resources

- [React Documentation](https://react.dev)
- [Vite Documentation](https://vitejs.dev)
- [Express.js Documentation](https://expressjs.com)
- [MongoDB Documentation](https://docs.mongodb.com)
- [Tailwind CSS Documentation](https://tailwindcss.com)
- [Google OAuth Documentation](https://developers.google.com/identity/protocols/oauth2)
- [JWT.io](https://jwt.io)

---

**Last Updated**: March 6, 2026
**Version**: 1.0
