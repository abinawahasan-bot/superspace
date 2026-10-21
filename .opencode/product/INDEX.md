# Product Brain — Index (SUPERSPACE)

> **Owner:** Product Manager (Rampage / 9Router)
> **Pipeline Stage:** PRODUCT_DISCOVERY → PRODUCT_PLANNING
> **Status:** ACTIVE — initialization in progress

## File Registry
| File                    | Topic                      | Confidence   | Status        |
|-------------------------|----------------------------|--------------|---------------|
| INDEX.md                | Master index               | CONFIRMED    | ✅ Active     |
| VISION.md               | Vision, mission, positioning | CONFIRMED  | ✅ Active     |
| GOALS.md                | Strategic objectives & OKRs | CONFIRMED   | ✅ Active     |
| DISCOVERY.md            | Discovery summary          | INFERRED     | ✅ Active     |
| PERSONAS.md             | User personas              | ASSUMPTION   | ✅ Active     |
| JTBD.md                 | Jobs-to-be-done            | INFERRED     | ✅ Active     |
| PROBLEMS.md             | Problem statements         | INFERRED     | ✅ Active     |
| OPPORTUNITY_MAP.md      | Opportunity map            | INFERRED     | ✅ Active     |
| PRD.md                  | Product Requirements Doc   | INFERRED     | ✅ Active     |
| REQUIREMENTS.md         | Requirements register      | CONFIRMED/INFERRED | ✅ Active |
| USER_STORIES.md         | User stories + AC          | INFERRED     | ✅ Active     |
| FEATURES.md             | Feature catalog            | INFERRED     | ✅ Active     |
| BACKLOG.md              | Backlog (P0–P3)            | INFERRED     | ✅ Active     |
| PRIORITIES.md           | RICE/WSJF scoring          | INFERRED     | ✅ Active     |
| ROADMAP.md              | Release roadmap            | INFERRED     | ✅ Active     |
| TRACEABILITY.md         | Traceability matrix        | INFERRED     | ✅ Active     |
| SUCCESS_METRICS.md      | North Star & KPIs          | INFERRED     | ✅ Active     |
| FAIRNESS.md             | Provably-fair spec         | INFERRED     | ✅ Active     |
| DECISIONS.md            | Decision log               | CONFIRMED    | ✅ Active     |
| OPEN_QUESTIONS.md       | Open questions             | CONFIRMED    | ✅ Active     |
| RISK_PROFILE.md         | Risk register              | ASSUMPTION   | ✅ Active     |
| ARCHITECTURE_NOTES.md   | Architecture bridge        | INFERRED     | ✅ Active     |

## Confidence Legend
| Level      | Meaning                                                          |
|----------------|-----------------------------------------------------------------|
| CONFIRMED    | User-stated fact from README.md or direct instruction.          |
| INFERRED     | Derived from confirmed facts or standard industry practice.    |
| ASSUMPTION   | Reasonable guess; no user research conducted.                   |
| UNKNOWN      | Known to be unknown; requires investigation or decision.       |

## Project Brain Cross-Reference
| Project File            | Product Cross-Reference                       |
|-------------------------|-----------------------------------------------|
| PROJECT.md              | All product deliverables map to PROJECT.md objectives |
| STACK.md                | Stack constraints inform product decisions    |
| ARCHITECTURE.md         | Architecture_NOTES.md bridges technical decisions |
| REQUIREMENTS.md         | REQUIREMENTS.md here extends Project Brain FR/NFR |
| SECURITY.md             | FAIRNESS.md, DECISIONS.md reference security model |

## Approval Gates
| Domain               | Approval Required From                     |
|----------------------|--------------------------------------------|
| Payment/Wallet       | User (explicit sign-off)                   |
| Fairness             | User (explicit sign-off)                   |
| Auth                 | User (explicit sign-off)                   |
| Technical decisions  | Architect (review before code)             |
| Feature scope        | Product Manager                            |

## Next Actions
1. Review DISCOVERY.md → validate problem statements with stakeholders.
2. Review PROBLEMS.md → mark as CONFIRMED after user validation.
3. Review PRD.md bet limits, RTP, house edge → requires user approval.
4. Review FAIRNESS.md spec → requires user approval before implementation.
5. Dispatch to architect: validate ARCHITECTURE.md concerns.

## Last Updated: 2026-10-21

## Notes
- This directory was initialized from scratch (no prior product brain).
- Project Brain at `.opencode/brain/` contains the source of truth for CONFIRMED technical facts.
- All payment/wallet/fairness/auth decisions are APPROVAL GATE — do not proceed to engineering without user sign-off.