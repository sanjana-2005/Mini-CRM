# Mini-CRM Platform

A modern CRM platform with customer segmentation, campaign management, and AI-powered insights.

## Features

- 🔐 Google OAuth 2.0 Authentication
- 📊 Customer Segmentation with Dynamic Rule Builder
- 📨 Campaign Management & Delivery
- 🤖 AI-Powered Features:
  - Natural Language to Segment Rules
  - AI-Driven Message Suggestions
  - Campaign Performance Summarization
  - Smart Scheduling Suggestions
  - Auto-tagging Campaigns

## Tech Stack

- **Frontend**: Next.js 14 (App Router)
- **Backend**: Node.js with Express
- **Database**: MySQL
- **Message Broker**: Redis Streams
- **AI Integration**: OpenAI GPT-4
- **Authentication**: Google OAuth 2.0
- **Styling**: Tailwind CSS + Shadcn UI

## Architecture

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   Frontend  │     │   Backend   │     │  Database   │
│  (Next.js)  │◄───►│  (Node.js)  │◄───►│   (MySQL)   │
└─────────────┘     └─────────────┘     └─────────────┘
                           ▲
                           │
                    ┌─────────────┐
                    │    Redis    │
                    │   Streams   │
                    └─────────────┘
```

## Prerequisites

- Node.js 18+
- MySQL 8.0+
- Redis 6.0+
- Google Cloud Platform account (for OAuth)

## Setup Instructions

1. Clone the repository:
```bash
git clone <repository-url>
cd mini-crm
```

2. Install dependencies:
```bash
# Install frontend dependencies
cd frontend
npm install

# Install backend dependencies
cd ../backend
npm install
```

3. Set up environment variables:
```bash
# Frontend (.env.local)
NEXT_PUBLIC_API_URL=http://localhost:3001
NEXT_PUBLIC_GOOGLE_CLIENT_ID=your_google_client_id

# Backend (.env)
PORT=3001
MYSQL_HOST=localhost
MYSQL_USER=root
MYSQL_PASSWORD=your_password
MYSQL_DATABASE=mini_crm
REDIS_URL=redis://localhost:6379
OPENAI_API_KEY=your_openai_api_key
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
```

4. Initialize the database:
```bash
cd backend
npm run db:setup
```

5. Start the development servers:
```bash
# Start backend
cd backend
npm run dev

# Start frontend (in a new terminal)
cd frontend
npm run dev
```

## API Documentation

The API documentation is available at `http://localhost:3001/api-docs` when running the backend server.

## Project Structure

```
mini-crm/
├── frontend/                 # Next.js frontend application
│   ├── app/                 # App router pages
│   ├── components/          # Reusable components
│   ├── lib/                 # Utility functions
│   └── public/             # Static assets
│
├── backend/                 # Node.js backend application
│   ├── src/
│   │   ├── controllers/    # Route controllers
│   │   ├── models/        # Database models
│   │   ├── routes/        # API routes
│   │   ├── services/      # Business logic
│   │   └── utils/         # Utility functions
│   └── tests/             # Backend tests
│
└── docs/                   # Additional documentation
```

## Known Limitations

1. Campaign delivery is simulated with a 90% success rate
2. AI features require OpenAI API key
3. Message broker implementation uses Redis Streams for simplicity
4. Database indexes are basic and may need optimization for large datasets

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

MIT 
