# CreatoSphere - AI-Powered Creative Intelligence Hub

**Transform creative workflows with 18 specialized AI engines that generate campaign-ready ad creatives in minutes, not days.**

## Project Overview

CreatoSphere is an enterprise-grade AI-powered creative platform designed to revolutionize digital advertising workflows. The platform addresses the critical pain points faced by marketing teams, agencies, and creative professionals who struggle with time-consuming design processes, compliance issues, and the need to create multiple format variations for different platforms.

### Why CreatoSphere Exists

Traditional creative workflows require days of manual work, multiple tools, and constant back-and-forth between designers, copywriters, and compliance teams. CreatoSphere eliminates these bottlenecks by integrating 18 specialized AI engines that work together like a complete creative agency—from initial concept to compliance-validated, multi-format exports.

### Key Value Proposition

- **100x Faster Production**: Generate campaign-ready creatives in under 5 minutes
- **99% Compliance Rate**: Real-time validation against retailer guidelines prevents rejections
- **18 AI Engines**: Specialized engines handle everything from layout to typography
- **Multi-Format Export**: One design automatically optimized for Instagram, Facebook, in-store displays, and more
- **Zero Design Skills Required**: Natural language interface makes professional design accessible to everyone

## Key Features

### AI-Powered Creative Generation
- **Brand DNA Extraction**: Automatically extract brand identity, colors, and style from images
- **AutoLayout Engine**: Intelligent positioning and composition of design elements
- **AI Copywriting**: Generate compelling ad copy tailored to target audience and platform
- **Background Generation**: AI-powered background creation with style variations
- **Creative Multiverse**: Generate infinite style variations from a single design concept

### Design Intelligence
- **Attention Heatmap Simulation**: Predict where users' eyes will focus on your design
- **Performance Predictions**: AI-powered metrics forecasting for ad performance
- **Visual Auditor**: Expert-level design critique and improvement suggestions
- **Typography Harmony**: Intelligent font pairing recommendations based on design psychology
- **Color Psychology Engine**: Data-driven color recommendations for maximum impact

### Compliance & Quality Assurance
- **Auto-Compliance Validation**: Real-time checking against retailer guidelines (Amazon, Walmart, Target, etc.)
- **Safe Zones Overlay**: Visual guides for text and logo placement
- **Format-Specific Optimization**: Automatic adaptation for different ad formats and platforms

### Collaboration & Workflow
- **Real-time Collaboration**: Multiple users can work on designs simultaneously with live cursors
- **Brand Kit Management**: Centralized brand assets, colors, and guidelines
- **Template Gallery**: Reusable design templates with favorites system
- **Project Management**: Organize and manage multiple creative projects
- **Export & Publishing**: Direct export to multiple formats with one-click publishing

### Advanced Features
- **Natural Language Canvas Control**: Control design elements using conversational commands
- **Emotion-to-Design**: Convert emotional concepts into visual designs
- **Trend Forecasting**: AI-powered insights into upcoming creative trends
- **Campaign Set Creator**: Generate complete campaign variations automatically
- **Smart Resize**: Intelligent format adaptation maintaining design integrity

## Tech Stack

### Frontend
- **React 18.3** - Modern UI library with hooks and context API
- **TypeScript 5.8** - Type-safe development
- **Vite 5.4** - Fast build tool and development server
- **Tailwind CSS 3.4** - Utility-first CSS framework
- **shadcn/ui** - High-quality component library built on Radix UI
- **Fabric.js 7.0** - HTML5 canvas library for interactive design editor
- **Framer Motion 12.23** - Animation library for smooth UI transitions
- **React Router DOM 6.30** - Client-side routing
- **Zustand 5.0** - Lightweight state management
- **TanStack Query 5.83** - Server state management and caching
- **React Hook Form 7.61** - Performant form library with validation
- **Zod 3.25** - Schema validation

### Backend
- **FastAPI 0.109** - Modern, fast Python web framework
- **Python 3.x** - Backend runtime
- **Uvicorn** - ASGI server for FastAPI
- **Pydantic 2.5** - Data validation using Python type annotations
- **Beanie 1.24** - MongoDB ODM built on Motor and Pydantic
- **Motor 3.3** - Async MongoDB driver
- **Python-JOSE** - JWT token handling
- **Passlib** - Password hashing with bcrypt

