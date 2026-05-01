# Development Guide: meridian-web

General-purpose agent frontend for Meridian. Apache-2.0.

## Tech Stack

- React 19 + TypeScript
- Vite (build + dev server)
- shadcn/ui (component library)
- Zustand (state management)
- Native WebSocket (backend communication)

## Sibling Repos

- `../meridian-cli` — backend. Runs the chat/app server that this frontend connects to.
- `../prompts/meridian-base` — core agent profiles and skills
- `../prompts/meridian-dev-workflow` — dev orchestration agents

## Dev

From this repo:

```bash
pnpm install
pnpm dev
```

Or from `../meridian-cli`:

```bash
make dev       # starts both backend and frontend via portless
make frontend  # starts frontend only
```

Portless gives stable URLs: `https://app.meridian.localhost` (frontend) and `https://api.meridian.localhost` (backend).

## Backend API

The frontend communicates with the backend via REST + bidirectional WebSocket. API reference: `../meridian-cli/docs/chat.md`.

## Extension System

Third-party extensions run in sandboxed iframes. The extension SDK (`@meridian/extension-sdk`, MIT) provides types for the host bridge API. See the design docs in the shared work directory for architecture details.
