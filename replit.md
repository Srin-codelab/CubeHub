# CubeHub - Speedcubing Web Application

## Overview
CubeHub is a comprehensive speedcubing web application featuring a timer with WCA-standard inspection mode, an algorithm library, and practice features. Works on both desktop and mobile.

## Recent Changes
- 2026-02-07: Added complete 2x2 Ortega algorithm set (7 OLL + 5 PBL cases with dual images for PBL)
- 2026-02-07: Added OLL/PBL filter buttons to 2x2 section
- 2026-02-07: Made algorithm cards larger with vertical layout for better readability

## User Preferences
- Algorithms must match official reference images exactly
- Algorithm detail pages show case image and algorithm sequence
- Logo rotates on both hover (desktop) and touch (mobile) using onTouchStart
- Changed terminology from "sequence" to "algorithm"
- PBL cases show both layer images side by side
- No "All" filter option — only relevant categories per method

## Project Architecture
- **Frontend**: React + Vite + Tailwind CSS + shadcn/ui + Framer Motion
- **Routing**: wouter
- **Backend**: Express (minimal, mostly frontend-focused)
- **Database**: PostgreSQL with Drizzle ORM

### Key Pages
- `client/src/pages/home.tsx` - Landing page
- `client/src/pages/timer.tsx` - Timer with inspection mode and session management
- `client/src/pages/learn.tsx` - Algorithm library with multi-level navigation
- `client/src/pages/algorithms/[id].tsx` - Algorithm detail page

### Algorithm Library Structure
- Home → Cube Type (3x3/2x2) → Method (CFOP/Ortega) → Algorithm list with filters
- 3x3 CFOP: 10 OLL + 6 PLL cases
- 2x2 Ortega: 7 OLL + 5 PBL cases
- PBL cases support multiple images (both layers shown)
- Algorithm data is duplicated in learn.tsx and [id].tsx (detail page needs its own copy)

### Image Assets
- All algorithm images stored in `attached_assets/` directory
- Referenced via `@assets/` alias which maps to `attached_assets/`
