# Requirements Register

> **Status:** CONFIRMED facts from README.md; derived content is INFERRED.
> Cross-references Project Brain ARCHITECTURE.md and SECURITY.md.

## Confidence Legend
| Level      | Meaning                                                          |
|------------|-----------------------------------------------------------------|
| CONFIRMED  | User-stated fact from README.md or direct instruction.          |
| INFERRED   | Derived from confirmed facts or standard industry practice.    |
| ASSUMPTION | Reasonable guess; no user research conducted.                   |
| UNKNOWN    | Known to be unknown; requires investigation or decision.       |

## Functional Requirements

| ID       | Requirement                                                    | Source      | Confidence | Approval Gate |
|----------|----------------------------------------------------------------|-------------|------------|---------------|
| FR-001   | Backend must be implemented in Go 1.23                        | README.md   | CONFIRMED  | Architect     |
| FR-002   | Database must use PostgreSQL                                  | README.md   | CONFIRMED  | Architect     |
| FR-003   | Payment processing must integrate with Stripe                 | README.md   | CONFIRMED  | User          |
| FR-004   | Authentication must use JWT tokens                            | README.md   | CONFIRMED  | User          |
| FR-005   | Game fairness must use SHA-256 commit-reveal                  | README.md   | CONFIRMED  | User          |
| FR-006   | Frontend must use React + Vite + TypeScript + Three.js        | README.md   | CONFIRMED  | Architect     |
| FR-007   | Auth must support username/password registration              | README.md   | CONFIRMED  | User          |
| FR-008   | Internal wallet must support demo credits                     | README.md   | CONFIRMED  | User          |
| FR-009   | Demo credits must be convertible to real money via Stripe     | README.md   | CONFIRMED  | User          |
| FR-010   | Game must implement crash multiplier mechanics                | INFERRED    | Product    |
| FR-011   | Game must support real-time multiplayer sessions               | ASSUMPTION  | Product    |
| FR-012   | Betting must support configurable bet amounts                  | INFERRED    | User       |

## Non-Functional Requirements

| ID       | Requirement                                                    | Source      | Confidence | Approval Gate |
|----------|----------------------------------------------------------------|-------------|------------|---------------|
| NFR-001  | System must handle real-money transactions securely (PCI DSS) | ASSUMPTION  | User       |
| NFR-002  | Game fairness must be auditable via provably-fair verification | INFERRED  | User       |
| NFR-003  | JWT tokens must have secure expiration & refresh                | INFERRED   | Architect  |
| NFR-004  | System must validate all user input                            | ASSUMPTION  | Architect  |
| NFR-005  | Database must support ACID transactions                        | INFERRED   | Architect  |
| NFR-006  | Frontend must render 3D crash visualization at 60fps           | INFERRED   | Architect  |
| NFR-007  | API must enforce rate limiting                                 | ASSUMPTION  | Architect  |
| NFR-008  | System must log all game events for audit                      | INFERRED   | User       |

## Product Requirements (to be detailed in Product Brain)

| ID       | Requirement                                                    | Source      | Confidence | Approval Gate |
|----------|----------------------------------------------------------------|-------------|------------|---------------|
| PRD-001  | Crash game must have configurable house edge (default ~1-3%)   | ASSUMPTION | User       |
| PRD-002  | Game must support auto-cash-out at configurable multiplier      | INFERRED   | Product    |
| PRD-003  | Game must support auto-bet/auto-play mode                       | INFERRED   | Product    |
| PRD-004  | Betting limits must be configurable per user tier                | ASSUMPTION | User       |
| PRD-005  | RTP (Return to Player) must be target ~97%                      | ASSUMPTION | User       |
| PRD-006  | Game history must be queryable                                  | INFERRED   | Product    |
| PRD-007  | Responsible gambling controls required (deposit/loss limits)   | ASSUMPTION | User       |

## Approval Gates
- **User:** All payment, wallet, fairness, and auth engineering decisions.
- **Architect:** All technical implementation decisions.
- **Product:** Feature scope and mechanics.