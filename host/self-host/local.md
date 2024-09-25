---
title: 'Deploy Terapi on your local machine'
sidebarTitle: 'Locally'
---

Set up Terapi locally in 3 minutes. Run: 
```bash
git clone https://github.com/NangoHQ/nango && cd nango
```
```bash
docker compose up
```

Go to your [local Dashboard](http://localhost:3003).

Check out the `.env.example` file for all configuration options. 

Terapi uses the following ports (all overridable with `docker-compose.yaml` or env vars): 
- Server: 3003
- Postgres: 5432

