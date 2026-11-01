## 👋 Welcome to linkwarden 🚀

Collaborative bookmark manager with screenshots and PDFs

## 📋 Description

Collaborative bookmark manager with screenshots and PDFs

## 🚀 Services

- **app**: ghcr.io/linkwarden/linkwarden:latest

### Infrastructure Components

- **db**: Postgres database


## 📦 Installation

### Option 1: Quick Install
```bash
curl -q -LSsf "https://raw.githubusercontent.com/composemgr/linkwarden/main/docker-compose.yaml" -o compose.yml
```

### Option 2: Git Clone
```bash
git clone "https://github.com/composemgr/linkwarden" ~/.local/srv/docker/linkwarden
cd ~/.local/srv/docker/linkwarden
cp default.env .env
docker compose --env-file .env up -d
```

### Option 3: Using composemgr
```bash
composemgr install linkwarden
```

## 🔧 Configuration

### Environment Variables

```shell
TZ=America/New_York
BASE_DOMAIN_NAME=example.com
BASE_HOST_NAME=linkwarden.example.com
DB_USER_NAME=linkwardendb
DB_USER_PASS=replace-with-a-random-password
APP_SECRET_KEY=replace-with-a-random-32-character-secret
```

See `docker-compose.yaml` for complete list of configurable options.

### Environment Files

`default.env.sample` holds the full set of variables and is copied to `.env`
before starting the stack:

```bash
cp default.env .env
docker compose --env-file .env up -d
```

`app.env.sample` holds the app-specific overrides and is copied to `app.env`:

```bash
cp app.env.sample app.env
```

`composemgr up` applies `app.env` and `default.env` automatically. Raw
`docker compose` commands need `--env-file .env` to pick up the same values.

### Reverse Proxy

Three standalone compose files ship in this repo:

| File | Use |
|------|-----|
| `docker-compose.yaml` | Default, published on `172.17.0.1:64237` |
| `docker-compose.traefik.yaml` | Behind an existing external `traefik` network |
| `docker-compose.tunnel.yaml` | Behind an existing external `cloudflare` tunnel network |

```bash
docker compose -f docker-compose.traefik.yaml --env-file .env up -d
```

## 🌐 Access

- **Web Interface**: http://172.17.0.1:64237

## 📂 Volumes

- `./volumes/data/linkwarden` - Linkwarden data storage
- `./volumes/db/postgres/linkwarden` - Database data
## 🔐 Security

- Change all default passwords before deploying to production
- Use strong secrets for all authentication tokens
- Configure HTTPS using a reverse proxy (nginx, traefik, caddy)
- Regularly update Docker images for security patches
- Backup your data regularly

## 🔍 Logging

```shell
docker compose --env-file .env logs -f app
```

## 🛠️ Management

```bash
# Start services
docker compose --env-file .env up -d

# Stop services
docker compose --env-file .env down

# Update to latest images
docker compose --env-file .env pull && docker compose --env-file .env up -d

# View logs
docker compose --env-file .env logs -f

# Restart services
docker compose --env-file .env restart
```

## 📋 Requirements

- Docker Engine 20.10+
- Docker Compose V2+

## 🤝 Author

🤖 casjay: [Github](https://github.com/casjay) 🤖
🦄 composemgr: [Github](https://github.com/composemgr) 🦄
