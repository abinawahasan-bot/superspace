# Architecture

> **Status:** INFERRED — Awaiting architect review before implementation.
> All technical decisions are provisional until validated by the architecture review process.

## Module Layers

### 1. Frontend (React + Vite + TypeScript + Three.js)
**Confidence:** CONFIRMED (stack), INFERRED (structure)

```
src/
├── app/              — App shell, routing, providers
├── pages/            — Route-level components (Lobby, Game, Wallet, Auth)
├── components/
│   ├── game/         — Three.js crash visualization
│   ├── ui/           — Shared UI components
│   └── wallet/       — Balance, deposit, withdrawal UI
├── hooks/            — Custom React hooks
├── store/            — State management (likely Zustand or Context API) [ASSUMPTION]
├── services/         — API client services
├── types/            — TypeScript type definitions
└── utils/            — Utility functions
```

### 2. Backend (Go 1.23 + PostgreSQL + Stripe + JWT)
**Confidence:** CONFIRMED (stack), INFERRED (structure)

```
internal/
├── api/              — HTTP API layer (handlers, middleware)
├── game/             — Crash game engine, provably-fair logic
├── wallet/           — Internal wallet + Stripe integration
├── auth/             — JWT authentication, password hashing
├── user/             — User management
├── config/           — Configuration management
├── db/               — Database migrations, queries
└── middleware/       — Auth, CORS, rate limiting
```

## Dependency Flow
Frontend -- HTTP/HTTPS --> Backend API -- SQL --> PostgreSQL
Backend -- API --> Stripe
Backend -- JWT --> Frontend

[INFERRED — needs architect validation]

## Data Flow Summary

### Game Lifecycle
1. User creates/joins game session via API.
2. Server generates seed, sends commit hash to client (before bet).
3. User places bet (from internal wallet or demo credits).
4. Server reveals seed after crash multiplier is determined.
5. Payout calculated based on provably-fair algorithm.
6. Wallet updated; transaction recorded.

### Payment Flow
1. User requests deposit via Stripe Checkout.
2. Stripe webhook confirms payment.
3. Backend credits internal wallet.
4. User plays with real money or demo credits.

[INFERRED — payment flow requires user approval before implementation]

## Open Architecture Concerns
| # | Concern                          | Status     | Owner     |
|---|----------------------------------|------------|-----------|
| 1 | WebSocket vs HTTP for game sync  | UNKNOWN    | Architect |
| 2 | Three.js rendering performance    | ASSUMPTION | Architect |
| 3 | Database schema for game history | ASSUMPTION | Architect |
| 4 | Rate limiting strategy           | UNKNOWN    | Architect |
| 5 | JWT token refresh mechanism      | ASSUMPTION | Architect |
| 6 | Stripe webhook idempotency       | INFERRED   | Architect |
| 7 | Provably-fair seed storage       | ASSUMPTION | Architect |
| 8 | Session management architecture  | UNKNOWN    | Architect |

## Confidence Legend
| Level      | Meaning                                                          |
|------------|-----------------------------------------------------------------|
| CONFIRMED  | User-stated fact from README.md or direct instruction.          |
| INFERRED   | Derived from confirmed facts or standard industry practice.    |
| ASSUMPTION | Reasonable guess; no user research conducted.                   |
| UNKNOWN    | Known to be unknown; requires investigation or decision.       |