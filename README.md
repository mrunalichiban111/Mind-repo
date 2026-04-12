<div align="center">

<img src="https://raw.githubusercontent.com/HariOm-Coder-Ambadnya/Mind-repo/main/assets/logo.png" alt="MindRepo Logo" width="120" />

# 🧠 MindRepo

**GitHub for thinking, not just code.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Java](https://img.shields.io/badge/Java-21-orange.svg)](https://openjdk.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.2-green.svg)](https://spring.io/)
[![Next.js](https://img.shields.io/badge/Next.js-14-black.svg)](https://nextjs.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-blue.svg)](https://www.postgresql.org/)
[![GSSoC](https://img.shields.io/badge/GSSoC-2025-purple.svg)](https://gssoc.girlscript.tech/)

[🚀 Live Demo](#) · [📖 Documentation](#documentation) · [🤝 Contributing](#contributing)

</div>

---

## 📋 Table of Contents

- [About](#about)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [GSSoC 2025](#gssoc-2025)
- [License](#license)
- [Contact](#contact)

---

## 🎯 About

**MindRepo** is a platform for documenting and version-controlling architectural decisions (ADRs) alongside your code. It bridges the gap between GitHub (which stores *what* you built) and the institutional knowledge of *why* you built it that way.

### The Problem

- **Knowledge Loss:** When developers leave, they take critical decision context with them
- **Decision Fatigue:** Teams repeatedly debate the same architectural choices
- **Onboarding Friction:** New developers struggle to understand codebase rationale
- **Scattered Documentation:** ADRs are buried in Confluence, Notion, or random Markdown files

### The Solution

MindRepo provides a **centralized, searchable, version-controlled platform** for:
- 📊 Tracking decision status (Proposed, Accepted, Deprecated, Superseded)
- 🏷️ Organizing by tags, repositories, and teams
- 🔍 Full-text search across all decisions
- ✍️ Rich-text editing with markdown support
- 🔐 GitHub OAuth integration

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🔐 **GitHub Authentication** | Secure login with GitHub OAuth |
| 📝 **Rich Text Editor** | TipTap-powered editor with markdown support |
| 📊 **Decision Lifecycle** | Track status: Proposed → Accepted → Deprecated/Superseded |
| 🏷️ **Tagging System** | Categorize decisions by technology, domain, or team |
| 🔍 **Full-Text Search** | Find decisions by content, author, or tags |
| 👥 **Collaboration** | Comments and team-based access |
| 🔔 **Notifications** | Email alerts for status changes |
| 📱 **Responsive UI** | Works on desktop, tablet, and mobile |

---

## 🛠️ Tech Stack

### Frontend
- **Framework:** [Next.js 14](https://nextjs.org/) (App Router)
- **Language:** [TypeScript](https://www.typescriptlang.org/)
- **Styling:** [Tailwind CSS](https://tailwindcss.com/)
- **State Management:** [Zustand](https://zustand-demo.pmnd.rs/)
- **Data Fetching:** [TanStack Query](https://tanstack.com/query/latest)
- **Editor:** [TipTap](https://tiptap.dev/)
- **Icons:** [Lucide React](https://lucide.dev/)

### Backend
- **Framework:** [Spring Boot 3.2](https://spring.io/)
- **Language:** [Java 21](https://openjdk.org/)
- **Database:** [PostgreSQL 16](https://www.postgresql.org/)
- **Cache:** [Redis](https://redis.io/)
- **Auth:** JWT + GitHub OAuth
- **Migrations:** [Flyway](https://flywaydb.org/)
- **Build Tool:** Maven

### DevOps
- **Containerization:** Docker & Docker Compose
- **Database Admin:** pgAdmin 4

---

## 🚀 Getting Started

### Prerequisites

- [Java 21+](https://adoptium.net/)
- [Maven 3.9+](https://maven.apache.org/)
- [Node.js 20+](https://nodejs.org/)
- [Docker](https://www.docker.com/) (optional, for database)

### Quick Start with Docker

```bash
# Clone the repository
git clone https://github.com/HariOm-Coder-Ambadnya/Mind-repo.git
cd Mind-repo

# Start PostgreSQL and Redis
docker-compose up -d postgres redis

# Setup backend
cd backend
cp .env.example .env
# Edit .env with your GitHub OAuth credentials
mvn spring-boot:run

# Setup frontend (in new terminal)
cd frontend
npm install
npm run dev
```

### Manual Setup

#### 1. Database Setup

```bash
# Start PostgreSQL and Redis
docker-compose up -d postgres redis
```

#### 2. Backend Setup

```bash
cd backend

# Copy environment file
cp .env.example .env

# Edit .env and add your GitHub OAuth credentials:
# GITHUB_CLIENT_ID=your_github_client_id
# GITHUB_CLIENT_SECRET=your_github_client_secret
# JWT_SECRET=your_jwt_secret_key

# Run migrations and start server
mvn clean install
mvn spring-boot:run
```

The backend will be available at `http://localhost:8080`

#### 3. Frontend Setup

```bash
cd frontend

# Install dependencies
npm install

# Start development server
npm run dev
```

The frontend will be available at `http://localhost:3000`

### GitHub OAuth Setup

1. Go to [GitHub Developer Settings](https://github.com/settings/developers)
2. Click "New OAuth App"
3. Fill in the details:
   - **Application name:** MindRepo (Local)
   - **Homepage URL:** `http://localhost:3000`
   - **Authorization callback URL:** `http://localhost:8080/login/oauth2/code/github`
4. Copy the Client ID and Client Secret to your `.env` file

---

## 📁 Project Structure

```
mindrepo/
├── backend/                    # Spring Boot application
│   ├── src/main/java/dev/mindrepo/
│   │   ├── auth/              # Authentication controllers
│   │   ├── decision/          # Decision (ADR) management
│   │   ├── org/               # Organization management
│   │   ├── repo/              # Repository management
│   │   ├── user/              # User management
│   │   └── common/            # Shared utilities
│   └── pom.xml
├── frontend/                  # Next.js application
│   ├── app/                   # App router pages
│   │   ├── auth/              # Auth callback
│   │   ├── dashboard/         # Main dashboard
│   │   └── decisions/         # Decision pages
│   ├── components/            # React components
│   ├── lib/                   # Utilities and API clients
│   └── stores/                # Zustand stores
└── docker-compose.yml         # Infrastructure services
```

---

## 📸 Screenshots

> *Screenshots will be added soon!*

---

## 🤝 Contributing

We welcome contributions from everyone! Whether you're fixing a typo, adding a feature, or improving documentation, your help is appreciated.

### How to Contribute

1. **Fork** the repository
2. **Clone** your fork: `git clone https://github.com/your-username/Mind-repo.git`
3. **Create a branch:** `git checkout -b feature/your-feature-name`
4. **Make your changes**
5. **Commit:** `git commit -m "Add feature: description"`
6. **Push:** `git push origin feature/your-feature-name`
7. **Open a Pull Request**

### Contribution Guidelines

- Follow the existing code style
- Write clear commit messages
- Add tests for new features
- Update documentation as needed
- Be respectful in discussions

See [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed guidelines.

---

## 🌸 GSSoC 2025

MindRepo is proud to be part of **GirlScript Summer of Code 2025**!

### About GSSoC

[GSSoC](https://gssoc.girlscript.tech/) is a 3-month open-source program by GirlScript Foundation aimed at helping beginners get started with open source while encouraging diversity in the tech community.

### For GSSoC Contributors

- **Level 1:** Documentation, minor bug fixes (10 points)
- **Level 2:** Small features, UI improvements (25 points)
- **Level 3:** Major features, architecture changes (45 points)

### Open Issues for GSSoC

| Issue | Labels | Points |
|-------|--------|--------|
| #1 - Add dark mode toggle | `good first issue`, `ui` | 10 |
| #2 - Implement decision templates | `feature`, `enhancement` | 25 |
| #3 - Add export to PDF | `feature` | 25 |
| #4 - Email notification system | `feature`, `backend` | 45 |

> Check the [Issues](../../issues) tab for more!

---

## 📜 License

This project is licensed under the [MIT License](./LICENSE).

```
MIT License

Copyright (c) 2025 HariOm-Coder-Ambadnya

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 📬 Contact

- **Project Maintainer:** [@HariOm-Coder-Ambadnya](https://github.com/HariOm-Coder-Ambadnya)
- **Email:** [your.email@example.com](mailto:your.email@example.com)
- **Discord:** [Join our server](#) *(coming soon)*

---

## 🙏 Acknowledgments

- [GirlScript Foundation](https://www.girlscript.tech/) for GSSoC
- [Spring Boot](https://spring.io/) team
- [Vercel](https://vercel.com/) for Next.js
- All our amazing contributors!

---

<div align="center">

**[⬆ Back to Top](#-mindrepo)**

Made with 💜 for the open-source community

</div>
