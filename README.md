# BizScout - AI-Powered Business Data Scraper

BizScout is an advanced data scraping solution that gathers comprehensive business information across multiple categories for any city, starting with Orlando, FL.

## Project Structure

```
bizscout/
├── backend/                  # FastAPI backend
│   ├── app/
│   │   ├── api/              # API endpoints
│   │   ├── core/             # Core settings
│   │   ├── db/               # Database models
│   │   ├── scrapers/         # Web scraping modules
│   │   └── services/         # Business logic
│   ├── Dockerfile
│   ├── requirements.txt
│   └── main.py
├── frontend/                 # React/Next.js frontend
│   ├── components/           # UI components
│   ├── pages/                # App pages
│   ├── public/               # Static assets
│   ├── styles/               # CSS styles
│   ├── Dockerfile
│   └── package.json
├── db/                       # Database scripts
│   ├── init.sql              # Schema setup
│   └── seed.sql              # Sample data
├── docker/                   # Docker configurations
│   ├── docker-compose.yml
│   └── .env.example
└── README.md
```

## Prerequisites

- Python 3.9+
- Node.js 16+
- PostgreSQL 13+
- Docker & Docker Compose (for containerized deployment)

## Local Development Setup

### Step 1: Clone the repository

```bash
git clone https://github.com/your-username/bizscout.git
cd bizscout
```

### Step 2: Set up PostgreSQL database

Create a database named `bizscout`:

```bash
psql -U postgres -c "CREATE DATABASE bizscout;"
psql -U postgres -d bizscout -f db/init.sql
psql -U postgres -d bizscout -f db/seed.sql
```

### Step 3: Set up Python backend

```bash
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt

# Create .env file
cp .env.example .env

# Start the backend server
uvicorn main:app --reload
```

### Step 4: Set up React frontend

```bash
cd ../frontend
npm install
npm run dev
```

### Step 5: Access the application

- Backend API: http://localhost:8000
- Frontend: http://localhost:3000
- API Documentation: http://localhost:8000/docs

## Docker Deployment

For containerized deployment:

```bash
cd docker
cp .env.example .env
# Edit .env with your configuration

docker-compose up -d
```

## Cloud Deployment

The provided Docker configuration can be easily deployed to any cloud provider:

- **AWS**: Use ECS or EKS with RDS for PostgreSQL
- **Google Cloud**: Use GKE with Cloud SQL
- **Azure**: Use AKS with Azure Database for PostgreSQL

Detailed deployment guides are available in the `docs/deployment` directory.

## Features

- Multi-source data collection (Yelp, Google Places, Yellow Pages)
- AI-powered data processing and enhancement
- Geocoding and location intelligence
- Business categorization and deduplication
- Interactive dashboard with data visualization
- API for integration with other applications

## License

MIT
