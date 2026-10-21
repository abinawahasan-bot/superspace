# Technology Stack

## Backend (CONFIRMED — from README.md)
| Component     | Technology     | Notes                                  |
|---------------|----------------|----------------------------------------|
| Language      | Go 1.23        | Primary backend language               |
| Database      | PostgreSQL     | Persistence layer                      |
| Payments      | Stripe         | Real-money deposits/withdrawals        |
| Auth          | JWT            | Session tokens                         |
| Fairness      | SHA-256        | Commit-reveal provably fair algorithm  |

## Frontend (CONFIRMED — from README.md)
| Component     | Technology     | Notes                                  |
|---------------|----------------|----------------------------------------|
| Framework     | React          | UI framework                           |
| Build         | Vite           | Build tool                             |
| Language      | TypeScript     | Type-safe JavaScript                   |
| 3D Rendering  | Three.js       | Crash multiplier visualization         |

## Authentication (CONFIRMED — from README.md)
| Mechanism     | Provider       | Notes                                  |
|---------------|----------------|----------------------------------------|
| Primary       | Username/Password | User account registration          |
| Wallet        | Internal       | Demo credits + real money via Stripe   |

## Deployment (INFERRED)
| Layer         | Technology     | Notes                                  |
|---------------|----------------|----------------------------------------|
| Hosting       | INFERRED — likely Docker/Kubernetes or serverless | Architecture review pending |
| CI/CD         | INFERRED — likely GitHub Actions | Not yet configured          |

## Confidence Legend
| Level      | Meaning                                                          |
|------------|-----------------------------------------------------------------|
| CONFIRMED  | User-stated fact from README.md or direct instruction.          |
| INFERRED   | Derived from confirmed facts or standard industry practice.    |
| ASSUMPTION | Reasonable guess; no user research conducted.                   |
| UNKNOWN    | Known to be unknown; requires investigation or decision.       |