### Database
- **MongoDB Atlas** - Cloud-hosted NoSQL database
- **Beanie ODM** - Object-Document Mapper for type-safe database operations

### AI / ML
- **AI Gateway Integration** - Unified interface for multiple AI models
- **Google Gemini 2.5 Flash** - Primary AI model for creative generation
- **Hugging Face Transformers** - ML model integration capabilities
- **Custom AI Engines** - 18 specialized engines for different creative tasks

### DevOps / Tools
- **Docker** - Containerization for backend services
- **Docker Compose** - Multi-container orchestration
- **Supabase** - Optional cloud backend (authentication, storage, edge functions)
- **Vite Build** - Production build optimization
- **ESLint** - Code quality and consistency
- **TypeScript ESLint** - TypeScript-specific linting rules

## System Architecture

CreatoSphere follows a **client-server architecture** with optional cloud backend support. The system is designed for flexibility, allowing deployment as a fully local solution or a hybrid cloud-local setup.

### Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                        Frontend Layer                         │
│  React + TypeScript + Vite + Tailwind CSS + Fabric.js        │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   UI Layer   │  │  State Mgmt  │  │  API Client  │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
└─────────────────────────────────────────────────────────────┘
                            │
                            │ HTTP/REST API
                            │
        ┌───────────────────┴───────────────────┐
        │                                       │
┌───────▼────────┐                    ┌────────▼────────┐
│  FastAPI       │                    │   Supabase      │
│  Backend       │                    │   (Optional)    │
│  (Local)       │                    │   Cloud         │
└───────┬────────┘                    └────────┬────────┘
        │                                       │
        │                                       │
