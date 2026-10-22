# Code Connect

Code Connect is a developer community app in early development: a place for
developers to create profiles, connect with each other, and build community
around code. This repository holds the web app, built with TanStack Start,
React, Tailwind CSS, and Supabase.

## Current status

The product screens are not built yet. What exists today is the project
foundation, ready for feature work:

- TanStack Start app shell with file-based routing, a root layout, a custom
  404 page, and an error boundary with error reporting.
- A complete shadcn/ui component library in `src/components/ui` (buttons,
  forms, dialogs, tables, charts, navigation, and more), styled with
  Tailwind CSS 4.
- Supabase wiring in `src/integrations/supabase`: browser client, server
  client, auth middleware and auth token attacher, and generated database
  types. The connected Supabase project currently has no tables defined.
- The home route (`src/routes/index.tsx`) is still the starter placeholder
  page and is the first thing to replace when feature work starts.

## Tech stack

- React 19 and TypeScript
- TanStack Start, TanStack Router (file-based routing), TanStack Query
- Tailwind CSS 4 with shadcn/ui (Radix UI primitives)
- Supabase (Postgres database and auth) via `@supabase/supabase-js`
- Vite 8 and Nitro for dev, build, and preview
- React Hook Form and Zod for forms and validation

## Getting started

Prerequisites: Node.js and npm.

```sh
git clone https://github.com/ramgubbala333-byte/my-code-connect.git
cd my-code-connect
npm install
cp .env.example .env
npm run dev
```

Then fill in `.env` with your own Supabase project values (Supabase
dashboard, Project Settings, API).

## Environment variables

| Variable | Used by |
| --- | --- |
| `SUPABASE_URL` | Server-side Supabase client |
| `SUPABASE_PUBLISHABLE_KEY` | Server-side Supabase client |
| `SUPABASE_PROJECT_ID` | Tooling and configuration |
| `VITE_SUPABASE_URL` | Browser Supabase client |
| `VITE_SUPABASE_PUBLISHABLE_KEY` | Browser Supabase client |
| `VITE_SUPABASE_PROJECT_ID` | Browser configuration |

Note: earlier commits in this repository's history contained a committed
`.env` file. It held only the Supabase publishable (anon) keys, which are
public client keys designed to ship in browser apps. The file has been
removed from the current tree, and `.env` is now gitignored.

## Scripts

| Command | What it does |
| --- | --- |
| `npm run dev` | Start the Vite dev server |
| `npm run build` | Production build |
| `npm run build:dev` | Build in development mode |
| `npm run preview` | Preview the production build |
| `npm run lint` | Run ESLint |
| `npm run format` | Format the codebase with Prettier |

## Project structure

```text
src/
  routes/          File-based routes (__root.tsx is the app shell)
  components/ui/   shadcn/ui component library
  integrations/
    supabase/      Supabase clients, auth helpers, generated types
  hooks/           React hooks
  lib/             Utilities and error reporting
  router.tsx       Router setup
  server.ts        Server entry point
  start.ts         App entry point
supabase/
  config.toml      Local Supabase configuration
```

## License

MIT. See [LICENSE](LICENSE).
