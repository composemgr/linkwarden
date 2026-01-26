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
docker compose up -d
```

### Option 3: Using composemgr
```bash
composemgr install linkwarden
```

## 🔧 Configuration

### Environment Variables

```shell
TZ=America/New_York
APP_JWT_TOKEN=changeme_jwt_secret
DB_USER_NAME=linkwardendb
```

See `docker-compose.yaml` for complete list of configurable options.

## 🌐 Access

- **Web Interface**: http://172.17.0.1:59051

## 📂 Volumes

- `./rootfs/data/linkwarden` - Data storage
- `./rootfs/data/db/postgres/linkwarden` - Data storage

## 🔐 Security

- Change all default passwords before deploying to production
- Use strong secrets for all authentication tokens
- Configure HTTPS using a reverse proxy (nginx, traefik, caddy)
- Regularly update Docker images for security patches
- Backup your data regularly

## 🔍 Logging

```shell
docker compose logs -f app
```

## 🛠️ Management

```bash
# Start services
docker compose up -d

# Stop services
docker compose down

# Update to latest images
docker compose pull && docker compose up -d

# View logs
docker compose logs -f

# Restart services
docker compose restart
```

## 📋 Requirements

- Docker Engine 20.10+
- Docker Compose V2+

## 🤝 Author

🤖 casjay: [Github](https://github.com/casjay) 🤖  
🦄 composemgr: [Github](https://github.com/composemgr) 🦄
