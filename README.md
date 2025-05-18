# BizScout

<p align="center">
  <img src="docs/assets/logo.png" alt="BizScout Logo" width="200"/>
</p>

<p align="center">
  <strong>AI-Powered Business Data Collection</strong>
</p>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#screenshots">Screenshots</a> •
  <a href="#tech-stack">Tech Stack</a> •
  <a href="#installation">Installation</a> •
  <a href="#api">API</a> •
  <a href="#deployment">Deployment</a> •
  <a href="#contributing">Contributing</a> •
  <a href="#license">License</a>
</p>

<p align="center">
  <img src="https://img.shields.io/github/license/yourusername/bizscout" alt="License">
  <img src="https://img.shields.io/github/v/release/yourusername/bizscout" alt="Version">
  <img src="https://img.shields.io/github/workflow/status/yourusername/bizscout/CI" alt="Build Status">
</p>

BizScout is an advanced web scraping solution that gathers comprehensive business data across multiple categories for any city, starting with Orlando, FL. It combines AI-powered data collection with powerful visualization tools to help users discover and analyze local businesses.

## Features

- **Multi-Source Data Collection**: Scrape business data from Yelp, Google Places, Yellow Pages, and more
- **AI-Enhanced Processing**: Clean, deduplicate, and enrich business data using AI
- **Geocoding & Location Intelligence**: Convert addresses to precise geographical coordinates
- **Interactive Dashboard**: Monitor scraping jobs and explore collected data
- **Category Classification**: Auto-categorize businesses using NLP
- **Beautiful Visualizations**: Visualize business density and distribution on interactive maps
- **RESTful API**: Integrate with other applications using the comprehensive API
- **Database Integration**: Store data in PostgreSQL with PostGIS for spatial queries

## Screenshots

<p align="center">
  <img src="docs/assets/dashboard.png" alt="Dashboard" width="45%"/>
  &nbsp; &nbsp;
  <img src="docs/assets/map-view.png" alt="Map View" width="45%"/>
</p>
<p align="center">
  <img src="docs/assets/business-list.png" alt="Business List" width="45%"/>
  &nbsp; &nbsp;
  <img src="docs/assets/scraping-job.png" alt="Scraping Job" width="45%"/>
</p>

## Tech Stack

### Backend
- **FastAPI**: High-performance API framework
- **PostgreSQL** with **PostGIS**: Spatial database
- **SQLAlchemy**: ORM for database operations
- **Celery**: Distributed task queue
- **BeautifulSoup4** & **HTTPX**: Web scraping
- **Redis**: Caching and message broker

### Frontend
- **React** with **Next.js**: UI framework
- **MaterialUI**: Component library
- **Leaflet**: Interactive maps
- **Chart.js**: Data visualization
- **React Query**: Data fetching and caching

### DevOps
- **Docker** & **Docker Compose**: Containerization
- **GitHub Actions**: CI/CD
- **Prometheus** & **Grafana**: Monitoring

## Installation

### Prerequisites

- Python 3.9+
- Node.js 16+
- PostgreSQL 13+ with PostGIS extension
- Redis (optional, for background tasks)

### Local Development Setup

1. **Clone the repository**

```bash
git clone https://github.com/totallyesteban/bizscout.git
cd bizscout
```

2. **Backend setup**

```bash
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env  # Configure your environment variables
```

3. **Database setup**

```bash
# PostgreSQL with PostGIS must be running
psql -U postgres -d bizscout -f db/init.sql
psql -U postgres -d bizscout -f db/seed.sql
```

4. **Start backend server**

```bash
cd backend
uvicorn main:app --reload
```

5. **Frontend setup**

```bash
cd frontend
npm install
npm run dev
```

The application will be available at:
- Frontend: http://localhost:3000
- Backend API: http://localhost:8000
- API Documentation: http://localhost:8000/docs

### Docker Setup

For a containerized setup:

```bash
docker-compose up -d
```

## API

BizScout provides a comprehensive API for interacting with the application:

### Authentication

```
POST /api/v1/auth/login
POST /api/v1/auth/register
```

### Scraping Jobs

```
GET /api/v1/jobs/
POST /api/v1/jobs/
GET /api/v1/jobs/{job_id}
POST /api/v1/jobs/{job_id}/cancel
POST /api/v1/jobs/{job_id}/retry
```

### Businesses

```
GET /api/v1/businesses/
POST /api/v1/businesses/
GET /api/v1/businesses/{business_id}
PUT /api/v1/businesses/{business_id}
DELETE /api/v1/businesses/{business_id}
```

See [API Documentation](docs/api/README.md) for complete details.

## Deployment

### Docker Deployment

The easiest way to deploy BizScout is using Docker:

```bash
# Clone the repository
git clone https://github.com/yourusername/bizscout.git
cd bizscout/docker

# Configure environment
cp .env.example .env
nano .env  # Edit your configuration

# Deploy
docker-compose up -d
```

### Cloud Deployment

BizScout can be deployed to AWS, Google Cloud, or Azure. See [deployment documentation](docs/deployment/README.md) for detailed guides.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Please ensure your code adheres to our coding standards and includes appropriate tests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [Yelp Fusion API](https://www.yelp.com/developers/documentation/v3)
- [Google Places API](https://developers.google.com/maps/documentation/places/web-service/overview)
- [OpenStreetMap](https://www.openstreetmap.org)
- All contributors who have helped this project grow

---

<p align="center">
  Made with ❤️ by Your Name
</p>
