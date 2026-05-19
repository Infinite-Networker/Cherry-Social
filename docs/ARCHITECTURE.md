# 🏗️ Cherry-Social Architecture

> Built by **Cherry Computer Ltd.**

## System Overview

Cherry-Social follows a modern, scalable microservices-inspired architecture with a monorepo structure.

```
                    ┌────────────────────┐
                    │   CDN / Edge Cache  │
                    └────────┬───────────┘
                             │
                    ┌────────▼───────────┐
                    │   Load Balancer     │
                    └────────┬───────────┘
                             │
              ┌──────────────┼──────────────┐
              │              │              │
     ┌────────▼────┐ ┌───────▼──────┐ ┌────▼─────────┐
     │  React App  │ │  Express API │ │ WebSocket Srv │
     │  (Vite SSR) │ │  (GraphQL)   │ │ (Socket.io)  │
     └─────────────┘ └──────┬───────┘ └──────────────┘
                            │
              ┌─────────────┼─────────────┐
              │             │             │
     ┌────────▼────┐ ┌──────▼──────┐ ┌───▼───────┐
     │ PostgreSQL  │ │   Redis     │ │    S3     │
     │  (Primary)  │ │  (Cache)    │ │ (Storage) │
     └─────────────┘ └─────────────┘ └───────────┘
```

## Key Design Principles

1. **API-First** — All features exposed via GraphQL & REST endpoints
2. **Real-time** — WebSocket connections for live notifications & feeds
3. **Cache-heavy** — Redis caching for hot data, CDN for static assets
4. **Privacy-first** — E2E encryption for DMs, minimal data collection
5. **Open Source** — Full transparency, community-driven development

---

*© 2024 Cherry Computer Ltd.*
