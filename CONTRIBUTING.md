# Contributing to LabPulse

Welcome to the team! Please read this before pushing your first commit.

## Branching

Branch off `main` for all work. Never commit directly to `main`.

| Prefix | Use for |
|--------|---------|
| `feature/` | New features |
| `fix/` | Bug fixes |
| `infra/` | Docker, CI, cloud config |
| `docs/` | Documentation only |

Example: `git checkout -b feature/device-list-api`

## Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):
feat: add device ping endpoint

fix: correct null check in metrics worker

infra: add nginx reverse proxy config

docs: update deployment guide

## Pull Requests

- Open a PR against `main` for every change, even small ones
- Describe what changed and how to test it
- CI must be green before merging
- Squash and merge to keep history clean

## Local Dev

```bash
cp .env.example .env
docker compose up --build
```

Frontend: http://localhost:3000
Backend: http://localhost:5000

## Code Style

- Python: PEP8, run `flake8 .` before pushing
- JavaScript: keep it consistent with existing files
- Write a test for any new backend endpoint

## Questions?

Ask in the group chat, don't sit on it.
