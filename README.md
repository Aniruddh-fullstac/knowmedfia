<div align="center">

<br />

<!-- ═══ Hero ═══ -->
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://readme-typing-svg.demolab.com?font=DM+Sans&weight=600&size=28&duration=2800&pause=1200&color=F8FAFC&center=true&vCenter=true&width=520&lines=KnowMedia;Plan+%E2%80%94+Create+%E2%80%94+Measure;Your+AI-native+social+workspace">
  <img alt="KnowMedia — Plan, Create, Measure" src="https://readme-typing-svg.demolab.com?font=DM+Sans&weight=600&size=28&duration=2800&pause=1200&color=0F172A&center=true&vCenter=true&width=520&lines=KnowMedia;Plan+%E2%80%94+Create+%E2%80%94+Measure;Your+AI-native+social+workspace" width="520" />
</picture>

<h3><em>The AI-native social workspace for modern brands</em></h3>

<br />

Plan feeds · Generate creatives · Schedule campaigns · Read the room — **one calm, cohesive surface.**

<br />

[![Next.js](https://img.shields.io/badge/Next.js-15.2-000000?style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org)
[![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev)
[![Tailwind](https://img.shields.io/badge/Tailwind-v4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![Firebase](https://img.shields.io/badge/Firebase-11-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com)
[![Gemini](https://img.shields.io/badge/Google-Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://ai.google.dev)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.95-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)

<br />

</div>

<p align="center">
  <a href="#at-a-glance">Overview</a> ·
  <a href="#whats-inside">Features</a> ·
  <a href="#architecture">Architecture</a> ·
  <a href="#quickstart">Quickstart</a> ·
  <a href="#project-structure">Structure</a> ·
  <a href="#api-surface">API</a> ·
  <a href="#scripts">Scripts</a> ·
  <a href="#roadmap">Roadmap</a> ·
  <a href="#tech-stack">Stack</a>
</p>

---

## Contents

<table>
<tr>
<td valign="top" width="50%">

**Get oriented**

1. [At a glance](#at-a-glance) — the loop in one diagram
2. [What's inside](#whats-inside) — six core surfaces, feature map
3. [Architecture](#architecture) — topology, request flow, routes

</td>
<td valign="top" width="50%">

**Build & ship**

4. [Quickstart](#quickstart) — prereqs, env, run
5. [Project structure](#project-structure) — directory map
6. [API surface](#api-surface) — Next handlers + FastAPI sidecar
7. [Scripts](#scripts) · [Roadmap](#roadmap) · [Tech stack](#tech-stack)

</td>
</tr>
</table>

---

## At a glance

**KnowMedia** is a Next.js workspace that brings **social planning**, **generative content**, **marketing automation**, and **cross-platform analytics** together under one roof. The frontend is a Next.js 15 App Router application with a Tremor + Recharts analytics surface and a Fabric-powered canvas editor. The backend is a small FastAPI service that talks to the Instagram Graph API. Generative tasks run on Google's Gemini models.

> Built for solo creators and small social teams who want to ship faster than they could with Buffer, Hootsuite, or Later — and who want reporting to feel **less like a spreadsheet** and **more like a dashboard**.

<br />

### Product loop

How teams move through the workspace — from intent to insight:

```mermaid
%%{init: { "theme": "neutral", "themeVariables": { "fontFamily": "ui-sans-serif, system-ui, sans-serif" } }}%%
flowchart LR
  A(["Intent &amp; ideas"]) --> B(["Calendar + grid"]) --> C(["Copy + visuals"]) --> D(["Queue &amp; publish"]) --> E(["Analytics + AI"])
  E -.->|"iterate"| A

  classDef intent fill:#ede9fe,stroke:#7c3aed,stroke-width:1.8px,color:#4c1d95
  classDef plan   fill:#dbeafe,stroke:#2563eb,stroke-width:1.8px,color:#1e3a8a
  classDef make   fill:#dcfce7,stroke:#16a34a,stroke-width:1.8px,color:#14532d
  classDef ship   fill:#ffedd5,stroke:#ea580c,stroke-width:1.8px,color:#7c2d12
  classDef learn  fill:#fce7f3,stroke:#db2777,stroke-width:1.8px,color:#831843

  class A intent
  class B plan
  class C make
  class D ship
  class E learn

  linkStyle default stroke:#94a3b8,stroke-width:1.6px
```

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

### Feature map

```mermaid
%%{init: { "theme": "neutral" }}%%
mindmap
  root((KnowMedia))
    Plan
      Editorial calendar
      Grid planner
      Drag-to-schedule
    Create
      Gemini copy
      Gemini imagery
      Fabric canvas
    Automate
      Email blasts
      WhatsApp sends
      Recent activity
    Measure
      Tremor dashboards
      Recharts visuals
      AI Insights
    Identity
      Firebase Auth
      Google SSO
```

<br />

---

## Architecture

A four-tier layout: **Experience** (Next.js App Router) → **API gateway** (Next.js Route Handlers) → **Intelligence plane** (generation, automation, analytics) → **Model & data plane** (Gemini, Instagram Graph, Firebase).

### System topology

```mermaid
%%{init: { "theme": "neutral" }}%%
flowchart TB
  subgraph Experience["Experience layer"]
    direction TB
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

  classDef exp fill:#dbeafe,stroke:#2563eb,stroke-width:2px,color:#1e3a8a
  classDef gw fill:#ede9fe,stroke:#7c3aed,stroke-width:2px,color:#4c1d95
  classDef intel fill:#dcfce7,stroke:#16a34a,stroke-width:2px,color:#14532d
  classDef data fill:#ffedd5,stroke:#ea580c,stroke-width:2px,color:#7c2d12
  classDef db fill:#fef3c7,stroke:#d97706,stroke-width:2px,color:#78350f

  class SPA,AUTH exp
  class ROUTES gw
  class GEN,AUTO,ANA intel
  class GEM,IG data
  class FB db
```

<br />

### Request voyage (generation example)

```mermaid
%%{init: {
  "theme": "base",
  "themeVariables": {
    "fontFamily": "ui-sans-serif, system-ui, sans-serif",
    "primaryColor": "#dbeafe",
    "primaryBorderColor": "#2563eb",
    "primaryTextColor": "#1e3a8a",
    "actorBkg": "#dbeafe",
    "actorBorder": "#2563eb",
    "actorTextColor": "#1e3a8a",
    "actorLineColor": "#94a3b8",
    "signalColor": "#475569",
    "signalTextColor": "#0f172a",
    "labelBoxBkgColor": "#fef3c7",
    "labelBoxBorderColor": "#d97706",
    "labelTextColor": "#78350f",
    "noteBkgColor": "#fef3c7",
    "noteBorderColor": "#d97706",
    "noteTextColor": "#78350f",
    "activationBkgColor": "#ede9fe",
    "activationBorderColor": "#7c3aed",
    "sequenceNumberColor": "#ffffff"
  }
}}%%
sequenceDiagram
  autonumber
  participant U as Creator
  participant N as Next.js app
  participant R as Route handler
  participant G as Gemini API
  participant F as Firebase
  participant I as FastAPI / IG

  U->>N: Compose brief + brand tone
  N->>R: POST /api/generate/content
  R->>G: Generate caption / hooks
  G-->>R: Structured copy
  R-->>N: Response
  N-->>U: Inline suggestions + edits

  opt Optional publish path
    N->>R: POST /api/automate/*
    R->>I: Sidecar Instagram / channel action
    I-->>R: Delivery status
    R->>F: Persist campaign metadata
  end
```

<br />

| Tier | What lives here | Key dependencies |
|------|-----------------|------------------|
| **Experience** | App Router pages, dashboards, canvas editor | `next`, `react`, `tailwindcss`, `@tremor/react`, `recharts`, `fabric`, `lucide-react`, `@heroicons/react` |
| **API gateway** | Server route handlers under `src/app/api/*` | `next` (server) |
| **Intelligence** | Content + image generation, automation, analytics handlers | `@google/genai`, `@google/generative-ai`, `uuid` |
| **Model & data** | Gemini, Instagram Graph, Firebase | `firebase`, FastAPI sidecar (`instagram_api.py`) |

<br />

### API routing overview

```mermaid
%%{init: { "theme": "neutral" }}%%
flowchart LR
  subgraph NextAPI["Next.js · /src/app/api"]
    API1["/analytics/[user]"]
    API2["/generate/content"]
    API3["/generate/image"]
    API4["/automate/*"]
  end

  subgraph Fast["FastAPI sidecar · :8000"]
    P["POST /post"]
    S["POST /story"]
    H["POST /highlight"]
  end

  API1 --> IG["Instagram Graph"]
  API2 --> GEM["Gemini"]
  API3 --> GEM
  API4 --> CH["Channels · logs"]
  P --> IG
  S --> IG
  H --> IG

  classDef nextapi fill:#ede9fe,stroke:#7c3aed,stroke-width:1.8px,color:#4c1d95
  classDef fastapi fill:#dcfce7,stroke:#16a34a,stroke-width:1.8px,color:#14532d
  classDef ext     fill:#ffedd5,stroke:#ea580c,stroke-width:1.8px,color:#7c2d12
  classDef ai      fill:#dbeafe,stroke:#2563eb,stroke-width:1.8px,color:#1e3a8a
  classDef chan    fill:#fce7f3,stroke:#db2777,stroke-width:1.8px,color:#831843

  class API1,API2,API3,API4 nextapi
  class P,S,H fastapi
  class IG ext
  class GEM ai
  class CH chan

  style NextAPI fill:#faf5ff,stroke:#a78bfa,stroke-width:1.6px,color:#4c1d95
  style Fast    fill:#f0fdf4,stroke:#86efac,stroke-width:1.6px,color:#14532d

  linkStyle default stroke:#94a3b8,stroke-width:1.4px
```

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
git clone https://github.com/Aniruddh-fullstac/knowmedfia.git
cd knowmedfia
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

### Local runtime (two processes)

<div align="center">

![Local runtime — Next.js on :3000, Uvicorn on :8000, plus Gemini, Firebase, and Instagram Graph](docs/assets/local-runtime.svg)

</div>

<details>
<summary>View as Mermaid (source of truth)</summary>

```mermaid
%%{init: { "theme": "neutral" }}%%
flowchart TB
  subgraph Dev["Your machine"]
    direction LR
    FE["Next.js :3000<br/>App Router UI"]
    BE["Uvicorn :8000<br/>instagram_api.py"]
  end

  U((You)) --> FE
  FE -.->|REST| BE
  FE --> GEM2((Gemini))
  FE --> FB2((Firebase))
  BE --> IG2((Instagram Graph))

  classDef fe   fill:#dbeafe,stroke:#2563eb,stroke-width:1.8px,color:#1e3a8a
  classDef be   fill:#dcfce7,stroke:#16a34a,stroke-width:1.8px,color:#14532d
  classDef user fill:#fce7f3,stroke:#db2777,stroke-width:1.8px,color:#831843
  classDef ai   fill:#ede9fe,stroke:#7c3aed,stroke-width:1.8px,color:#4c1d95
  classDef ext  fill:#ffedd5,stroke:#ea580c,stroke-width:1.8px,color:#7c2d12
  classDef db   fill:#fef3c7,stroke:#d97706,stroke-width:1.8px,color:#78350f

  class FE fe
  class BE be
  class U user
  class GEM2 ai
  class FB2 db
  class IG2 ext

  style Dev fill:#f8fafc,stroke:#94a3b8,stroke-width:1.6px,color:#0f172a
  linkStyle default stroke:#94a3b8,stroke-width:1.4px
```

</details>

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

```mermaid
%%{init: { "theme": "neutral" }}%%
flowchart LR
  subgraph near["Near term"]
    n1["Shorts adapters<br/>deeper analytics"]
    n2["Multi-account workspaces<br/>RBAC"]
  end
  subgraph mid["Mid term"]
    m1["A/B captions and creatives"]
    m2["CSV and Notion bulk import"]
  end
  subgraph later["Later"]
    l1["Webhook publish queue<br/>retries"]
    l2["SSR snapshots<br/>shareable reports"]
  end
  near --> mid --> later

  classDef nearC  fill:#dcfce7,stroke:#16a34a,stroke-width:1.8px,color:#14532d
  classDef midC   fill:#dbeafe,stroke:#2563eb,stroke-width:1.8px,color:#1e3a8a
  classDef laterC fill:#ede9fe,stroke:#7c3aed,stroke-width:1.8px,color:#4c1d95

  class n1,n2 nearC
  class m1,m2 midC
  class l1,l2 laterC

  style near  fill:#f0fdf4,stroke:#86efac,stroke-width:1.6px,color:#14532d
  style mid   fill:#eff6ff,stroke:#93c5fd,stroke-width:1.6px,color:#1e3a8a
  style later fill:#faf5ff,stroke:#c4b5fd,stroke-width:1.6px,color:#4c1d95

  linkStyle default stroke:#64748b,stroke-width:1.8px
```

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

```mermaid
%%{init: {
  "theme": "base",
  "themeVariables": {
    "fontFamily": "ui-sans-serif, system-ui, sans-serif",
    "pie1": "#2563eb",
    "pie2": "#7c3aed",
    "pie3": "#16a34a",
    "pie4": "#ea580c",
    "pie5": "#d97706",
    "pieTitleTextSize": "18px",
    "pieTitleTextColor": "#0f172a",
    "pieSectionTextSize": "13px",
    "pieSectionTextColor": "#ffffff",
    "pieStrokeColor": "#ffffff",
    "pieStrokeWidth": "2px",
    "pieOuterStrokeColor": "#cbd5e1",
    "pieOuterStrokeWidth": "1px",
    "pieLegendTextColor": "#0f172a",
    "pieLegendTextSize": "13px",
    "pieOpacity": "0.95"
  }
}}%%
pie showData title Where compute runs (illustrative split)
    "Browser & Next.js UI" : 40
    "Next.js route handlers" : 25
    "Google Gemini" : 20
    "FastAPI and Instagram" : 10
    "Firebase" : 5
```

<br />

---

<div align="center">

**Built with care.**  
<sub><strong>KnowMedia</strong> · 2026</sub>

</div>