┌───────▼────────┐                    ┌────────▼────────┐
│  MongoDB       │                    │  Supabase       │
│  Atlas         │                    │  Database       │
└────────────────┘                    └─────────────────┘
```

### Component Interaction Flow

1. **Authentication Flow**:
   - User authenticates via JWT tokens (local backend) or Supabase Auth (cloud)
   - Tokens stored securely with refresh token rotation
   - Protected routes validate tokens on each request

2. **AI Request Flow**:
   - Frontend sends creative request to backend API
   - Backend validates request and user permissions
   - Request forwarded to AI Gateway with appropriate model selection
   - Response processed and validated before returning to frontend
   - Results cached for similar requests

3. **Design Canvas Flow**:
   - Fabric.js canvas manages design state in browser
   - Changes synced to backend via REST API
   - Real-time collaboration updates via WebSocket (when using Supabase)
   - Export operations generate optimized files server-side

4. **Data Persistence**:
   - Projects, templates, and brand kits stored in MongoDB
   - User profiles and authentication data in MongoDB (local) or Supabase (cloud)
   - File uploads stored locally or in Supabase Storage

### API Architecture

The backend exposes RESTful APIs organized into logical groups:
- **Authentication APIs**: User registration, login, token refresh
- **Resource APIs**: CRUD operations for projects, templates, brand kits
- **AI APIs**: 18 specialized endpoints for different creative tasks
- **Storage APIs**: File upload and management

## Folder Structure

```
creative-intelligence-hub/
├── backend/                    # FastAPI backend application
│   ├── app/
│   │   ├── __init__.py
│   │   ├── main.py            # FastAPI application entry point
│   │   ├── config.py          # Configuration and settings
│   │   ├── database.py        # MongoDB connection management
│   │   ├── middleware/        # Custom middleware (auth, CORS)
│   │   │   └── auth.py        # JWT authentication middleware
│   │   ├── models/            # Beanie ODM models
│   │   │   ├── user.py
│   │   │   ├── profile.py
│   │   │   ├── project.py
│   │   │   ├── brand_kit.py
│   │   │   └── template.py
│   │   ├── routers/           # API route handlers
│   │   │   ├── auth.py
│   │   │   ├── profiles.py
│   │   │   ├── projects.py
│   │   │   ├── brand_kits.py
│   │   │   ├── templates.py
│   │   │   ├── storage.py
│   │   │   └── ai/            # AI-specific routers
│   │   │       ├── attention_heatmap.py
│   │   │       ├── brand_dna.py
│   │   │       ├── campaign_set.py
│   │   │       ├── canvas_control.py
│   │   │       ├── color_psychology.py
│   │   │       ├── copywriting.py
│   │   │       ├── creative_multiverse.py
│   │   │       ├── emotion_design.py
│   │   │       ├── performance_predictions.py
│   │   │       ├── trend_forecast.py
│   │   │       ├── typography_harmony.py
│   │   │       ├── visual_auditor.py
│   │   │       └── generate_background.py
│   │   ├── schemas/           # Pydantic request/response models
│   │   │   ├── user.py
│   │   │   ├── project.py
│   │   │   └── ai_schemas.py
│   │   └── services/         # Business logic layer
│   │       ├── auth_service.py
│   │       ├── ai_service.py
│   │       └── storage_service.py
│   ├── migrations/            # Database migration scripts
│   ├── Dockerfile            # Backend container definition
│   ├── docker-compose.yml    # Local development orchestration
│   ├── requirements.txt      # Python dependencies
│   └── README.md             # Backend-specific documentation
│
├── src/                       # Frontend React application
│   ├── components/           # React components
│   │   ├── ui/              # Reusable UI components (shadcn/ui)
│   │   ├── AIBackgroundGenerator.tsx
│   │   ├── AttentionHeatmap.tsx
│   │   ├── BrandDNAExtractor.tsx
│   │   ├── CopywritingEngine.tsx
│   │   ├── CreativeMultiverse.tsx
│   │   └── ...              # Other feature components
│   ├── pages/               # Page components
│   │   ├── LandingPage.tsx
│   │   ├── Dashboard.tsx
│   │   ├── CreativeBuilder.tsx
│   │   ├── Auth.tsx
│   │   └── Profile.tsx
│   ├── contexts/            # React context providers
│   │   └── AuthContext.tsx
│   ├── hooks/               # Custom React hooks
│   │   ├── useProject.ts
│   │   ├── useAICanvasControl.ts
│   │   └── ...
│   ├── lib/                 # Utility libraries
│   │   ├── api/            # API client adapters
│   │   │   ├── config.ts
│   │   │   ├── adapters/
│   │   │   │   ├── fastapi.ts
│   │   │   │   └── supabase.ts
│   │   └── utils.ts        # Helper functions
│   ├── store/               # State management (Zustand)
│   │   └── creativeStore.ts
│   ├── utils/               # Utility functions
│   │   ├── canvasUtils.ts
│   │   └── backgroundRemoval.ts
│   ├── integrations/        # Third-party integrations
│   │   └── supabase/
│   ├── App.tsx              # Root component
│   ├── main.tsx             # Application entry point
│   └── index.css            # Global styles
│
├── supabase/                 # Supabase configuration (optional)
│   ├── functions/          # Edge functions for AI operations
│   │   ├── ai-attention-heatmap/
│   │   ├── ai-brand-dna/
│   │   └── ...             # Other AI functions
│   ├── migrations/         # Database migrations
│   └── config.toml         # Supabase project configuration
│
├── public/                  # Static assets
│   ├── favicon.ico
│   └── placeholder.svg
│
├── package.json             # Frontend dependencies and scripts
├── vite.config.ts          # Vite configuration
├── tailwind.config.ts      # Tailwind CSS configuration
├── tsconfig.json           # TypeScript configuration
└── README.md               # This file
```

## Installation & Setup

### Prerequisites

- **Node.js** 18+ and npm (or yarn/pnpm)
- **Python** 3.10+ and pip
- **MongoDB Atlas** account (or local MongoDB instance)
- **Docker** and Docker Compose (optional, for containerized backend)
- **Git** for version control

### Step 1: Clone the Repository

```bash
git clone <YOUR_GIT_URL>
cd creative-intelligence-hub
```

### Step 2: Frontend Setup

```bash
# Install dependencies
npm install

# Create environment file
cp .env.example .env.local
```

Edit `.env.local` with your configuration:

```env
# Backend Configuration
VITE_BACKEND_TYPE=local  # or 'cloud' for Supabase
VITE_API_URL=http://localhost:8000/api

# Supabase Configuration (if using cloud backend)
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

