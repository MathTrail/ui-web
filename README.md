# mathtrail-ui-web
Primary web application for students — interactive interface for solving math olympiad problems, tracking progress, and receiving AI guidance.

## Mission & Responsibilities
- Student dashboard (progress, XP, skill tree)
- Task solving interface (problem display, answer input, hints)
- Real-time feedback on submissions
- Learning path visualization
- Settings and profile management

## Tech Stack
- **Framework**: React 19, TypeScript
- **Build**: Vite 6
- **Styling**: Tailwind CSS 4, shadcn/ui
- **State**: Zustand
- **API**: REST via fetch/axios, authenticated via Ory session cookies

## API & Communication
- **Outbound**: mathtrail-task (get/submit tasks), mathtrail-profile (read progress), mathtrail-identity (auth flows)
- All API calls go through Oathkeeper for token validation

## Data Persistence
- **None** — frontend only. All state on server side.

## Infrastructure
Standard `infra/` layout. Dockerfile: Node builder → nginx alpine.

## Development
- `npm run dev` — Vite dev server (port 3000)
- `npm run build` — production build

## Roadmap
1. Build student dashboard with XP/level display and skill tree
2. Implement task solving page (problem render, answer input, feedback)
3. Add real-time progress tracking with Zustand store
