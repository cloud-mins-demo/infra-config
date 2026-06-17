# Project Title

RideSharingApp Infra Config (Dummy App)

## Overview

This repository contains infrastructure and deployment configuration for a dummy ride-sharing application used to test a GitHub tech stack extractor.  
It is intentionally lightweight and focuses on representing a realistic multi-stack setup (containerization, Kubernetes, and Terraform) rather than production business logic.

## Features

- Dummy infrastructure setup for a ride-sharing application
- Docker Compose support for local orchestration
- Kubernetes deployment manifest for containerized workloads
- Terraform configuration for infrastructure-as-code workflows
- Clear repository layout for automated tech stack extraction tests
- CI/CD-friendly configuration style

## Tech Stack

- Frontend:
  - React 18.2.0
- Backend:
  - Node.js 20.x
  - Python 3.11
  - FastAPI 0.111.0
- Database:
  - PostgreSQL 15
- DevOps:
  - Docker 26.x
  - Kubernetes 1.30
  - Terraform 1.8.x
  - AWS Provider 5.x
  - GitHub Actions v4 runners
- Testing:
  - Pytest 8.x
  - Jest 29.x
  - Postman v11

## Project Structure

```text
infra-config/
├── docker-compose.yml
├── k8s/
│   └── ride-deployment.yaml
└── terraform/
    └── main.tf
```

## Installation

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd infra-config
   ```

2. Install required tools:
   - Docker and Docker Compose
   - kubectl
   - Terraform
   - (Optional) AWS CLI

3. Verify tool versions:

   ```bash
   docker --version
   kubectl version --client
   terraform --version
   ```

## Usage

1. Start local services with Docker Compose:

   ```bash
   docker compose up -d
   ```

2. Apply Kubernetes resources:

   ```bash
   kubectl apply -f k8s/ride-deployment.yaml
   ```

3. Initialize and apply Terraform:

   ```bash
   cd terraform
   terraform init
   terraform plan
   terraform apply
   ```

## API Endpoints (if applicable)

If a backend service is attached to this infrastructure, common dummy endpoints may include:

- `GET /health` - Service health check
- `GET /rides` - List rides
- `POST /rides` - Create ride request
- `GET /drivers` - List available drivers

## Environment Variables

Typical variables used in a setup like this:

- `NODE_ENV` - Runtime environment (`development`, `staging`, `production`)
- `DATABASE_URL` - PostgreSQL connection string
- `POSTGRES_USER` - Database username
- `POSTGRES_PASSWORD` - Database password
- `POSTGRES_DB` - Database name
- `AWS_REGION` - Target AWS region
- `AWS_ACCESS_KEY_ID` - AWS access key
- `AWS_SECRET_ACCESS_KEY` - AWS secret key

## Testing

Suggested testing approach for this dummy app:

- Unit tests:
  - Frontend: Jest + React Testing Library
  - Backend (Node.js): Jest or Supertest
  - Backend (Python/FastAPI): Pytest
- API tests:
  - Postman/Newman collections
- Infrastructure checks:
  - `terraform validate`
  - `kubectl apply --dry-run=client -f k8s/ride-deployment.yaml`

## Roadmap

- Add Helm chart support for Kubernetes deployment
- Add reusable Terraform modules
- Add environment-specific overlays (dev/stage/prod)
- Add GitHub Actions workflow for linting and validation
- Add integration test pipeline for infrastructure changes

## License

This project is provided for educational and testing purposes.  
Use an appropriate license (for example, MIT) if distributing publicly.
