<div align="center">

<img src="public/logo-mark.png" alt="BioRefMind" width="72" />

# BioRefMind

**The bio-waste marketplace: farmers and factories sell peels, pomace and residues to the industries that need them.**

[Live site](https://biorefmind.vercel.app)

</div>

## Project

| | |
|---|---|
| **Project** | BioRefMind |
| **CEO** | Hadjer |
| **Developer** | Azeddine Zellag |
| **Website** | [biorefmind.vercel.app](https://biorefmind.vercel.app) |
| **Contact** | biorefmindproject@gmail.com |
| **Languages** | English, Arabic (right to left) |

## What it does

- **Marketplace:** farms and factories list crop residues and by-products; buyers browse and send interest requests.
- **Quality score and routing:** every batch gets a 0–100 quality score and a route: **A** pharmaceutical, **B** food-grade or **C** recovery. Inspectors can override a route with a logged reason.
- **Certificates:** lab results from partner labs and BioRefMind's own testing team, with a public verification page.
- **Three account types:** farm (free), lab and factory workspaces, each with its own dashboard.
- **AI assistant:** answers questions about a workspace's data, checks lot photos and reads lab result files (Anthropic Claude).
- **Admin panel:** moderation, lots, inquiries, labs and AI settings.

## Tech stack

| Layer | Tools |
|---|---|
| Frontend | Next.js 16 (App Router), React 19, TypeScript, Tailwind CSS 4, shadcn/ui on Base UI, Motion, ECharts |
| Backend | Convex (database and server functions) |
| Auth | Better Auth running inside Convex |
| AI | Anthropic Claude via `@anthropic-ai/sdk` |
| Tests | Vitest, convex-test |
| Hosting | Vercel + Convex |

## Project structure

```
.
├── convex/             Backend: schema, queries, mutations, actions, tests
│   └── lib/            Shared rules (accounts, pricing, AI adapter, scoring)
├── public/             Logo and landing page artwork
└── src/
    ├── app/            Routes: landing, auth, dashboard, marketplace, admin, verify
    ├── components/     UI: landing, dashboard, marketplace, admin, certificate, ui
    ├── i18n/           English / Arabic messages and locale handling
    └── lib/            Client helpers: auth, backend access, types, utilities
```

## Getting started

Requirements: Node.js 20+ and a [Convex](https://convex.dev) account.

```bash
npm install
cp .env.example .env.local
npx convex dev            # creates a dev deployment and fills .env.local
npx convex env set SITE_URL http://localhost:3100
npx convex env set BETTER_AUTH_SECRET <random-string>
npm run dev -- -p 3100
```

Optional: set `ANTHROPIC_API_KEY` on the Convex deployment to turn on the AI features, and `ADMIN_EMAILS` to give accounts access to `/admin`.

## Scripts

| Command | What it does |
|---|---|
| `npm run dev` | Start the development server |
| `npm run build` | Production build |
| `npm test` | Run the test suite |
| `npm run typecheck` | Type-check the website |
| `npm run typecheck:convex` | Type-check the backend |
| `npm run lint` | Lint the code |

## License

© 2026 BioRefMind. All rights reserved.
