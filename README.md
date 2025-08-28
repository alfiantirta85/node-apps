# Sample Node Apps

## Requirement

1. PosgreSQL Database

## Deployment Steps

1. Install Node.js

```bash
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt-get install -y nodejs

# Verify installation
node --version
npm --version
```

2. Clone Source Code

```bash
git clone https://github.com/alfiantirta85/node-apps.git
cd node-apps
```

3. Setup Env File

```bash
cp .env.example .env
nano .env
---
-- CHANGE-YOUR-ENV --
```

4. Install Requirements

```bash
npm install --production
```

5. Start Node.js Server

```bash
node server.js 
```