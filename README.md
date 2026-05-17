<div align="center">

<br />

# **KnowMedia**

### *The AI-native social workspace for modern brands*

<br />

<p>
  Plan feeds. Generate creatives. Schedule campaigns.<br/>
  Read the room — all from a single, beautifully calm workspace.
</p>

<br />

[![Next.js](https://img.shields.io/badge/Next.js-15.2-000000?style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org)
[![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev)
[![Tailwind](https://img.shields.io/badge/Tailwind-v4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![Firebase](https://img.shields.io/badge/Firebase-11-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com)
[![Gemini](https://img.shields.io/badge/Google-Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://ai.google.dev)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.95-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)

<br />

</div>

---

## At a glance

**KnowMedia** is a Next.js workspace that brings social planning, generative content, marketing automation, and cross-platform analytics together under one roof. The frontend is a Next.js 15 App Router application with a Tremor + Recharts analytics surface and a Fabric-powered canvas editor. The backend is a small FastAPI service that talks to the Instagram Graph API. Generative tasks run on Google's Gemini models.

> Built for solo creators and small social teams who want to ship faster than they could with Buffer, Hootsuite, or Later — and who want their reporting to feel less like a spreadsheet and more like a dashboard.

<br />

<div align="center">

| | | |
|:---:|:---:|:---:|
| **Plan** | **Create** | **Measure** |
| Editorial calendar, grid planner, drag-to-schedule | Gemini-assisted copy, Fabric-powered design canvas | Cross-platform analytics with AI insights |

</div>

<br />

---

## What's inside

<table>
<tr>
<td width="33%" valign="top">

### Content studio

Generate captions, hooks, and on-brand imagery via Gemini. Refine creatives inside a Fabric.js canvas with full layer control, then push straight to the publishing queue.

</td>
<td width="33%" valign="top">

### Unified analytics

Tremor + Recharts dashboards over Instagram, LinkedIn, and other platforms. The **AI Insights** pane summarises engagement, demographics, and what's working — in plain English.

</td>
<td width="33%" valign="top">

### Marketing automation

One-click marketing blasts across email and WhatsApp, with recent-send timelines. Drop-in templates, recipient segments, and delivery confirmations.

</td>
</tr>
<tr>
<td valign="top">

### Editorial calendar

A drag-to-schedule calendar grid with an in-place event creator. Visualise your campaign cadence and never publish two reels on the same day by accident.

</td>
<td valign="top">

### Feed manager

Plan your grid before it goes live. Rearrange posts, preview the gallery, and lock in a look that holds up across nine, twelve, and fifteen tiles.

</td>
<td valign="top">

### Creator profiles

Per-user profile pages with feed, posts, and engagement at a glance — useful for agencies running multiple handles or creators auditing peers.

</td>
</tr>
</table>

<br />

---

## Architecture

A four-tier layout: **Experience** (Next.js App Router) → **API gateway** (Next.js Route Handlers) → **Intelligence plane** (generation, automation, analytics) → **Model & data plane** (Gemini, Instagram Graph, Firebase).

```mermaid
flowchart TB
  subgraph Experience["Experience layer"]
    SPA["Next.js 15 · React 19<br/>Tailwind v4 · Tremor · Fabric"]
    AUTH["Firebase Auth<br/>Google SSO"]
  end

  subgraph Gateway["API gateway"]
    ROUTES["Next.js Route Handlers<br/>src/app/api/*"]
  end

  subgraph Intelligence["Intelligence plane"]
    GEN["Generation<br/>content + image"]
    AUTO["Automation<br/>email · WhatsApp blasts"]
    ANA["Analytics aggregation<br/>per-username"]
  end

  subgraph Providers["Model & data plane"]
    GEM["Google Gemini<br/>@google/genai"]
    IG["FastAPI · instagram_api<br/>localhost:8000"]
    FB[("Firebase<br/>auth · persistence")]
  end

  SPA --> AUTH
  SPA --> ROUTES
  ROUTES --> GEN
  ROUTES --> AUTO
  ROUTES --> ANA
  GEN --> GEM
  AUTO --> IG
  ANA --> IG
  ANA --> FB
  AUTH --> FB
```

<br />

| Tier | What lives here | Key dependencies |
|------|-----------------|------------------|
| **Experience** | App Router pages, dashboards, canvas editor | `next`, `react`, `tailwindcss`, `@tremor/react`, `recharts`, `fabric`, `lucide-react`, `@heroicons/react` |
| **API gateway** | Server route handlers under `src/app/api/*` | `next` (server) |
| **Intelligence** | Content + image generation, automation, analytics handlers | `@google/genai`, `@google/generative-ai`, `uuid` |
| **Model & data** | Gemini, Instagram Graph, Firebase | `firebase`, FastAPI sidecar (`instagram_api.py`) |

<br />

---

## Quickstart

### Prerequisites

- **Node.js** 20 or newer
- **npm** (or pnpm / yarn / bun)
- **Python** 3.11+ — for the Instagram backend
- **Firebase** project with a web app configured
- **Google AI Studio** API key for Gemini
- **Instagram Graph API** long-lived access token

### Install

```bash
git clone <your-fork-url>
cd KnowMedia
npm install
```

### Configure

Create `.env.local` at the project root:

```dotenv
# Firebase web SDK
NEXT_PUBLIC_FIREBASE_API_KEY=
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=
NEXT_PUBLIC_FIREBASE_PROJECT_ID=
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=
NEXT_PUBLIC_FIREBASE_APP_ID=

# Google Gemini
GOOGLE_GENAI_API_KEY=

# Instagram backend
INSTAGRAM_GRAPH_TOKEN=
NEXT_PUBLIC_BACKEND_URL=http://localhost:8000
```

### Run

```bash
# Frontend — Next.js (http://localhost:3000)
npm run dev

# Backend — FastAPI Instagram sidecar (http://localhost:8000)
cd src/backend
pip install -r requirements.txt
uvicorn instagram_api:app --reload
```

Open <http://localhost:3000> and sign in with your Google account.

<br />

---

## Project structure

```text
KnowMedia/
├── public/                       Static assets — avatars, post imagery, icons
├── src/
│   ├── app/                      Next.js App Router
│   │   ├── api/
│   │   │   ├── analytics/        Per-username analytics endpoint
│   │   │   ├── automate/         Marketing blast · recent emails · recent WhatsApp
│   │   │   └── generate/         Content + image generation
│   │   ├── analytics/            Analytics dashboard
│   │   ├── automation/           Automation surface
│   │   ├── calendar/             Editorial calendar
│   │   ├── contentideas/         AI content ideation
│   │   ├── create/               New-post flow
│   │   ├── feed/                 Public feed view
│   │   ├── manage-feed/          Grid planner
│   │   ├── post/                 Post detail + create
│   │   ├── profile/              Creator profiles
│   │   └── components/           Page-scoped UI
│   │       ├── analytics/        AnalyticsDashboard, AIInsights, charts
│   │       ├── calendar/         CalendarGrid, EventCreator
│   │       ├── feed/             Grid, PostItem
│   │       ├── layout/           AppLayout, Navbar, Sidebar
│   │       └── post/             MediaDesigner (Fabric), PostCreator, PostItem
│   ├── backend/                  FastAPI Instagram sidecar
│   │   ├── instagram_api.py      /post · /story · /highlight
│   │   ├── requirements.txt
│   │   └── Dockerfile
│   └── components/               Shared UI (analytics charts, etc.)
├── next.config.mjs
├── postcss.config.mjs
├── jsconfig.json
└── package.json
```

<br />

---

## API surface

### Next.js route handlers

| Route | Purpose |
|-------|---------|
| `GET  /api/analytics/[username]` | Fetch analytics for a given handle |
| `POST /api/automate` | Trigger generic automation jobs |
| `POST /api/automate/marketing-blast` | Send a marketing blast across channels |
| `GET  /api/automate/recent-emails` | Pull recent email send history |
| `GET  /api/automate/recent-whatsapp` | Pull recent WhatsApp send history |
| `POST /api/generate/content` | Generate caption / copy via Gemini |
| `POST /api/generate/image` | Generate imagery via Gemini |

### FastAPI sidecar — Instagram Graph

| Route | Purpose |
|-------|---------|
| `POST /post` | Publish an image post with caption |
| `POST /story` | Publish a story |
| `POST /highlight` | Create a highlight cover |

Interactive docs at <http://localhost:8000/docs> (Swagger) or `/redoc`.

<br />

---

## Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start Next.js in development on port `3000` |
| `npm run build` | Production build |
| `npm start` | Start the production server |
| `npm run lint` | Run Next.js / ESLint checks |

<br />

---

## Roadmap

- TikTok and YouTube Shorts analytics adapters
- Multi-account workspaces with role-based access
- Native A/B testing for captions and creatives
- Bulk import from CSV and Notion
- Webhook-based publish queue with retries
- Server-side rendering for shareable analytics snapshots

<br />

---

## Tech stack

<table>
<tr>
<td valign="top" width="50%">

**Frontend**

- Next.js 15.2 (App Router)
- React 19
- Tailwind CSS v4
- Tremor 3 — dashboard primitives
- Recharts — composable charts
- Fabric.js 6 — canvas media editor
- Lucide React + Heroicons
- React Colorful — color pickers

</td>
<td valign="top" width="50%">

**Backend & services**

- Next.js Route Handlers
- FastAPI 0.95 + Uvicorn — Instagram sidecar
- Google Gemini via `@google/genai`
- Firebase 11 — auth + persistence
- Instagram Graph API
- UUID for ID generation
- Docker — backend container

</td>
</tr>
</table>

<br />

---

<div align="center">

<sub>Built with care.</sub><br/>
<sub><strong>KnowMedia</strong> · 2026</sub>

</div>
