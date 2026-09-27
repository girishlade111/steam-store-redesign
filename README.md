# Steam Store Redesign

A concept redesign of the Steam storefront, originally generated with [v0.app](https://v0.app). It's a modern, dark-themed game-store UI built with Next.js — featuring a hero carousel, game catalog with discounts, special offers, category browsing, a search dialog, and a detailed game page — all as a static, client-side demo.

## What It Does

- **Storefront homepage** — hero carousel of featured titles, game cards with prices/discounts/ratings, special-offer cards, and category tiles.
- **Game detail page** (`/game/[slug]`) — demo page with screenshots carousel, tabs (About / Reviews / Specs), price box, system requirements, tags and ratings.
- **Search dialog** — quick in-app search overlay (Cmd+K style).
- **Dark/light theme toggle** with an animated background on the homepage.
- All data is hardcoded mock data in the components — a pure UI demo, no backend or Steam API.

## Features

- Hero carousel with featured games and autoplay
- Game cards: price, discount badge, star rating, player counts, tags
- Special offers section with discount countdowns
- Category cards (Action, RPG, Strategy, etc.)
- Game detail page: image carousel, review tabs, system-requirements tables
- Command-style search dialog + mobile menu
- Dark/light theme via `next-themes`
- Framer Motion animations, Embla carousels, shadcn/ui primitives

## Tech Stack

- **Framework:** Next.js 15 (App Router, static export) + React 19 + TypeScript
- **UI:** shadcn/ui, Radix UI primitives, Tailwind CSS 3, `lucide-react` icons
- **Animation/carousels:** Framer Motion, `embla-carousel-react`
- **Forms/state:** React Hook Form + Zod (available), Recharts (available)
- **Package manager:** pnpm (lockfile committed); npm works too

## Quick Start

```bash
# clone
git clone https://github.com/girishlade111/steam-store-redesign.git
cd steam-store-redesign

# install (pnpm recommended; npm --legacy-peer-deps also works)
pnpm install
# or: npm install --legacy-peer-deps

# run locally
pnpm dev
# open http://localhost:3000
```

Open a game detail page via the game cards (e.g. `/game/elden-ring`).

## Project Structure

```
app/
  page.tsx              # Storefront homepage (mock game data)
  game/[slug]/page.tsx  # Game detail demo page
  loading.tsx           # Route loading skeleton
components/
  hero-carousel.tsx     # Featured-games carousel
  game-card.tsx         # Catalog card (price, discount, rating)
  special-offer-card.tsx
  category-card.tsx
  search-dialog.tsx     # Quick-search overlay
  animated-background.tsx
  ui/                   # shadcn/ui primitives
next.config.mjs         # Static export config
```

## Environment Variables

None — everything is local mock data; no API keys or secrets needed.

## Deployment

The app is statically exported (`output: "export"` in `next.config.mjs`):

- **GitHub Pages:** this repo is published via the `gh-pages` branch → live at `https://girishlade111.github.io/steam-store-redesign/`
  - Note: `basePath: '/steam-store-redesign'` is set for the subpath deploy. Remove `basePath` (keep `output: 'export'`) when deploying to a root domain or Vercel.
- **Vercel / Netlify / Cloudflare Pages:** `pnpm build` produces `out/` — point your host at it.

## License

UI concept demo for educational purposes. Steam is a trademark of Valve Corporation — this is an unofficial redesign mockup, not affiliated with Valve.

---

Built by Girish Lade — [ladestack.in](https://ladestack.in)