### Step 3: Backend Setup

#### Option A: Using Docker (Recommended)

```bash
cd backend

# Create environment file
cp .env.example .env

# Edit .env with your MongoDB connection string and API keys
# Then start services
docker-compose up -d

# View logs
docker-compose logs -f backend
```

#### Option B: Manual Setup

```bash
cd backend

# Create virtual environment
python -m venv venv

# Activate virtual environment
# On macOS/Linux:
source venv/bin/activate
# On Windows:
venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Create environment file
cp .env.example .env
```

Edit `backend/.env`:

```env
# MongoDB Configuration
MONGODB_URL=mongodb+srv://username:password@cluster.mongodb.net/?retryWrites=true&w=majority
MONGODB_DB_NAME=creative_hub

# JWT Configuration
JWT_SECRET=your-super-secret-jwt-key-change-in-production
JWT_ALGORITHM=HS256
ACCESS_TOKEN_EXIRE_MINUTES=60
REFRESH_TOKEN_EXPIRE_DAYS=7

# AI Service Configuration
LOVABLE_API_KEY=your_ai_gateway_api_key
LOVABLE_API_URL=https://ai.gateway.lovable.dev/v1/chat/completions

# Storage Configuration
STORAGE_ROOT=./storage
PUBLIC_URL_BASE=http://localhost:8000/storage/v1/object/public/assets

# CORS Configuration
FRONTEND_URL=http://localhost:5173
CORS_ORIGINS=["http://localhost:5173","http://localhost:3000"]

# Server Configuration
DEBUG=True
HOST=0.0.0.0
PORT=8000
```

### Step 4: Start Development Servers

#### Terminal 1: Frontend

```bash
# From project root
npm run dev
```

Frontend will be available at `http://localhost:5173`

#### Terminal 2: Backend

```bash
# If using Docker
cd backend
docker-compose up -d

# If using manual setup
cd backend
source venv/bin/activate  # or venv\Scripts\activate on Windows
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

Backend API will be available at `http://localhost:8000`
- API Documentation: `http://localhost:8000/docs` (Swagger UI)
- Alternative Docs: `http://localhost:8000/redoc` (ReDoc)

### Step 5: Verify Installation

1. Visit `http://localhost:8000/health` - Should return `{"status": "healthy"}`
2. Visit `http://localhost:5173` - Frontend should load
3. Register a new account and test login functionality

## Usage Guide

### Running the Application

1. **Start Backend**: Ensure MongoDB is accessible and backend is running on port 8000
2. **Start Frontend**: Run `npm run dev` from project root
3. **Access Application**: Open `http://localhost:5173` in your browser

### Basic Workflow

1. **Registration/Login**: Create an account or sign in with existing credentials
2. **Create Project**: Start a new creative project from the dashboard
3. **Design Canvas**: Use the Fabric.js canvas to add elements, images, and text
4. **AI Features**: Access 18 AI engines from the sidebar:
   - Generate backgrounds
   - Extract brand DNA from images
   - Get AI copywriting suggestions
   - Run compliance checks
   - Generate style variations
5. **Export**: Export designs in multiple formats (PNG, JPG, PDF, SVG)

### Example API Usage

#### Authentication

```bash
# Register new user
curl -X POST http://localhost:8000/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{
    "email": "user@example.com",
    "password": "securepassword123",
    "full_name": "John Doe"
  }'

# Login
curl -X POST http://localhost:8000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{
    "email": "user@example.com",
    "password": "securepassword123"
  }'
```

#### Create Project

```bash
curl -X POST http://localhost:8000/api/projects \
  -H "Authorization: Bearer YOUR_ACCESS_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Summer Campaign 2024",
    "description": "Social media campaign for summer collection"
  }'
```

#### Use AI Copywriting Engine

```bash
curl -X POST http://localhost:8000/api/ai/copywriting \
  -H "Authorization: Bearer YOUR_ACCESS_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "product_name": "Eco-Friendly Water Bottle",
    "target_audience": "Environmentally conscious millennials",
    "tone": "friendly",
    "platform": "instagram"
  }'
```

### Screenshots

*Note: Add screenshots of key features here:*
- Dashboard view
- Design canvas with AI tools
- Brand kit management
- Export dialog
- Compliance validation results

