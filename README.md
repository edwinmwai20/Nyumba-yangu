# Nyumba Yangu — Kenyan Real Estate Marketplace

This is the project scaffold generated from the build spec. It mirrors the
backend (FastAPI/PostgreSQL/Celery) and frontend (React/Vite/Tailwind)
structure exactly, with stub files at every layer so the codebase is ready
to fill in feature by feature, following the phased build order below.

## Structure

```
nyumba-yangu/
├── backend/     FastAPI app (models, schemas, routers, crud, services, tasks)
├── frontend/    React + Vite + Tailwind app (pages, components, store, routes)
└── README.md
```

## Getting started

### Backend
```bash
cd backend
cp .env.example .env        # fill in real secrets
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
# once models exist:
alembic revision --autogenerate -m "init"
alembic upgrade head
uvicorn app.main:app --reload
```

Or run the full stack (API + Postgres + Redis + Celery) with:
```bash
cd backend
docker compose up --build
```

### Frontend
```bash
cd frontend
cp .env.example .env
npm install
npm run dev
```

## Build order (per spec)
1. Setup — models + migrations + seed Kenyan counties/towns + amenities
2. Auth & RBAC — registration, OTP, JWT, password reset, profile CRUD
3. Property CRUD — listings, location hierarchy, moderation status
4. Media handling — image/video upload (Cloudinary/S3)
5. Search & filters — query builder, pagination, sort, map view
6. Favorites, inquiries, reviews
7. Admin moderation panel
8. M-Pesa payments (STK push + callback)
9. Notifications (SMS/email via Celery)
10. Hardening & deployment (security review, tests, CI/CD)

## What's stubbed vs. real

- **Real, working:** directory structure, `main.py` FastAPI entrypoint,
  `requirements.txt`, Dockerfiles, `docker-compose.yml`, Vite/Tailwind/React
  entrypoints, `package.json`, `.env.example` for both apps.
- **Stubbed (comment-only placeholders to fill in):** every model, schema,
  router, crud module, service, Celery task, and every React
  page/component/store/hook — one file per item in the spec, correctly
  named and located, so you (or I) can implement them one at a time without
  restructuring later.

Next natural step: implement `app/models/user.py` + `app/models/property.py`
+ `app/db/base.py`, wire up Alembic, then build out `auth.py` end to end.
Say the word and I'll start filling these in.
# Nyumba-yangu
