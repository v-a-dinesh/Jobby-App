# Jobby App 💼

A modern job search platform built with React.js that allows users to browse, search, and filter job opportunities. This application features user authentication, profile management, and detailed job listings with a responsive design.

🔗 **Live Demo**: [https://jobbyappvad.ccbp.tech/login](https://jobbyappvad.ccbp.tech/login)

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [API Documentation](#api-documentation)
- [Routes](#routes)
- [Authentication](#authentication)
- [Components](#components)
- [Styling](#styling)
- [Testing](#testing)
- [Contributing](#contributing)

## ✨ Features

### Core Features
- **User Authentication**: Secure login system with JWT tokens
- **Job Search**: Search jobs by title with real-time filtering
- **Advanced Filters**: Filter jobs by:
  - Employment Type (Full Time, Part Time, Freelance, Internship)
  - Salary Range (Multiple brackets from 10 LPA to 70 LPA)
- **Job Details**: Comprehensive job information including:
  - Company details
  - Job description
  - Required skills
  - Life at company
  - Similar job recommendations
- **User Profile**: Display user profile information
- **Responsive Design**: Optimized for all devices (mobile, tablet, desktop)

### Additional Features
- Protected routes for authenticated users
- Loading states for better UX
- Error handling with retry options
- Clean and intuitive UI

## 🛠️ Tech Stack

- **Frontend**: React.js, React Router
- **Styling**: CSS3, Responsive Design
- **HTTP Client**: Fetch API
- **Authentication**: JWT (JSON Web Tokens)
- **Icons**: React Icons
- **Loader**: React Loader Spinner
- **Build Tool**: Create React App

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn package manager

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/v-a-dinesh/Jobby-App.git
cd Jobby-App
```

2. **Install dependencies**
```bash
npm install
```

3. **Start the development server**
```bash
npm start
```

4. **Open your browser**
Navigate to `http://localhost:3000`

### Login Credentials
```
Username: rahul
Password: rahul@2021
```

## 📁 Project Structure

```
jobby-app/
├── public/
│   ├── index.html
│   └── ...
├── src/
│   ├── components/
│   │   ├── Header/
│   │   ├── Home/
│   │   ├── Login/
│   │   ├── Jobs/
│   │   ├── JobItemDetails/
│   │   ├── NotFound/
│   │   └── ...
│   ├── App.js
│   ├── App.css
│   └── index.js
├── package.json
└── README.md
```

## 📡 API Documentation

### Base URL
```
https://apis.ccbp.in
```

### Endpoints

#### 1. **Login**
- **URL**: `/login`
- **Method**: `POST`
- **Body**:
```json
{
  "username": "rahul",
  "password": "rahul@2021"
}
```
- **Success Response**:
```json
{
  "jwt_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

#### 2. **User Profile**
- **URL**: `/profile`
- **Method**: `GET`
- **Headers**: `Authorization: Bearer {jwt_token}`
- **Response**:
```json
{
  "profile_details": {
    "name": "Rahul Attuluri",
    "profile_image_url": "https://...",
    "short_bio": "Lead Software Developer and AI-ML expert"
  }
}
```

#### 3. **Jobs List**
- **URL**: `/jobs`
- **Method**: `GET`
- **Headers**: `Authorization: Bearer {jwt_token}`
- **Query Parameters**:
  - `employment_type`: String (comma-separated values)
  - `minimum_package`: String
  - `search`: String
- **Example**: `/jobs?employment_type=FULLTIME,PARTTIME&minimum_package=1000000&search=developer`

#### 4. **Job Details**
- **URL**: `/jobs/:id`
- **Method**: `GET`
- **Headers**: `Authorization: Bearer {jwt_token}`

## 🛣️ Routes

| Route | Component | Description | Access |
|-------|-----------|-------------|--------|
| `/login` | Login | User authentication page | Public |
| `/` | Home | Landing page with navigation to jobs | Protected |
| `/jobs` | Jobs | Job listings with search and filters | Protected |
| `/jobs/:id` | JobItemDetails | Detailed view of a specific job | Protected |
| `/not-found` | NotFound | 404 error page | Public |

## 🔐 Authentication

The app uses JWT token-based authentication:

1. User logs in with credentials
2. Server returns JWT token
3. Token is stored in cookies
4. Token is sent with every API request
5. Protected routes check for valid token
6. Logout clears the token

## 🧩 Components

### Major Components

#### 1. **Header**
- Navigation bar with logo
- Links to Home and Jobs
- Logout functionality
- Responsive mobile menu

#### 2. **Login**
- Username and password inputs
- Form validation
- Error message display
- Redirect on successful login

#### 3. **Jobs**
- Profile section
- Search bar
- Filter options (Employment Type, Salary Range)
- Job cards grid
- Loading/Error/Empty states

#### 4. **JobItemDetails**
- Complete job information
- Skills required
- Life at company section
- Similar jobs
- Apply button with external link

#### 5. **Home**
- Hero section
- Call-to-action button
- Responsive background images

## 🎨 Styling

### Design System

#### Colors
- Primary: `#4f46e5`, `#6366f1`
- Background: `#000000`, `#121212`, `#202020`
- Text: `#ffffff`, `#f8fafc`, `#64748b`
- Accent: `#fbbf24`, `#ff0b37`

#### Typography
- Font Family: Roboto
- Responsive font sizes
- Clear hierarchy

#### Breakpoints
- Mobile: < 576px
- Tablet: >= 768px
- Desktop: >= 992px

## 🧪 Testing

### Test Requirements
- All routes must render correctly
- Authentication flow must work
- API calls must handle success/failure
- Responsive design on all devices

### Test IDs
- Loader: `data-testid="loader"`
- Search button: `data-testid="searchButton"`
