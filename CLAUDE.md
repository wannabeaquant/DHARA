# DHARA / SimhasthaFlow

## What This Is
Smart crowd management and navigation system for large-scale religious gatherings (Simhastha Kumbh Mela, Ujjain).
Hackathon project. FastAPI backend with real-time WebSocket crowd monitoring, emergency response, AI pathfinding.

## Stack
- Python 3.8+ / FastAPI
- SQLite (simhasthaflow.db — auto-created, delete to reset)
- SQLAlchemy ORM
- JWT authentication (role-based: admin, security, medical, pilgrim)
- WebSocket (real-time crowd updates every 30s)
- Pydantic schemas

## Commands
```powershell
# Activate venv
.\venv\Scripts\Activate.ps1

pip install -r requirements.txt

# Run (3 options)
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
python -m app.main
python app/main.py
```
- API docs: http://localhost:8000/docs
- Default admin: username=admin / password=admin123

## Architecture
```
app/
  core/config.py              # Config
  database/
    database.py               # DB connection
    seed_data.py              # Mock data (55+ scenarios)
  models/
    database_models.py        # SQLAlchemy models
    schemas.py                # Pydantic schemas
  routers/
    auth.py                   # /api/v1/auth/*
    routes.py                 # /api/v1/routes/*
    weather.py                # /api/v1/weather/*
    crowd.py                  # /api/v1/crowd/*
    zones.py                  # /api/v1/zones/*
    emergency.py              # /api/v1/emergency/*
  websocket/crowd_updates.py  # WebSocket handler
  main.py                     # FastAPI app
```

## GitHub
https://github.com/wannabeaquant/DHARA
