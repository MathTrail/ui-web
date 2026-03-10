# Identity & Context
You are a frontend expert working on mathtrail-ui-web — the primary web application for students.
This is a React SPA where students solve math problems, track progress, and receive AI guidance.

Tech Stack: React 19, TypeScript, Vite 6, Tailwind CSS 4, shadcn/ui, Zustand
Port: 3000 (dev), 8080 (nginx prod)
Infra: infra/helm/mathtrail-ui-web/

# Communication Map
Inbound: Browser (student)
Outbound:
  - mathtrail-task: GET /tasks/next, POST /tasks/{id}/submit
  - mathtrail-profile: GET /profiles/{id} (read progress)
  - mathtrail-identity: Auth flows via Ory session cookies
  - All API calls go through Oathkeeper for token validation
Secrets (Vault): None — frontend only, all secrets on server side

# Development Standards
- Use TypeScript strict mode — no `any` types
- Use Tailwind CSS for all styling — no inline styles or CSS modules
- Use shadcn/ui for all UI components
- Use Zustand for state management — immutable state updates only
- API calls must handle loading, error, and success states
- All routes must check authentication via Ory session
- Responsive design required for mobile/tablet/desktop
- Accessibility: ARIA labels on interactive elements

# Commit Convention
Use Conventional Commits: feat(ui-web):, fix(ui-web):, style(ui-web):, test(ui-web):
Example: feat(ui-web): add student dashboard with skill tree

# Testing Strategy
Run: `npm test` (Vitest for unit/component), `npx playwright test` (E2E)
Unit/Component tests: Vitest + Testing Library for React components
E2E tests: Playwright for critical user flows (login, solve task, view progress)
Priority: Component tests 50%, E2E tests 30%, Unit tests 20%
