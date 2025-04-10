
# 🎓 Classroom Management System

A comprehensive web application for managing classroom activities, student progress tracking, and educational resource sharing - designed to revolutionize how educators and students interact in digital learning environments.

## ✨ Overview

The Classroom Management System is a cutting-edge educational platform designed to streamline workflows for teachers and enhance learning experiences for students. Built with modern web technologies, it provides a seamless interface for course management, student tracking, file sharing, and academic reporting, all in a secure and intuitive environment.

## 🚀 Key Features

- **Secure Authentication** - Role-based access control with dedicated portals for teachers and students
- **Personalized Dashboards** - Data-driven insights tailored to user roles
- **Comprehensive Course Management** - Create, modify, and organize courses with intuitive tools
- **Advanced File Management** - Upload, categorize, and share educational materials with granular access controls
- **Student Progress Analytics** - Track attendance, participation, and performance with visual metrics
- **Behavioral Insights** - Monitor and analyze student behavioral patterns
- **Interactive Reporting** - Generate dynamic reports with customizable filters and export options
- **Integrated Calendar** - Schedule classes, assignments, and events with notification reminders
- **Gamified Leaderboard** - Motivate students through achievement recognition and friendly competition
- **Real-time Notifications** - Keep all users informed about important updates and deadlines

## 💻 Tech Stack

### Frontend
- **Framework**: React 18 with TypeScript for type-safe code
- **Styling**: Tailwind CSS with responsive design principles
- **Components**: Shadcn/UI for consistent, accessible UI elements
- **State Management**: React Context API for global state, TanStack Query for server state
- **Routing**: React Router v6 with dynamic route protection
- **Data Visualization**: Recharts for responsive, interactive charts

### Backend
- **Database**: Supabase PostgreSQL for relational data storage
- **Authentication**: Supabase Auth with JWT tokens and session management
- **Storage**: Supabase Storage for secure file management
- **API**: RESTful endpoints with type-safe interactions

### Development Tools
- **Build System**: Vite for fast development and optimized production builds
- **Type Checking**: TypeScript with strict mode for code quality
- **Deployment**: Vercel for continuous deployment

## 🏗️ Architecture

The application follows a modern component-based architecture with clear separation of concerns:

```
src/
├── components/         # Reusable UI components
│   ├── student/        # Student-specific components
│   ├── reports/        # Reporting and analytics components
│   ├── notifications/  # Notification system components
│   └── ui/             # Base UI components from shadcn/ui
├── context/            # React context providers for global state
├── hooks/              # Custom React hooks for shared logic
├── integrations/       # Third-party service integrations
│   └── supabase/       # Supabase client and type definitions
├── lib/                # Utility libraries
├── pages/              # Page components for main routes
├── routes.tsx          # Application routing configuration
├── types/              # TypeScript type definitions
└── utils/              # Utility functions and helpers
```

## 📊 Database Schema

The application utilizes a normalized PostgreSQL database schema through Supabase:

### Core Tables

- **students** - Comprehensive student profiles with academic metrics
  - Primary academic indicators: attendance, behavior_score, academic_score
  - Performance tracking: participation_score, leaderboard_points, cgpa

- **personality_traits** - Psychological profile data for each student
  - Five-factor model: openness, conscientiousness, extraversion, agreeableness, neuroticism

- **behavioral_incidents** - Documented behavioral events
  - Categorized by type, severity, and detailed descriptions

- **teaching_materials** - Educational resources with access controls
  - Metadata: name, description, file details
  - Access management: shared_with_all, shared_with_course

- **notifications** - System-wide messaging infrastructure
  - Targeted by recipient roles and IDs
  - Categorized by type and read status

- **course_cards** - Course information and metadata
  - Visual customization: color, thumbnail_url
  - Content organization: title, description, subject

### Relationships

- Students have personality traits (one-to-one)
- Students are associated with behavioral incidents (one-to-many)
- Courses contain teaching materials (one-to-many)
- Students have access to specific materials (many-to-many through student_materials)
- Users receive targeted notifications (one-to-many)

## 🚦 Data Flow

1. **Authentication Flow**
   - User login credentials validated against Supabase Auth
   - JWT tokens stored in secure localStorage
   - Role-based redirects to appropriate dashboards

2. **Content Delivery**
   - Teachers upload materials to Supabase Storage
   - Access controls applied based on course and student selections
   - Materials securely served to authorized students

3. **Analytics Processing**
   - Student interaction data collected and stored
   - Real-time metrics calculated and visualized
   - Trend analysis provided for academic performance

## 🛠️ Getting Started

### Prerequisites
- Node.js 16+ and npm/yarn/bun
- Supabase account and project

### Installation

1. Clone the repository
   ```bash
   git clone https://github.com/yourusername/classroom-management-system.git
   cd classroom-management-system
   ```

2. Install dependencies
   ```bash
   npm install
   # or
   yarn install
   # or
   bun install
   ```

3. Set up environment variables
   ```
   VITE_SUPABASE_URL=your_supabase_url
   VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
   ```

4. Start the development server
   ```bash
   npm run dev
   # or
   yarn dev
   # or
   bun dev
   ```

## 🌐 Deployment

The application is optimized for deployment on Vercel:

- **Build Configuration**:
  ```json
  {
    "buildCommand": "npm run build",
    "framework": "vite",
    "outputDirectory": "dist"
  }
  ```

- **Environment Variables**: Configure the same environment variables in your Vercel project settings
- **Deployment Trigger**: Automatic deployments on commits to the main branch

## 🧪 Testing Strategy

- **Unit Tests**: Component-level testing with React Testing Library
- **Integration Tests**: Cross-component interaction testing
- **E2E Tests**: Critical user flows with Cypress

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. Commit your changes
   ```bash
   git commit -m 'Add some amazing feature'
   ```
4. Push to the branch
   ```bash
   git push origin feature/amazing-feature
   ```
5. Open a Pull Request

## 🙏 Acknowledgements

- [React](https://reactjs.org/)
- [TypeScript](https://www.typescriptlang.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Shadcn/UI](https://ui.shadcn.com/)
- [Supabase](https://supabase.io/)
- [Recharts](https://recharts.org/)
- [React Router](https://reactrouter.com/)
