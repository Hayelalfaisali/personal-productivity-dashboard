
# Next.js Productivity Dashboard

A comprehensive, feature-rich productivity dashboard built with Next.js, React, Tailwind CSS, and shadcn/ui components. This dashboard provides a centralized hub for managing tasks, notes, analytics, and weather information.

![Dashboard Preview](https://placeholder.svg?height=400&width=800)

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Key Components](#key-components)
- [Authentication](#authentication)
- [API Routes](#api-routes)
- [Server Actions](#server-actions)
- [Styling](#styling)
- [Customization](#customization)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

### Dashboard Overview
- **Summary Cards**: Quick overview of tasks, notes, analytics, and weather
- **Responsive Design**: Fully responsive layout that works on mobile, tablet, and desktop
- **Light/Dark Mode**: Toggle between light and dark themes

### Task Management
- View tasks categorized by today, upcoming, and completed
- Task priority indicators (high, medium, low)
- Add, edit, and delete tasks
- Mark tasks as complete

### Notes System
- Create and organize notes with tags
- Search functionality for finding specific notes
- View detailed note content

### Analytics
- Productivity score tracking
- Task completion statistics
- Time tracking breakdown
- Visual charts and graphs for data visualization

### Weather Widget
- Current weather conditions
- 5-day forecast
- Location-based weather data

### User Management
- User authentication (login/signup)
- Profile management
- Account settings
- Notification preferences

## 🛠️ Tech Stack

- **Framework**: [Next.js 14](https://nextjs.org/) with App Router
- **Language**: [TypeScript](https://www.typescriptlang.org/)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **UI Components**: [shadcn/ui](https://ui.shadcn.com/)
- **Icons**: [Lucide React](https://lucide.dev/)
- **Charts**: [Recharts](https://recharts.org/)
- **Form Handling**: React Hook Form
- **State Management**: React Context API and Server Components
- **Authentication**: (Simulated, ready for integration with NextAuth.js)
- **API Routes**: Next.js API Routes for backend functionality

## 🚀 Getting Started

### Prerequisites

- Node.js 18.17 or later
- npm or yarn

### Installation

1. Clone the repository:
   \`\`\`bash
   git clone https://github.com/Hayelalfaisali/personal-productivity-dashboard.git
   cd personal-productivity-dashboard
   \`\`\`

2. Install dependencies:
   \`\`\`bash
   npm install
   # or
   yarn install
   \`\`\`

3. Run the development server:
   \`\`\`bash
   npm run dev
   # or
   yarn dev
   \`\`\`

4. Open [http://localhost:3000](http://localhost:3000) in your browser to see the dashboard.

## 📁 Project Structure

\`\`\`
nextjs-dashboard/
├── app/                    # Next.js App Router
│   ├── api/                # API routes
│   ├── analytics/          # Analytics page
│   ├── login/              # Login page
│   ├── notes/              # Notes page
│   ├── settings/           # Settings page
│   ├── signup/             # Signup page
│   ├── tasks/              # Tasks page
│   ├── actions.ts          # Server actions
│   ├── error.tsx           # Error handling
│   ├── globals.css         # Global styles
│   ├── layout.tsx          # Root layout
│   ├── loading.tsx         # Loading state
│   ├── not-found.tsx       # 404 page
│   └── page.tsx            # Home page
├── components/             # React components
│   ├── ui/                 # shadcn/ui components
│   ├── analytics-summary.tsx
│   ├── recent-notes.tsx
│   ├── task-list.tsx
│   ├── theme-toggle.tsx
│   └── weather-widget.tsx
├── hooks/                  # Custom React hooks
├── lib/                    # Utility functions
├── public/                 # Static assets
├── .eslintrc.json         # ESLint configuration
├── .gitignore             # Git ignore file
├── next.config.js         # Next.js configuration
├── package.json           # Project dependencies
├── README.md              # Project documentation
├── tailwind.config.ts     # Tailwind CSS configuration
└── tsconfig.json          # TypeScript configuration
\`\`\`

## 🧩 Key Components

### Dashboard (`app/page.tsx`)
The main dashboard page displays summary cards, recent tasks, notes, analytics, and weather information. It serves as the central hub for all productivity data.

### Task Management (`app/tasks/page.tsx`)
A dedicated page for managing tasks with filtering options for today's tasks, upcoming tasks, and completed tasks. Each task includes priority indicators and action buttons.

### Notes System (`app/notes/page.tsx`)
A comprehensive notes management system with search functionality, tags, and detailed note views. Notes are displayed in a card-based layout for easy scanning.

### Analytics (`app/analytics/page.tsx`)
Detailed analytics with charts and statistics about productivity, task completion rates, and time tracking. The page includes tabs for different types of analytics data.

### Weather Widget (`components/weather-widget.tsx`)
A weather widget that displays current conditions and a 5-day forecast. The widget can be customized to show weather for different locations.

### Settings (`app/settings/page.tsx`)
A settings page for managing user profile, account settings, and notification preferences. Changes are persisted using server actions.

## 🔐 Authentication

The dashboard includes authentication pages (login and signup) that are ready to be integrated with authentication providers like NextAuth.js. Currently, the authentication is simulated for demonstration purposes.

To implement real authentication:
1. Install NextAuth.js: `npm install next-auth`
2. Configure providers in `app/api/auth/[...nextauth]/route.ts`
3. Update the login and signup pages to use NextAuth.js

## 🌐 API Routes

The dashboard includes API routes for tasks management:

- `GET /api/tasks` - Get all tasks with optional filtering
- `POST /api/tasks` - Create a new task
- `GET /api/tasks/[id]` - Get a specific task
- `PATCH /api/tasks/[id]` - Update a task
- `DELETE /api/tasks/[id]` - Delete a task

These API routes can be extended or modified to connect to a real database.

## ⚡ Server Actions

Server actions are used for form submissions and data mutations:

- `addTask` - Add a new task
- `toggleTaskCompletion` - Toggle task completion status
- `deleteTask` - Delete a task

These actions demonstrate how to use Next.js server actions for data mutations with proper revalidation.

## 🎨 Styling

The dashboard uses Tailwind CSS for styling with shadcn/ui components. The design is fully responsive and supports both light and dark modes.

Key styling features:
- Responsive layout with mobile-first approach
- Constrained width for better readability (max-width: 1200px)
- Consistent spacing and typography
- Color scheme based on shadcn/ui defaults
- Custom card designs for different data types

## 🔧 Customization

### Theming
You can customize the theme by modifying the Tailwind CSS configuration in `tailwind.config.ts`. The dashboard uses CSS variables for theming, which can be found in `app/globals.css`.

### Adding New Features
To add new features:
1. Create new components in the `components` directory
2. Add new pages in the `app` directory
3. Update the navigation to include links to new pages
4. Extend API routes or server actions as needed

### Connecting to a Database
The dashboard is ready to be connected to a database like PostgreSQL, MySQL, or MongoDB. To do this:
1. Install the appropriate database client
2. Create database connection utilities in `lib/db.ts`
3. Update API routes and server actions to use the database

## 📦 Deployment

The dashboard can be deployed to Vercel with minimal configuration:

1. Push your code to a GitHub repository
2. Import the repository in Vercel
3. Configure environment variables if needed
4. Deploy

For other hosting providers, build the project using:
\`\`\`bash
npm run build
# or
yarn build
\`\`\`

Then serve the output from the `.next` directory.

## 👥 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

Built with ❤️ using Next.js and shadcn/ui
