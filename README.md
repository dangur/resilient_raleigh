# ResilientRaleigh

Climate equity early warning for Southeast Raleigh. One Docker Compose stack runs the website, the API, and TimescaleDB on a Mac or an Ubuntu computer.

## Run at home

Install Docker Desktop or OrbStack on a Mac, or Docker Engine and the Compose plugin on Ubuntu.

```bash
cp .env.example .env
docker compose up --build -d
```

Open http://localhost:3000. From another device on the same network, open `http://<that-computer-ip>:3000`. If port 3000 is already in use, set `WEB_PORT` in `.env` and open that port instead.

On the site, choose **Seed storm pulse** to load the Walnut Creek gauges. Without `GEMINI_API_KEY`, alerts stay on the prepared fallback copy.

The database is only reachable by the API inside Docker. It is not published on the host.
