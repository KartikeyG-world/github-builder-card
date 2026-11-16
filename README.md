# GitHub Builder Card

**Engineering Challenge:** Hackyard Winter 2026 Engineering Challenge
**Application Type:** Single-Page Frontend Application (SPA)

---

## 1. Project Purpose

GitHub Builder Card is a focused, responsive web application that enables users to look up any public GitHub username and view an informative, developer-centric Builder Card.

When fully implemented, the application will display:
1. **GitHub Profile Information:** Display name, username, avatar, bio, location, company, website, and follower/following metrics.
2. **Top Repositories:** Top public non-fork repositories ranked by stars across up to 100 recently active repositories.
3. **Primary Language Distribution:** Percentage distribution of primary programming languages across sampled public repositories.
4. **Recent Public Activity:** Chronological timeline of public events from the past 30 days formatted using verified GitHub Events API payload fields.

---

## 2. Technology Stack

* **View Library:** React 19 (`react`, `react-dom`)
* **Type System:** TypeScript 7 (`strict: true`)
* **Build Tool & Dev Server:** Vite 8 (powered by the Rolldown unified bundler)
* **Styling:** Tailwind CSS v4 (`@tailwindcss/vite`, CSS-first configuration via `@import "tailwindcss";`)
* **Component Primitives:** shadcn/ui (Radix UI headless primitives styled via Tailwind CSS variables)
* **Iconography:** Lucide React (`lucide-react`)
* **Class Merging:** `cn` (`cn` package by shadcn)
* **Data Source:** GitHub REST API (`api.github.com`)
* **Target Deployment Platform:** Vercel (static single-page application)

---

## 3. Current Implementation Status

> **Status: Phase 1 Baseline Setup Verified (Application Logic Pending)**

* **Completed:**
  * Project scaffolded with React 19, TypeScript 7, Vite 8, and Tailwind CSS v4.
  * Verified `@tailwindcss/vite` integration and `@/*` path alias configuration.
  * Installed core shadcn/ui primitives (`Button`, `Card`, `Badge`, `Input`, `Skeleton`, `Separator`).
  * Established project guidelines and standards in `AGENTS.md`.
  * Cleaned up starter branding and unused assets.
  * Verified clean TypeScript compilation and production builds (`tsc -b && vite build`).
* **Not Yet Implemented:**
  * GitHub REST API client and domain types (Phase 2).
  * Repository ranking, language distribution, and event formatting transforms (Phase 2).
  * Builder Card presentation components and search flow (Phase 3 & 4).

---

## 4. Getting Started

### Prerequisites

* Node.js: `v22` or `v24` (Current environment: `v24.15.0`)
* npm: `10.x` or `11.x` (Current environment: `11.12.1`)

### Installation

Clone the repository and install dependencies:

```bash
npm install
```

### Development Server

Start the local Vite development server with Hot Module Replacement (HMR):

```bash
npm run dev
```

### Production Build

Run TypeScript type-checking and generate the production bundle:

```bash
npm run build
```

The output will be generated in the `dist/` directory.

### Linting

Run Oxlint to check code quality:

```bash
npm run lint
```
