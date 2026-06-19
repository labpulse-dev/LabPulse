# LabPulse

A homelab infrastructure monitoring dashboard, built collaboratively as a portfolio project by Computer Systems Technician graduates.

## What This Is

LabPulse lets you add devices to an inventory, check whether they're online, and view their status from a central dashboard. Think a simplified mix of Uptime Kuma, Grafana, and NetBox, built from scratch as a learning and portfolio project.

## Status

🚧 Early setup. Infrastructure and CI/CD scaffolding is in place. Backend and frontend development starting soon.

## MVP Scope (Phase 1)

- User login
- Add devices to an inventory
- View devices on a dashboard
- Ping devices and show online/offline status
- Store device data in a database
- Run fully in Docker
- Deploy publicly to the cloud

Everything beyond this (CPU/RAM graphs, alerts, Docker container monitoring, network discovery) is a Phase 2 stretch goal and comes after the MVP works end to end.

## Tech Stack

| Layer | Choice |
|---|---|
| Backend | Flask (Python) |
| Frontend | HTML / CSS / JavaScript |
| Database | SQLite locally, PostgreSQL in production |
| Infrastructure | Docker Compose |
| CI/CD | GitHub Actions |
| Hosting | TBD (cloud free tier) |

## Team Roles

| Role | Owns |
|---|---|
| Infrastructure / DevOps | Docker Compose, CI/CD, branch protection, deployment |
| Backend / API | Flask app, REST endpoints, auth, ping logic |
| Frontend / UI | Dashboard, device pages, login page, API integration |

## Getting Started Locally

```bash
git clone https://github.com/labpulse-dev/LabPulse.git
cd LabPulse
cp .env.example .env
docker compose up --build
```

Frontend: http://localhost:3000
Backend health check: http://localhost:5000/api/health

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for branch naming, commit conventions, and the PR process before pushing any code.

## License

TBD
