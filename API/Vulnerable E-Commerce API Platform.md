# 🛒 Vulnerable E-Commerce API

⚠️ **WARNING:**  
This application contains intentional security vulnerabilities for educational purposes only.  
**DO NOT deploy to production or use with real data.**

---

## 🎯 Project Overview

A realistic, production-like e-commerce API with intentional security vulnerabilities designed for:

- Security training  
- Penetration testing practice  

### 🔧 Features Included

- User authentication and authorization (JWT)
- Product catalog management
- Shopping cart operations
- Order processing with payment simulation
- Review and rating system
- Admin panel functionality
- File upload capabilities
- Internal microservices simulation
- Webhook integrations
- Coupon/discount system

---

## 📋 Security Implementations

> Some parts are intentionally secure to simulate real-world mixed environments

- Password hashing with bcrypt
- JWT-based authentication
- Input validation on selected endpoints
- Proper RBAC on some admin endpoints
- Parameterized SQL queries (in most places)

---

## 🚀 Quick Start

### 📦 Prerequisites

- Node.js 18+
- npm or yarn
- Docker (optional)

---

## 🔍 Check if Node.js is Installed

    node -v
    npm -v

If both fail → Node.js is not installed.

---

## 🛠️ Install Node.js

### ✅ Option 1: Package Manager (Recommended)

For **Ubuntu / Kali / Debian**:

    apt update
    apt install nodejs npm
    apt install python3-setuptools

---

### ✅ Option 2: NVM (Best Practice)

Install NVM:

    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

Reload shell:

    source ~/.zshrc

Install Node:

    nvm install node

Verify:

    node -v
    npm -v

---

## ⚙️ Installation

### 🖥️ Method 1: Local Setup

#### 1. Navigate to Project

    cd Vulnerable-Ecommerce-API

#### 2. Install Dependencies

    npm install sqlite3@latest
    npm install

#### 3. Configure Environment

    cp .env.example .env

(Optional: edit `.env` if needed)

#### 4. Seed Database

    npm run seed

#### 5. Start Server

    npm start

---

### 🌐 Access API

- API Base URL → http://localhost:3000/api/v1  
- API Docs (Swagger) → http://localhost:3000/api-docs  
- Health Check → http://localhost:3000/health  

---

## 🐳 Method 2: Docker Setup

Run container:

    docker run -p 3000:3000 infosecwarrior/vapi:latest

Seed database:

    docker-compose exec api npm run seed

Access API:

    http://localhost:3000

---

## 🔐 Test Accounts

| Username | Password    | Role           |
|----------|------------|----------------|
| admin    | Admin123!  | Administrator  |
| alice    | User123!   | Regular User   |
| bob      | User123!   | Regular User   |
| charlie  | User123!   | Regular User   |
| diana    | User123!   | Regular User   |
| eve      | User123!   | Regular User   |

---

## ⚠️ Disclaimer

This lab is intentionally vulnerable.  
Use it **only for learning and ethical hacking practice**.