## API Documentation

### Base URL

- **Local Development**: `http://localhost:8000/api`
- **Production**: `https://your-domain.com/api`

### Authentication

All protected endpoints require JWT Bearer token authentication:

```
Authorization: Bearer <access_token>
```

Tokens are obtained via `/api/auth/login` or `/api/auth/register` endpoints.

### Sample Endpoints

#### Authentication Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/api/auth/register` | Register new user | No |
| POST | `/api/auth/login` | Login and get tokens | No |
| POST | `/api/auth/refresh` | Refresh access token | No |
| GET | `/api/auth/me` | Get current user | Yes |
| POST | `/api/auth/logout` | Logout | Yes |

#### Project Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/projects` | List user projects | Yes |
| POST | `/api/projects` | Create new project | Yes |
| GET | `/api/projects/{id}` | Get project details | Yes |
| PUT | `/api/projects/{id}` | Update project | Yes |
| DELETE | `/api/projects/{id}` | Delete project | Yes |

#### AI Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/api/ai/attention-heatmap` | Generate attention predictions | Yes |
| POST | `/api/ai/brand-dna` | Extract brand DNA from image | Yes |
| POST | `/api/ai/campaign-set` | Generate campaign variations | Yes |
| POST | `/api/ai/canvas-control` | Natural language canvas control | Yes |
| POST | `/api/ai/color-psychology` | Get color recommendations | Yes |
| POST | `/api/ai/copywriting` | Generate ad copy | Yes |
| POST | `/api/ai/creative-multiverse` | Generate style variations | Yes |
| POST | `/api/ai/emotion-design` | Emotion-based design generation | Yes |
| POST | `/api/ai/generate-background` | AI background generation | Yes |
| POST | `/api/ai/performance-predictions` | Predict ad performance | Yes |
| POST | `/api/ai/trend-forecast` | Creative trend forecasts | Yes |
| POST | `/api/ai/typography-harmony` | Font pairing suggestions | Yes |
| POST | `/api/ai/visual-auditor` | Design feedback and critique | Yes |

### Request/Response Format

#### Example: Create Project Request

```json
POST /api/projects
Headers: {
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "Content-Type": "application/json"
}
Body: {
  "name": "Summer Campaign",
  "description": "Social media campaign"
}
```

#### Example: Create Project Response

```json
{
  "id": "507f1f77bcf86cd799439011",
  "name": "Summer Campaign",
  "description": "Social media campaign",
  "user_id": "507f191e810c19729de860ea",
  "created_at": "2024-01-15T10:30:00Z",
  "updated_at": "2024-01-15T10:30:00Z"
}
```

#### Example: AI Copywriting Request

```json
POST /api/ai/copywriting
Headers: {
  "Authorization": "Bearer <token>",
  "Content-Type": "application/json"
}
Body: {
  "product_name": "Eco-Friendly Water Bottle",
  "target_audience": "Environmentally conscious millennials",
  "tone": "friendly",
  "platform": "instagram",
  "max_length": 150
}
```

#### Example: AI Copywriting Response

```json
{
  "copy": "Stay hydrated, save the planet. Our eco-friendly water bottle keeps you refreshed while reducing plastic waste. Join the movement! 🌱💧",
  "variations": [
    "Hydrate sustainably. Every sip makes a difference. 🌍",
    "Your daily companion for a greener tomorrow. Refill, reuse, reduce."
  ],
  "hashtags": ["#EcoFriendly", "#SustainableLiving", "#GoGreen"]
}
```

Full API documentation is available at:
- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

## Environment Variables

### Frontend Environment Variables

| Variable | Description | Example Value | Required |
|----------|-------------|---------------|----------|
| `VITE_BACKEND_TYPE` | Backend type: 'local' or 'cloud' | `local` | Yes |
| `VITE_API_URL` | FastAPI backend URL | `http://localhost:8000/api` | If local |
| `VITE_SUPABASE_URL` | Supabase project URL | `https://xxx.supabase.co` | If cloud |
| `VITE_SUPABASE_ANON_KEY` | Supabase anonymous key | `eyJhbGci...` | If cloud |

### Backend Environment Variables

