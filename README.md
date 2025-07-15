# RemixRelay

A monorepo for the RemixRelay project, combining Next.js, FastAPI, and AI utilities for video processing and clip generation.

## Project Structure

```
remixrelay/
├── apps/
│   ├── frontend/     # Next.js 14 (React Server Components)
│   └── backend/      # FastAPI + Celery workers
├── packages/
│   ├── shared/       # TypeScript utils shared front/back
│   └── ai-utils/     # Python lib: transcripts, clip finder, etc.
├── docker/           # Compose files for local stack
└── .github/          # CI actions
```

## Prerequisites

- Node.js 22.x
- Python 3.13
- Poetry
- Docker & Docker Compose
- pnpm (recommended)

## Development Setup

1. Install dependencies:
   ```bash
   # Install Node.js dependencies
   pnpm install

   # Install Python dependencies
   cd apps/backend && poetry install
   cd ../../packages/ai-utils && poetry install
   ```

2. Start local services:
   ```bash
   cd docker && docker-compose up -d
   ```

3. Start development servers:
   ```bash
   # Start all services
   pnpm dev

   # Or start individual services
   pnpm --filter frontend dev
   cd apps/backend && poetry run uvicorn remixrelay_backend.main:app --reload
   ```

## License

Private - All Rights Reserved
