# 🚀 Sample Node Apps

A simple CRUD application with Node.js, Express, PostgreSQL, and vanilla JavaScript frontend.

## ✨ Features

### 🎯 Core Functionality

- Full CRUD Operations - Create, Read, Update, Delete users
- RESTful API - Clean API endpoints with proper HTTP methods
- Real-time UI Updates - Dynamic frontend without page refresh
- Input Validation - Client and server-side validation
- Error Handling - Comprehensive error management

### 🎨 User Interface

- Modern Design - Gradient backgrounds and clean aesthetics
- Responsive Layout - Mobile-first design approach
- Interactive Cards - Hover effects and smooth animations
- Real-time Statistics - Live user count and metrics
- Success/Error Messages - Visual feedback for all actions
- Auto-refresh - Automatic data updates every 30 seconds

## 🏗️ Requirements

1. Node.js
2. PosgreSQL Database

## 🖥️ Systemd Deployment

1. Install Node.js

```bash
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt-get install -y nodejs

# Verify installation
node --version
npm --version
```

2. Install PostgreSQL

```bash
sudo apt-get install -y postgresql postgresql-contrib
sudo systemctl enable --now postgresql
```

3. Setup PostgreSQL

```
# Create database and user
sudo -u postgres psql
CREATE DATABASE [your-database-name];
CREATE USER [your-user-name] WITH PASSWORD '[your-user-password]';
GRANT ALL PRIVILEGES ON DATABASE [your-user-name] TO [your-user-name];
\q
```

4. Clone Source Code

```bash
cd /opt
git clone https://github.com/alfiantirta85/node-apps.git
cd node-apps
```

5. Setup Database Environment

```bash
cp .env.example .env
nano .env
---
-- CHANGE-YOUR-ENV --
```

6. Install Requirements

```bash
npm install --production
```

7. Start Node.js Server

```bash
npm start
```

8. Start Node.js Server as Service

```bash
nano /etc/systemd/system/node-apps.service
---
[Unit]
Description=Node Apps
After=network-online.target postgresql.service
Wants=postgresql.service

[Service]
User=root
Group=root
Type=simple
Restart=on-failure
RestartSec=5
WorkingDirectory=/opt/node-apps
ExecStart=/usr/bin/npm start

[Install]
WantedBy=multi-user.target
---
systemctl daemon-reload
systemctl enable --now node-apps.service

# Verify Service
systemctl status node-apps.service
```

## 🐳 Docker Deployment

1. Install Docker

```bash
apt-get install ca-certificates curl
install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
chmod a+r /etc/apt/keyrings/docker.asc
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
apt-get update
apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y

# Verify installation
docker version
docker compose version
```

2. Clone Source Code

```bash
cd /opt
git clone https://github.com/alfiantirta85/node-apps.git
cd node-apps
```

3. Start PostgreSQL

```bash
docker compose -f docker/db-compose.yml up -d

# Verify DB
docker ps
```

4. Build Image

```bash
docker build -t node-apps -f docker/Dockerfile .
```

5. Setup Database Environment

```bash
cp .env.example .env
nano .env
---
-- CHANGE-YOUR-ENV --
```

6. Start Container

```bash
docker compose up docker/app-compose.yml -d

# Verify App
docker ps
```

## Preview Apps

<img width="1311" height="955" alt="2025-08-29_19-36" src="https://github.com/user-attachments/assets/fb20b64c-9983-48e0-bacd-7418551b83ab" />
