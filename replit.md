# National Construction Company - Construction Contractor Website

## Overview

This is a full-stack web application for National Construction Company, a national electrical and mechanical construction contractor. The application serves as a corporate website featuring company information, services, projects, team details, and includes an AI-powered chatbot for customer inquiries. It also provides a contact form system for lead generation.

## System Architecture

### Monorepo Structure
The application uses a monorepo architecture with clear separation of concerns:
- **`client/`** - React frontend with Vite build system
- **`server/`** - Express.js backend API
- **`shared/`** - Shared TypeScript types and database schema
- **Configuration files** at root level for tooling and deployment

### Technology Stack
- **Frontend**: React 18, TypeScript, Vite, TailwindCSS, shadcn/ui components
- **Backend**: Express.js, TypeScript, Node.js
- **Database**: PostgreSQL with Drizzle ORM
- **UI Framework**: shadcn/ui (Radix UI primitives)
- **Styling**: TailwindCSS with custom design system
- **AI Integration**: OpenAI GPT-4o for chatbot functionality
- **Build Tools**: Vite for frontend, esbuild for backend
- **Deployment**: Configured for Replit with autoscale deployment

## Key Components

### Frontend Architecture
- **Single Page Application (SPA)** using React with wouter for routing
- **Component-based architecture** with reusable UI components from shadcn/ui
- **Responsive design** optimized for desktop and mobile devices
- **State management** using React Query for server state and React hooks for local state
- **Custom design system** with CSS variables for consistent theming

### Backend Architecture
- **RESTful API** built with Express.js
- **Middleware-based architecture** for request processing and logging
- **Type-safe database operations** using Drizzle ORM
- **Modular routing system** with centralized route registration
- **Environment-based configuration** for development and production

### Database Design
The application uses three main tables:
- **`users`** - User authentication (currently for future admin functionality)
- **`contact_inquiries`** - Contact form submissions with customer details
- **`chat_conversations`** - AI chatbot conversation history with session tracking

### UI Components
- **Navigation system** with smooth scrolling to sections
- **Hero section** with call-to-action buttons
- **Statistics showcase** highlighting company achievements
- **Services presentation** for electrical and mechanical contracting
- **Project portfolio** with featured case studies
- **Team profiles** and company values
- **Customer testimonials** for social proof
- **Contact form** with validation and submission handling
- **AI chatbot** with persistent conversation sessions

## Data Flow

### Contact Form Flow
1. User fills out contact form with personal and project details
2. Frontend validates form data using Zod schemas
3. Data submitted via POST to `/api/contact` endpoint
4. Backend validates and stores inquiry in PostgreSQL database
5. Success/error response sent back to frontend
6. User receives confirmation message

### Chatbot Flow
1. User opens chatbot interface and sends message
2. Frontend sends message with session ID to `/api/chat` endpoint
3. Backend calls OpenAI API with system prompt and user message
4. AI response generated using GPT-4o model
5. Conversation stored in database with session tracking
6. Response sent back to frontend and displayed to user

### Page Navigation
- **Single-page application** with smooth scrolling navigation
- **Section-based routing** using element IDs and scroll behavior
- **Mobile-responsive navigation** with hamburger menu

## External Dependencies

### Core Dependencies
- **React ecosystem**: React, React DOM, React Query for state management
- **UI framework**: Radix UI primitives, shadcn/ui components
- **Styling**: TailwindCSS, class-variance-authority for component variants
- **Database**: Drizzle ORM, @neondatabase/serverless for PostgreSQL
- **AI integration**: OpenAI SDK for chatbot functionality
- **Utilities**: date-fns, nanoid, clsx for various utilities

### Development Dependencies
- **Build tools**: Vite, esbuild, TypeScript
- **Development experience**: tsx for TypeScript execution, @replit/vite-plugin-runtime-error-modal

### External Services
- **Database**: PostgreSQL database (configured for Neon in production)
- **AI Service**: OpenAI API for GPT-4o chatbot responses
- **CDN Assets**: Font Awesome icons, Google Fonts (Inter)
- **Images**: Unsplash for project and team photos

## Deployment Strategy

### Development Environment
- **Local development**: `npm run dev` starts both frontend and backend
- **Port configuration**: Application runs on port 5000
- **Hot reload**: Vite provides instant frontend updates
- **Database**: Uses environment variable `DATABASE_URL` for connection

### Production Deployment
- **Build process**: `npm run build` creates optimized production bundles
- **Frontend**: Vite builds to `dist/public` directory
- **Backend**: esbuild bundles server to `dist/index.js`
- **Static serving**: Express serves built frontend files in production
- **Environment**: Production mode detected via `NODE_ENV=production`

