# 🏥 HealthBand Frontend

A modern, responsive healthcare patient portal built with React and Vite. This application provides patients with an intuitive interface to track their health activities, manage appointments with doctors, and set health reminders.

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Project Structure](#project-structure)
- [Features Overview](#features-overview)
- [Components](#components)
- [API Integration](#api-integration)
- [Styling](#styling)
- [Building for Production](#building-for-production)
- [Troubleshooting](#troubleshooting)

## ✨ Features

### 🔐 Authentication
- User registration with form validation
- Secure login system
- JWT token-based authentication
- Automatic token management
- Protected routes and session handling

### 📊 Patient Dashboard
- **Real-time Health Tracking**
  - Steps counter with daily goals
  - Sleep hours tracking
  - Water intake monitoring (liters)
  - Calories burned tracking
- **Visual Progress Indicators**
  - Progress bars for each metric
  - Color-coded status (green for achieved, blue for in-progress)
  - Percentage completion display
- **Health Tips**
  - Random daily wellness tips
  - Motivational health messages

### 💊 Health Reminders
- **Reminder Management**
  - Create new health reminders
  - View all upcoming reminders
  - Update reminder status
  - Delete completed reminders
- **Reminder Categories**
  - Lab Tests
  - Checkups
  - Diabetes Monitoring
  - Cardio Health
  - Medication
  - Other
- **Smart Time Display**
  - Automatic time remaining calculation
  - Due date tracking
  - Status indicators

### 👨‍⚕️ Doctor Appointments
- **Doctor Directory**
  - Browse available doctors
  - View specializations
  - Check qualifications and experience
  - See ratings and consultation fees
- **Appointment Booking**
  - Select preferred doctor
  - Choose date and available time slots
  - Add appointment notes
  - Instant booking confirmation
- **Appointment Management**
  - View all scheduled appointments
  - Check appointment history
  - Cancel appointments with reason
  - Reschedule appointments
  - Real-time appointment status

### 🎯 Goals Management
- **Customizable Daily Goals**
  - Set target steps
  - Define sleep hours goal
  - Set water intake target
  - Set calorie burn goal
- **Easy Updates**
  - Quick edit modal
  - Instant goal updates
  - Persistent goal storage

## 🛠 Tech Stack

- **Framework**: React 19.2.0
- **Build Tool**: Vite 7.2.4
- **Routing**: React Router DOM 7.10.0
- **Styling**: CSS3 (Custom stylesheets)
- **HTTP Client**: Fetch API
- **State Management**: React Hooks (useState, useEffect)
- **Development**: 
  - ESLint for code linting
  - Hot Module Replacement (HMR)
  - Fast Refresh

## 📦 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v16 or higher) - [Download](https://nodejs.org/)
- **npm** or **yarn** package manager
- **Backend API** running on `http://localhost:5000`

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd hclhackethon/hclfrontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Verify backend connection**
   
   Ensure the backend API is running on `http://localhost:5000`. See backend README for setup instructions.

## ⚙️ Configuration

### API Configuration

The frontend connects to the backend API. Update the API URL if needed:

**File**: `src/utils/api.js`

```javascript
const API_URL = 'http://localhost:5000/api';
```

For production, update this to your deployed backend URL:

```javascript
const API_URL = 'https://your-api-domain.com/api';
```

### Environment Variables (Optional)

Create a `.env` file in the root directory for environment-specific configuration:

```env
VITE_API_URL=http://localhost:5000/api
```

Then update `api.js`:

```javascript
const API_URL = import.meta.env.VITE_API_URL || 'http://localhost:5000/api';
```

## 🏃‍♂️ Running the Application

### Development Mode

Start the development server with Hot Module Replacement:

```bash
npm run dev
```

The application will be available at `http://localhost:5173` (default Vite port)

### Preview Production Build

Build and preview the production version:

```bash
npm run build
npm run preview
```

### Linting

Run ESLint to check code quality:

```bash
npm run lint
```

## 📁 Project Structure

```
hclfrontend/
├── public/
│   └── vite.svg              # Vite logo
├── src/
│   ├── assets/
│   │   └── react.svg         # React logo
│   ├── components/
│   │   ├── Auth.css          # Authentication page styles
│   │   ├── Login.jsx         # Login component
│   │   ├── Register.jsx      # Registration component
│   │   ├── Dashboard.jsx     # Main dashboard component
│   │   ├── Dashboard.css     # Dashboard styles
│   │   ├── Modal.jsx         # Reusable modal component
│   │   ├── Modal.css         # Modal styles
│   │   ├── GoalsModal.jsx    # Goals editing modal
│   │   ├── GoalsModal.css    # Goals modal styles
│   │   ├── ReminderModal.jsx         # Add reminder modal
│   │   ├── ReminderModal.css         # Reminder modal styles
│   │   ├── RemindersListModal.jsx    # View reminders modal
│   │   ├── RemindersListModal.css    # Reminders list styles
│   │   ├── DoctorAppointmentModal.jsx    # Book appointment modal
│   │   ├── DoctorAppointmentModal.css    # Appointment modal styles
│   │   ├── MyAppointmentsModal.jsx       # View appointments modal
│   │   └── MyAppointmentsModal.css       # Appointments list styles
│   ├── utils/
│   │   └── api.js            # API utility functions
│   ├── App.jsx               # Main app component with routing
│   ├── App.css               # App-level styles
│   ├── main.jsx             # Application entry point
│   └── index.css            # Global styles
├── node_modules/            # Dependencies
├── .gitignore              # Git ignore rules
├── eslint.config.js        # ESLint configuration
├── index.html              # HTML entry point
├── package.json            # Project dependencies and scripts
├── package-lock.json       # Locked dependency versions
├── README.md               # This file
└── vite.config.js         # Vite configuration
```

## 🎨 Features Overview

### Authentication Flow

1. **Home Page** (`/`)
   - Welcome screen with Login/Register options
   - Auto-redirects to dashboard if already logged in

2. **Registration** (`/register`)
   - Username, name, email, and password fields
   - Form validation
   - Automatic login after successful registration
   - Token storage in localStorage

3. **Login** (`/login`)
   - Email and password authentication
   - JWT token retrieval
   - Redirect to dashboard on success

### Dashboard Features

#### Activity Cards
- **Steps**: Track daily walking/running
- **Sleep**: Monitor sleep hours
- **Water**: Track hydration
- **Calories**: Log calories burned

Each card displays:
- Current progress
- Goal target
- Progress bar
- Percentage completion
- Color-coded status

#### Action Buttons
- 📝 **Add Reminder**: Create new health reminders
- 🔔 **View Reminders**: See all reminders
- 👨‍⚕️ **Book Appointment**: Schedule doctor visits
- 📅 **My Appointments**: View appointment history
- 🎯 **Update Goals**: Modify daily targets

#### Health Tips Section
- Displays random wellness tips
- Changes on each dashboard refresh
- Provides health advice and motivation

## 🧩 Components

### Core Components

#### `Login.jsx`
- Email/password form
- Form validation
- API integration for authentication
- Token management
- Navigation after login

#### `Register.jsx`
- User registration form
- Input validation
- Account creation
- Automatic login post-registration

#### `Dashboard.jsx`
- Main patient dashboard
- Fetches and displays health data
- Activity tracking cards
- Health tips display
- Modal management for all features
- Real-time data updates

### Modal Components

#### `GoalsModal.jsx`
- Edit daily health goals
- Input fields for all metrics
- Form validation
- API update integration

#### `ReminderModal.jsx`
- Create new reminders
- Category selection
- Date/time picker
- Notes field
- Submit functionality

#### `RemindersListModal.jsx`
- Display all reminders
- Category badges
- Time remaining display
- Update/delete actions
- Status indicators

#### `DoctorAppointmentModal.jsx`
- Browse doctors list
- View doctor details
- Select date and time slot
- Book appointments
- Confirmation messages

#### `MyAppointmentsModal.jsx`
- List all appointments
- Appointment details
- Status indicators
- Cancel functionality
- Reschedule option

#### `Modal.jsx`
- Reusable modal wrapper
- Close functionality
- Backdrop click handling
- Responsive design

## 🔌 API Integration

### API Utility (`src/utils/api.js`)

```javascript
// Base URL configuration
const API_URL = 'http://localhost:5000/api';

// Get auth token
const getAuthHeaders = () => ({
  'Content-Type': 'application/json',
  'Authorization': `Bearer ${localStorage.getItem('token')}`
});

// API functions
- register(userData)
- login(credentials)
- getDashboard()
- updateGoals(goals)
- addReminder(reminder)
- getReminders()
- updateReminder(id, data)
- deleteReminder(id)
- getDoctors()
- getDoctorAvailability(doctorId, date)
- bookAppointment(appointmentData)
- getMyAppointments()
- cancelAppointment(appointmentId, reason)
- rescheduleAppointment(appointmentId, data)
```

### Token Management

- Stored in `localStorage` with key `'token'`
- Automatically included in all protected API calls
- Cleared on logout
- Validated on each request

## 🎨 Styling

### Design Philosophy
- **Modern**: Clean, contemporary UI design
- **Responsive**: Works on desktop, tablet, and mobile
- **Intuitive**: User-friendly interface
- **Accessible**: Clear contrast and readable fonts

### Color Scheme
- **Primary**: Blue (#007bff)
- **Success**: Green (#28a745)
- **Warning**: Orange (#ff9800)
- **Danger**: Red (#dc3545)
- **Neutral**: Gray shades for backgrounds

### CSS Organization
- Component-specific CSS files
- Global styles in `index.css`
- Consistent naming conventions
- Modular and maintainable

## 🏗 Building for Production

### Build the Application

```bash
npm run build
```

This creates an optimized production build in the `dist/` folder.

### Build Output

```
dist/
├── assets/
│   ├── index.[hash].js      # Optimized JavaScript
│   ├── index.[hash].css     # Optimized CSS
│   └── [other assets]
└── index.html               # Entry HTML
```

### Deployment Options

**Static Hosting (Recommended)**
- Vercel
- Netlify
- GitHub Pages
- AWS S3 + CloudFront
- Azure Static Web Apps

**Deploy Steps** (Example: Vercel)

1. Install Vercel CLI:
   ```bash
   npm install -g vercel
   ```

2. Deploy:
   ```bash
   vercel
   ```

3. Follow prompts to complete deployment

**Environment Configuration for Production**

Update API URL in `src/utils/api.js` to point to your production backend:

```javascript
const API_URL = 'https://your-production-api.com/api';
```

## 🐛 Troubleshooting

### Common Issues

**Issue**: Cannot connect to backend API
- **Solution**: Ensure backend server is running on `http://localhost:5000`
- Check CORS settings in backend
- Verify API URL in `src/utils/api.js`

**Issue**: 401 Unauthorized errors
- **Solution**: 
  - Check if token exists in localStorage
  - Token might be expired (re-login)
  - Verify Authorization header format

**Issue**: White screen on startup
- **Solution**:
  - Check browser console for errors
  - Verify all dependencies are installed (`npm install`)
  - Clear browser cache

**Issue**: Styles not loading
- **Solution**:
  - Check CSS import statements
  - Clear Vite cache: `rm -rf node_modules/.vite`
  - Restart dev server

**Issue**: Modal not closing
- **Solution**:
  - Check modal state management
  - Verify close button onClick handlers
  - Check for JavaScript errors in console

### Debug Mode

Enable debug logs by adding to `src/utils/api.js`:

```javascript
const DEBUG = true;

const api = async (endpoint, options = {}) => {
  if (DEBUG) console.log('API Call:', endpoint, options);
  // ... rest of code
};
```

## 📜 Available Scripts

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview

# Run linter
npm run lint

# Install dependencies
npm install
```

## 🔒 Security Considerations

- JWT tokens stored in localStorage (consider httpOnly cookies for production)
- All sensitive operations require authentication
- Input validation on forms
- XSS protection through React's built-in escaping
- CORS configured properly in backend

## 🚀 Performance Optimizations

- Vite's fast HMR for instant updates
- Code splitting with React Router
- Optimized production builds
- Lazy loading for modal components (can be implemented)
- Minimal bundle size

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📞 Support

For issues, questions, or suggestions:
- Create an issue in the repository
- Contact the development team
- Check backend API documentation

## 🎯 Future Enhancements

- [ ] TypeScript migration
- [ ] Progressive Web App (PWA) support
- [ ] Dark mode theme
- [ ] Multi-language support
- [ ] Real-time notifications
- [ ] Health data visualization charts
- [ ] Export health reports as PDF
- [ ] Integration with fitness trackers
- [ ] Video consultation feature
- [ ] Prescription management

## 📄 License

This project is licensed under the ISC License.

## 🎉 Acknowledgments

- Built for HCL Hackathon
- Designed with patient experience in mind
- Focused on simplicity and usability
- Powered by React and Vite

---

**Status**: ✅ Production Ready

**Version**: 0.0.0

**Last Updated**: December 2024

Made with ❤️ for better healthcare access
