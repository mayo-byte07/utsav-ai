# UtsavAI - Smart Event Planning & Vendor Marketplace

An AI-powered event planning platform that uses TOPSIS and K-Means algorithms to provide intelligent vendor recommendations for events.

## Project Structure

```
utsavai/
├── utsavai-backend/          # Node.js/Express API Server
│   ├── src/
│   │   ├── @types/          # Custom type definitions
│   │   ├── config/          # Database, Redis, Passport configuration
│   │   ├── controllers/     # Request/response handlers
│   │   ├── middleware/      # Auth, error handling, rate limiting
│   │   ├── models/          # Mongoose schemas (User, Event, Vendor, Review)
│   │   ├── routes/          # API route definitions
│   │   ├── services/        # Business logic, AI algorithms
│   │   │   ├── ai/          # TOPSIS/K-Means scoring logic
│   │   │   ├── payment/     # Stripe/Razorpay integration
│   │   │   └── socket/      # WebSocket handlers
│   │   └── utils/           # Shared helpers (Logger, Mailer)
│   ├── tests/               # Jest/Supertest tests
│   └── server.ts           # Entry point
└── utsavai-frontend/         # React/Vite Frontend
    ├── src/
    │   ├── api/             # Axios instances & React Query hooks
    │   ├── components/      
    │   │   ├── ui/          # Atomic components (Shadcn/ui)
    │   │   ├── layout/      # Navbar, Sidebar, Footer
    │   │   ├── vendors/     # Vendor Cards, Filter Sidebars
    │   │   └── ai/          # AI Prompt bar, Recommendation displays
    │   ├── context/         # AuthContext, ThemeContext
    │   ├── hooks/           # Custom React hooks
    │   ├── pages/           # Page components
    │   ├── store/           # Global state (Zustand)
    │   ├── types/           # TypeScript interfaces
    │   └── utils/           # Formatters, helpers
    └── index.html
```

## Features

### Backend
- **Express.js** REST API with TypeScript
- **MongoDB** with Mongoose ODM
- **Redis** for caching AI recommendations
- **JWT** authentication with Passport.js
- **Stripe & Razorpay** payment integration
- **Socket.io** for real-time updates
- **Winston** logging
- **Rate limiting** and security middleware
- **AI Services**: TOPSIS and K-Means algorithms for vendor scoring

### Frontend
- **React 18** with TypeScript
- **Vite** for fast development
- **TailwindCSS** for styling
- **Shadcn/ui** component library
- **React Query** for data fetching
- **React Router** for navigation
- **Zustand** for state management
- **Framer Motion** for animations
- **Lucide React** for icons

## Getting Started

### Prerequisites
- Node.js 18+
- MongoDB
- Redis
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd utsavai
   ```

2. **Install backend dependencies**
   ```bash
   cd utsavai-backend
   npm install
   ```

3. **Install frontend dependencies**
   ```bash
   cd ../utsavai-frontend
   npm install
   ```

### Environment Setup

1. **Backend Environment Variables**
   ```bash
   cd utsavai-backend
   cp .env.example .env
   # Edit .env with your configuration
   ```

2. **Frontend Environment Variables**
   ```bash
   cd ../utsavai-frontend
   cp .env.example .env
   # Edit .env with your configuration
   ```

### Running the Application

1. **Start MongoDB and Redis**
   ```bash
   # Start MongoDB
   mongod
   
   # Start Redis
   redis-server
   ```

2. **Start the backend server**
   ```bash
   cd utsavai-backend
   npm run dev
   # Server runs on http://localhost:5000
   ```

3. **Start the frontend development server**
   ```bash
   cd utsavai-frontend
   npm run dev
   # Frontend runs on http://localhost:3000
   ```

## API Documentation

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `GET /api/auth/me` - Get current user

### Events
- `GET /api/events` - Get all events
- `POST /api/events` - Create new event
- `GET /api/events/:id` - Get event by ID
- `PUT /api/events/:id` - Update event
- `DELETE /api/events/:id` - Delete event

### Vendors
- `GET /api/vendors` - Get all vendors with filters
- `POST /api/vendors` - Create vendor profile
- `GET /api/vendors/:id` - Get vendor by ID
- `PUT /api/vendors/:id` - Update vendor
- `DELETE /api/vendors/:id` - Delete vendor

### AI Recommendations
- `POST /api/ai/recommendations` - Get vendor recommendations
- `POST /api/ai/analyze-event` - Analyze event with AI
- `GET /api/ai/insights` - Get AI insights

### Payments
- `POST /api/payments/create-payment-intent` - Create payment
- `POST /api/payments/confirm-payment` - Confirm payment
- `GET /api/payments/payment-history` - Get payment history

## AI Algorithm Overview

### TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)
- Multi-criteria decision-making method
- Ranks vendors based on multiple criteria (price, rating, availability, etc.)
- Provides optimal vendor recommendations

### K-Means Clustering
- Groups similar vendors together
- Helps in categorizing vendors based on services and characteristics
- Improves recommendation accuracy

## Testing

### Backend Tests
```bash
cd utsavai-backend
npm test                # Run all tests
npm run test:watch      # Run tests in watch mode
npm run test:coverage    # Run tests with coverage
```

### Frontend Tests
```bash
cd utsavai-frontend
npm test                # Run all tests
npm run test:ui         # Run tests with UI
```

## Deployment

### Backend Deployment
1. Build the TypeScript code:
   ```bash
   npm run build
   ```

2. Set production environment variables

3. Start the production server:
   ```bash
   npm start
   ```

### Frontend Deployment
1. Build the React application:
   ```bash
   npm run build
   ```

2. Deploy the `dist` folder to your hosting provider

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

For support, please email support@utsavai.com or create an issue in the repository.