| Variable | Description | Example Value | Required |
|----------|-------------|---------------|----------|
| `MONGODB_URL` | MongoDB Atlas connection string | `mongodb+srv://user:pass@cluster.mongodb.net/` | Yes |
| `MONGODB_DB_NAME` | Database name | `creative_hub` | No (default: creative_hub) |
| `JWT_SECRET` | Secret key for JWT tokens | `your-super-secret-key` | Yes |
| `JWT_ALGORITHM` | JWT signing algorithm | `HS256` | No (default: HS256) |
| `ACCESS_TOKEN_EXPIRE_MINUTES` | Access token expiration | `60` | No (default: 60) |
| `REFRESH_TOKEN_EXPIRE_DAYS` | Refresh token expiration | `7` | No (default: 7) |
| `LOVABLE_API_KEY` | AI Gateway API key | `sk-xxx...` | Yes (for AI features) |
| `LOVABLE_API_URL` | AI Gateway endpoint | `https://ai.gateway.lovable.dev/v1/chat/completions` | No (has default) |
| `STORAGE_ROOT` | Local file storage path | `./storage` | No (default: ./storage) |
| `PUBLIC_URL_BASE` | Public URL for stored files | `http://localhost:8000/storage/v1/object/public/assets` | No |
| `FRONTEND_URL` | Frontend application URL | `http://localhost:5173` | No |
| `CORS_ORIGINS` | Allowed CORS origins (JSON array) | `["http://localhost:5173"]` | No |
| `DEBUG` | Enable debug mode | `True` | No (default: True) |
| `HOST` | Server host | `0.0.0.0` | No (default: 0.0.0.0) |
| `PORT` | Server port | `8000` | No (default: 8000) |

## Security Considerations

### Authentication & Authorization

- **JWT-Based Authentication**: Secure token-based authentication with access and refresh token rotation
- **Password Hashing**: All passwords hashed using bcrypt with appropriate salt rounds
- **Token Expiration**: Short-lived access tokens (60 minutes) with longer refresh tokens (7 days)
- **Protected Routes**: All sensitive endpoints require valid JWT tokens
- **Role-Based Access**: User-specific data isolation (users can only access their own projects)

### Data Validation

- **Input Validation**: All API inputs validated using Pydantic schemas on backend
- **Type Safety**: TypeScript on frontend and Pydantic on backend prevent type-related vulnerabilities
- **SQL Injection Prevention**: MongoDB ODM (Beanie) uses parameterized queries
- **XSS Prevention**: React's built-in XSS protection and proper content sanitization
- **File Upload Validation**: File type, size, and content validation before storage

### Rate Limiting & Access Control

- **API Rate Limiting**: Implemented at application level (can be enhanced with reverse proxy)
- **CORS Configuration**: Strict CORS policy allowing only configured origins
- **Environment Variable Security**: Sensitive keys stored in environment variables, never in code
- **HTTPS Enforcement**: Production deployments should enforce HTTPS only

### Additional Security Measures

- **Error Handling**: Generic error messages to prevent information leakage
- **Secure Headers**: CORS, content-type, and security headers properly configured
- **Session Management**: Secure token storage and automatic cleanup on logout
- **Data Encryption**: Sensitive data encrypted at rest (MongoDB Atlas encryption)
- **API Key Rotation**: Support for rotating AI Gateway API keys without code changes

## Performance & Scalability

### Frontend Optimizations

- **Code Splitting**: Vite automatically splits code for optimal loading
- **Lazy Loading**: React components and routes loaded on demand
- **Image Optimization**: Responsive images and lazy loading for better performance
- **State Management**: Efficient state updates using Zustand and React Query caching
- **Memoization**: React.memo and useMemo used strategically to prevent unnecessary re-renders
- **Bundle Optimization**: Tree-shaking and minification in production builds

### Backend Optimizations

- **Async Operations**: All I/O operations are asynchronous using FastAPI's async capabilities
- **Database Indexing**: MongoDB indexes on frequently queried fields (user_id, email)
- **Connection Pooling**: MongoDB connection pooling for efficient database access
- **Response Caching**: TanStack Query caches API responses on frontend
- **AI Request Batching**: Multiple AI requests can be batched when possible

### Scalability Considerations