### Replit Configuration
- **Modules**: nodejs-20, web, postgresql-16
- **Autoscale deployment**: Configured for automatic scaling
- **Port mapping**: Internal port 5000 mapped to external port 80
- **Workflows**: Integrated development workflow with run button

## Changelog

```
Changelog:
- June 16, 2025. Initial setup with ElectroBuild Pro branding
- June 16, 2025. Updated company name to "National Construction Company" throughout application
- June 16, 2025. Updated to focus on India's infrastructure (from America's), changed experience to 14+ years (from 25+), updated locations to Indian cities
- June 16, 2025. Major update with authentic company data from profile document:
  - Contact details: Updated email to nccsagardighi@gmail.com, phone to +91-99328-82667
  - Address: Updated to Prince Regent Tower, Raghunathganj, Murshidabad, West Bengal
  - Team: Updated leadership to reflect actual Director MD Wasim Bari (B-Tech, MEO Marine Engineering)
  - Projects: Updated to reflect actual operations in Gujarat, Andhra Pradesh, Odisha, Bihar, West Bengal
  - Services: Focused on Thermal Power Plants, Solar Plants, Oil Refinery construction and maintenance
  - AI Chatbot: Updated system prompts with accurate company information and capabilities
  - Experience: Corrected to 13+ years (established 2011), average turnover ₹4.23 crores
  - About Section: Added comprehensive company description with authentic details about establishment, leadership, and mission
  - Logo Integration: Updated navigation and footer to latest high-quality logo with consistent sizing, clean borderless design, subtle shadow effects, and hover animation for seamless webpage integration
  - Project Images: Updated Andhra Pradesh project from solar to oil refinery with authentic company photo
  - Featured Projects: Updated Gujarat from thermal power to oil refinery with Jamnagar refinery image, changed Odisha to NTPC Thermal Power Plant with authentic facility photo
  - Clients Section: Added comprehensive tabbed section with detailed client information organized by industry (Power & Energy, Oil & Gas, Construction, Technology) including full company names, descriptions, and services provided
  - UI/UX Enhancement: Implemented professional design with gradient backgrounds, hover animations, glass morphism effects, enhanced typography, and modern card layouts
  - Statistics Section: Enhanced with vibrant color-coded cards (blue, emerald, orange, purple) for better visual appeal and professional presentation
  - Hero Section Carousel: Added dynamic slideshow featuring Solar Panel Plants, Oil Refineries, and Thermal Power Plants with professional twilight refinery complex wallpaper, left/right navigation arrows, auto-rotation, slide indicators, and project-specific content
  - Navigation Enhancement: Upgraded to modern glassmorphism design with gradient logo effects, animated underlines, icon integration, enhanced CTA button with shimmer effects, and premium mobile menu with staggered animations
  - Professional Text Styling: Refined company name with sophisticated gradient typography, elegant shadow effects, subtle animations, and corporate color scheme for executive-level presentation
  - Modern Website Styling: Implemented cutting-edge CSS and JavaScript features including interactive particle background system, advanced animations (float, glow, shimmer, fade-in), enhanced hero with parallax mouse tracking, animated statistics counters with scroll triggers, glassmorphism effects, gradient text animations, and modern hover effects throughout
  - Theme Switching: Added complete light/dark theme system with toggle button, proper CSS variables, and full component support
  - Background Image Fix: Resolved blur issue in hero section by removing backdrop-blur overlay that was affecting background image clarity
  - Professional Hero Design: Refined hero section with corporate styling - removed animated sparkles, simplified typography, clean badge design for executive-level presentation, removed action buttons for streamlined focus on content, and cleaned up navigation arrows with professional styling
  - Navigation Company Name: Updated company name display to vertical layout with each word on separate lines (National, Construction, Company) while maintaining gradient effects and professional styling
  - Navigation Layout Optimization: Increased logo size to h-20 w-20, enlarged company name to text-2xl, reduced menu item spacing for compact layout, and improved visual hierarchy
  - Dark Mode Fixes: Added comprehensive dark mode support to services section and clients section with proper color schemes, backgrounds, borders, and text colors for optimal readability and visual consistency
  - Content Optimization: Removed Technology Showcase section from innovation component and orange dot decorative elements from client cards for cleaner, more professional appearance
  - Innovation Section Enhancement: Removed AI-Powered Solutions section and enlarged Upcoming Projects to full-width with enhanced styling, bigger text, centered layout, and 2-column grid for better visual impact
  - Team Section Restructure: Replaced team grid with professional director profile featuring large photo, comprehensive background, experience details, core expertise list, and enhanced dark mode support for executive-level presentation
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
Company name: National Construction Company (updated from ElectroBuild Pro)
Geographic focus: India's infrastructure development
Experience: 14+ years (updated from 25+ years)
Location: Gurgaon, Haryana (headquarters)
```