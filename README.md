# 📚 Bookify

## Overview
**Bookify** is a modular booking API system built with scalability and maintainability in mind. It leverages modern architectural patterns such as **CQRS**, **Outbox Pattern**, and **caching**, and is fully containerized using Docker. The project is ideal for scenarios requiring robust domain separation, asynchronous communication, and secure identity management.

---

## ✨ Features
- 🧭 **CQRS Architecture**: Separates read and write operations for better scalability and clearer domain logic.
- 📦 **Outbox Pattern**: Ensures reliable event publishing and eventual consistency across services.
- 🔐 **Identity Management**: Uses Keycloak for authentication and realm-based access control.
- 🧠 **Caching Layer**: Redis integration for performance optimization.
- 📊 **Structured Logging**: Integrated with Seq for centralized log management and observability.
- 🐳 **Dockerized Services**: All components run in isolated containers for easy deployment and orchestration.

---

## 🛠️ Tech Stack
- **Backend**: ASP.NET Core (C#)
- **Database**: PostgreSQL
- **Identity Provider**: Keycloak
- **Caching**: Redis
- **Logging**: Seq
- **Containerization**: Docker & Docker Compose

---

## 📦 Services

### `bookify.api`
- Main booking API service
- Exposes port `5000` → internal `8080`
- Built from `Bookify.Api/Dockerfile`

### `bookify-db`
- PostgreSQL database
- Stores booking data
- Volume-mounted for persistence

### `bookify-idp`
- Keycloak identity provider
- Uses `start-dev` mode with realm import
- Admin credentials configured via environment variables

### `bookify-seq`
- Seq logging server
- Exposes ports `5341` (ingestion) and `8081` (UI)

### `bookify-redis`
- Redis cache server
- Used for performance optimization and async workflows