- **Stateless Backend**: JWT-based authentication allows horizontal scaling
- **Microservices Ready**: AI endpoints can be extracted into separate services
- **Database Scaling**: MongoDB Atlas supports automatic scaling and sharding
- **CDN Integration**: Static assets can be served via CDN in production
- **Load Balancing**: Backend designed to work behind load balancers

### Caching Strategy

- **Frontend Caching**: React Query caches API responses with configurable TTL
- **Browser Caching**: Static assets cached with appropriate cache headers
- **AI Response Caching**: Similar AI requests can be cached to reduce API costs

## Testing

### Testing Strategy

The project currently focuses on manual testing and integration testing. Test coverage can be expanded with the following approach:

### Types of Tests

1. **Unit Tests** (Planned)
   - Component testing with React Testing Library
   - Service function testing with pytest
   - Utility function testing

2. **Integration Tests** (Planned)
   - API endpoint testing with FastAPI TestClient
   - Database operation testing
   - Authentication flow testing

3. **End-to-End Tests** (Planned)
   - User workflow testing with Playwright or Cypress
   - Complete creative generation flow
   - Multi-user collaboration scenarios

### Running Tests

```bash
# Frontend tests (when implemented)
npm run test

# Backend tests (when implemented)
cd backend
pytest

# E2E tests (when implemented)
npm run test:e2e
```

### Testing Tools

- **Frontend**: Jest, React Testing Library, Vitest
- **Backend**: pytest, pytest-asyncio, httpx for API testing
- **E2E**: Playwright or Cypress
- **Coverage**: Coverage.py (backend), Vitest coverage (frontend)

## Deployment

### Hosting Platform

#### Frontend Deployment

**Recommended Platforms:**
- **Vercel**: Optimized for Vite/React applications with automatic deployments
- **Netlify**: Easy deployment with continuous integration
- **AWS S3 + CloudFront**: For enterprise deployments requiring more control

**Deployment Steps (Vercel):**

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel

# Set environment variables in Vercel dashboard
# VITE_BACKEND_TYPE=cloud
# VITE_SUPABASE_URL=...
# VITE_SUPABASE_ANON_KEY=...
```

#### Backend Deployment

**Recommended Platforms:**
- **Railway**: Easy Python/FastAPI deployment with MongoDB support
- **Render**: Simple deployment with automatic scaling
- **AWS EC2/ECS**: For enterprise deployments
- **DigitalOcean App Platform**: Managed platform with Docker support

**Deployment Steps (Railway):**

```bash
# Install Railway CLI
npm i -g @railway/cli

# Login and deploy
railway login
railway init
railway up

# Set environment variables in Railway dashboard
```

### CI/CD

**GitHub Actions** (Recommended setup):

```yaml
# .github/workflows/deploy.yml
name: Deploy
on:
  push:
    branches: [main]
jobs:
  deploy-frontend:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
      - run: npm install
      - run: npm run build
      - run: vercel deploy --prod
```

### Build & Production Notes

**Frontend Build:**

```bash
# Production build
npm run build

# Preview production build locally
npm run preview
```

**Backend Production:**

```bash
# Using Docker
docker build -t creatosphere-backend ./backend
docker run -p 8000:8000 --env-file .env creatosphere-backend

