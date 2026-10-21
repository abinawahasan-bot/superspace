# Discovery Summary

> **Pipeline Stage:** PRODUCT_DISCOVERY
> **Status:** Complete — findings are INFERRED/ASSUMPTION pending user validation.

## Discovery Outputs

| Artifact               | File                  | Confidence | Status      |
|------------------------|-----------------------|------------|-------------|
| Personas               | PERSONAS.md           | ASSUMPTION | ✅ Draft    |
| Jobs-to-be-Done        | JTBD.md               | INFERRED   | ✅ Draft    |
| Problem Statements     | PROBLEMS.md           | INFERRED   | ✅ Draft    |
| Opportunity Map        | OPPORTUNITY_MAP.md    | INFERRED   | ✅ Draft    |
| Open Questions         | OPEN_QUESTIONS.md     | CONFIRMED  | ✅ Active   |

## Key Insights

### Problems Identified
1. Players distrust crash game fairness — need provable verification. [INFERRED]
2. Friction between demo and real-money modes — need seamless wallet. [INFERRED]
3. Complex payout calculations — need transparent, automated systems. [INFERRED]

### Personas
1. Alex — casual gambler, demo-first. [ASSUMPTION]
2. Sam — high-roller, real-money primary. [ASSUMPTION]
3. Morgan — admin, fairness oversight. [ASSUMPTION]

### Opportunities
1. SHA-256 commit-reveal as differentiation. [CONFIRMED]
2. Dual wallet (demo→real) reduces friction. [CONFIRMED]
3. 3D visualization for engagement. [CONFIRMED]

## Assumptions & Known Unknowns

| # | Assumption/Unknown                             | Classification | Needs Validation |
|---|-----------------------------------------------|----------------|------------------|
| 1 | Crash multiplier algorithm uses e^(rt) formula | INFERRED      | Yes              |
| 2 | House edge target is ~1-3%                    | ASSUMPTION    | Yes (user)       |
| 3 | RTP target is ~97%                            | ASSUMPTION    | Yes (user)       |
| 4 | Betting limits per user tier                  | ASSUMPTION    | Yes (user)       |
| 5 | WebSocket for real-time game sync             | UNKNOWN       | Yes (architect)  |
| 6 | State management: Zustand vs Context API      | ASSUMPTION    | Yes (architect)  |
| 7 | Deployment platform (Docker, K8s, serverless)  | UNKNOWN       | Yes (architect)  |
| 8 | Multiplayer support required                  | ASSUMPTION    | Yes (product)    |

## Confidence Legend
| Level      | Meaning                                                          |
|----------------|-----------------------------------------------------------------|
| CONFIRMED    | User-stated fact from README.md or direct instruction.          |
| INFERRED     | Derived from confirmed facts or standard industry practice.    |
| ASSUMPTION   | Reasonable guess; no user research conducted.                   |
| UNKNOWN      | Known to be unknown; requires investigation or decision.       |