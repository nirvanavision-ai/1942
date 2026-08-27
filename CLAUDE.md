# Project: The Don Julio 1942 Pour Meter

## Tech Stack

- Frontend: Next.js (App Router, Strict TypeScript)
- Styling: Tailwind CSS
- 3D/Graphics: Three.js / WebGL
- Animation Orchestration: GSAP + Framer Motion
- Audio: Native Web Audio API
- Data Persistence: IndexedDB (local-first) -> Supabase

## Luxury UI/UX Conventions

- **Visual Aesthetic:** DO NOT use plain white backgrounds or standard generic boxes. Default to an ultra-luxe dark mode (deep obsidian, amber gold, metallic finishes).
- **Layouts:** Use high-end bento-box grid layouts with heavy, moody shadows and frosted glass filters.
- **Component Rules:** Default to React Server Components for performance. Strictly isolate all Three.js, GSAP, and Web Audio API logic into Client Components (`"use client"`).
- **Animation Routing:** Use Framer Motion for simple UI spring physics (modals, task cards). Use GSAP exclusively for sequencing complex timelines (e.g., the exact sequence of card snap -> cork pop -> pour -> crystal clink).

## Product Mechanics (the source of truth for behavior)

- The day is one bottle. Every task planned today is an equal share of 100%.
- Tasks live inside **time blocks**; a block's end time is a hard deadline.
- Completing a task **pours** its share in. A block closing on unfinished work
  **spills** those shares — spilled shares can never be re-poured.
- **Last call** fires 15 minutes before a block closes with work outstanding.
- Rewards: gauge tiers, a full-bottle fanfare, a 7-day Cellar shelf, and a
  streak for days ending at or above 80%.
- Deadlines missed while the app was closed are settled retroactively on load.

## Repository Layout

- `prototype/index.html` — the shipped zero-dependency prototype: raw WebGL
  lathe bottle, world-horizontal liquid plane with spring-damper slosh,
  synthesized Web Audio SFX, LocalStorage persistence. It is the **reference
  implementation** for mechanics, shaders, and sound. Port from it; never
  restart from zero.
- The Next.js app scaffolds at the repository root (`app/`, `src/`, `public/`).
  Do not create anything named `app/` for other purposes.

## Legal Guardrail

The bottle silhouette, label, and mark must stay original. "1942" is used as a
number. Never reproduce Diageo's Don Julio wordmark, logo, or trade dress —
_Hermès v. Rothschild_ settled that "it's art" is not a defense.
