# CppMasterHub

A professional C++ programming educational platform — the definitive C++ learning hub covering tutorials, interview prep, practice problems, and projects from beginner to advanced.

## Run & Operate

- `pnpm --filter @workspace/cppmasterhub run dev` — run the frontend (served via workflow)
- `pnpm --filter @workspace/api-server run dev` — run the API server (port 5000)
- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from the OpenAPI spec
- Required env: `DATABASE_URL` — Postgres connection string (not used yet; site is frontend-only)

## Stack

- pnpm workspaces, Node.js 24, TypeScript 5.9
- Frontend: React + Vite, Tailwind CSS, wouter (routing), framer-motion (animations)
- API: Express 5 (optional backend, not yet used)
- DB: PostgreSQL + Drizzle ORM (provisioned when needed)
- Build: Vite (static output)

## Where things live

- `artifacts/cppmasterhub/src/` — all frontend source
- `artifacts/cppmasterhub/src/data/` — tutorial, practice, interview, project data
- `artifacts/cppmasterhub/src/pages/` — page components
- `artifacts/cppmasterhub/src/components/` — shared UI components
- `artifacts/cppmasterhub/index.html` — includes chatbot script tag
- `artifacts/api-server/src/routes/` — API route handlers

## Architecture decisions

- Frontend-only for v1: all tutorial content is static data (no DB needed)
- Green + dark theme matching GeeksforGeeks-style educational branding
- Wouter for client-side routing with dynamic `:category/:topic` params
- Chatbot embedded via external script tag in index.html

## Product

CppMasterHub is a GeeksforGeeks-inspired C++ learning platform with:
- 9 tutorial categories (Basics, OOP, STL, DS, Algorithms, etc.) with detailed per-topic pages
- Syntax-highlighted C++ code examples on every tutorial
- Interview prep section with 20+ expandable Q&A
- Practice problems in Easy/Medium/Hard tiers
- Project showcase (Beginner → Advanced)
- Dark/light mode toggle
- Embedded AI chatbot

## User preferences

_Populate as you build — explicit user instructions worth remembering across sessions._

## Gotchas

- Google Fonts @import must be the FIRST line in index.css (before @import "tailwindcss")
- All `red` placeholder CSS vars must be replaced before any component renders
- Chatbot script: `<script src='https://www.noupe.com/embed/019ec6df1a9d77db85ca7355122a705121a3.js'></script>` in index.html

## Pointers

- See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details