# Using Uvicorn directly
uvicorn app.main:app --host 0.0.0.0 --port 8000 --workers 4
```

**Production Checklist:**
- [ ] Set `DEBUG=False` in production
- [ ] Use strong `JWT_SECRET` (generate with `openssl rand -hex 32`)
- [ ] Configure proper CORS origins
- [ ] Enable HTTPS/SSL
- [ ] Set up database backups
- [ ] Configure monitoring and logging
- [ ] Set up error tracking (Sentry, etc.)
- [ ] Configure rate limiting
- [ ] Review and update environment variables

## Limitations & Future Enhancements

### Current Limitations

1. **AI Model Dependency**: Currently relies on external AI Gateway; limited control over model selection
2. **Real-time Collaboration**: Full real-time features require Supabase cloud backend
3. **File Storage**: Local storage backend requires manual file management
4. **Testing Coverage**: Limited automated test coverage (manual testing primary)
5. **Mobile Experience**: Canvas editor optimized for desktop; mobile experience is basic
6. **Offline Support**: No offline mode for design editing
7. **Export Formats**: Limited to common formats (PNG, JPG, PDF, SVG); video export not available
8. **Multi-language Support**: UI currently English-only
9. **Analytics**: No built-in analytics or usage tracking
10. **Rate Limiting**: Basic rate limiting; can be enhanced with Redis-based solution

### Future Enhancements

#### Short-term Roadmap (1-3 months)

- **Enhanced Testing**: Comprehensive unit and integration test suite
- **Mobile Optimization**: Improved mobile canvas experience with touch gestures
- **Export Enhancements**: Additional export formats (WebP, AVIF, video)
- **Analytics Dashboard**: User analytics and project insights
- **Template Marketplace**: Community-driven template sharing
- **Advanced Collaboration**: Comments, annotations, and approval workflows

#### Medium-term Roadmap (3-6 months)

- **Multi-language Support**: i18n implementation for global users
- **Custom AI Models**: Integration with custom fine-tuned models
- **Video Ad Generation**: AI-powered video ad creation
- **Advanced Analytics**: Performance prediction accuracy improvements
- **API Rate Limiting**: Redis-based distributed rate limiting
- **Webhook Support**: Event webhooks for integrations

#### Long-term Roadmap (6-12 months)

- **White-label Solution**: Customizable branding for enterprise clients
- **Plugin System**: Third-party plugin architecture
- **Advanced AI Features**: 
  - Multi-modal AI (text-to-image, image-to-video)
  - Style transfer and neural style matching
  - Automated A/B testing
- **Enterprise Features**:
  - SSO integration (SAML, OAuth)
  - Advanced role-based access control
  - Audit logs and compliance reporting
- **Performance Optimization**:
  - Edge computing for AI operations
  - Advanced caching strategies
  - Database query optimization

## Contribution Guidelines

### How to Contribute

We welcome contributions from the community! Here's how you can help:

1. **Report Bugs**: Open an issue with detailed bug reports
2. **Suggest Features**: Share your ideas for new features
3. **Submit Pull Requests**: Fix bugs or add features
4. **Improve Documentation**: Help make the docs better
5. **Share Feedback**: Let us know what you think

### Development Workflow

1. **Fork the Repository**: Create your own fork on GitHub
2. **Create a Branch**: 
   ```bash
   git checkout -b feature/your-feature-name
   # or
   git checkout -b fix/your-bug-fix
   ```
3. **Make Changes**: Implement your feature or fix
4. **Test Your Changes**: Ensure everything works locally
5. **Commit Changes**: 
   ```bash
   git commit -m "Add: description of your changes"
   ```
6. **Push to Your Fork**: 
   ```bash
   git push origin feature/your-feature-name
   ```
7. **Open Pull Request**: Create a PR with clear description

### Branching Strategy

- **main**: Production-ready code
- **develop**: Integration branch for features
- **feature/***: New features
- **fix/***: Bug fixes
- **docs/***: Documentation updates

### Pull Request Guidelines

- **Clear Description**: Explain what and why, not just how
- **Reference Issues**: Link to related issues
- **Testing**: Describe how you tested your changes
- **Screenshots**: Include screenshots for UI changes
- **Code Quality**: Follow existing code style and patterns
- **Small PRs**: Keep PRs focused and reasonably sized

### Code Style

- **Frontend**: Follow ESLint rules, use TypeScript strictly
- **Backend**: Follow PEP 8, use type hints, async/await patterns
- **Commits**: Use conventional commit messages (Add:, Fix:, Update:, etc.)
- **Documentation**: Update README and code comments as needed

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author / Team

### Author

**Dhruv**

- **Role**: Full-Stack Developer & Project Lead
- **Responsibilities**: Architecture design, full-stack development, AI integration

### Team Members

- **Anurag** - Contributor
- **Meenakshi** - Contributor
- **Lakshmi** - Contributor
- **Aditi** - Contributor

### Contact

For questions, suggestions, or collaboration opportunities:
- **GitHub**: [Your GitHub Profile]
- **Email**: [Your Email]
- **LinkedIn**: [Your LinkedIn Profile]

---

**Built with ❤️ by the CreatoSphere team**
