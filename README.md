# SIH 26024 — Android Application

Field operations application for coal mine inspections, compliance monitoring,
incident reporting, and geo-tagged field data collection.

## Tech Stack

- React Native + Expo
- TypeScript
- Expo Location — GPS / Geo-tagging
- Expo Camera — Photos / Media
- SQLite — Offline Storage
- Go API Gateway
- Python + FastAPI — Backend / AI Integration

## Architecture

```mermaid
flowchart TD
    U[Field Users] --> A[Android App<br/>React Native + Expo]

    A --> G[GPS / Camera]
    A --> O[Offline SQLite]

    A --> GW[Go API Gateway<br/>Auth • RBAC • Rate Limit]

    GW --> B[Python FastAPI]
    B --> AI[AI / ML Services]

    B --> DB[(PostgreSQL + PostGIS)]
    B --> R[Cloudflare R2]
    B --> N[Notifications]

    DB --> W[Web Dashboard]
    AI --> W
