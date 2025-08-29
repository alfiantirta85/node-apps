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

## Requirements

1. Node.js
2. PosgreSQL Database

## Deployment Steps

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
# Install PostgreSQL
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
node server.js 
```

## Preview Apps

<img width="1321" height="958" alt="2025-08-29_13-20" src="https://github.com/user-attachments/assets/44eb00a5-6d7a-49d1-affc-b2dc73d2b08b" />
