# Goals & OKRs

## Strategic Objectives

| # | Objective                                         | Key Result                          | Confidence | Approval Gate |
|---|---------------------------------------------------|-------------------------------------|------------|---------------|
| 1 | Deliver provably-fair crash game (MVP)            | Game engine with SHA-256 commit-reveal working | INFERRED  | User, Product |
| 2 | Enable real-money betting via Stripe              | Deposit → play → withdraw cycle functional | INFERRED | User          |
| 3 | Build transparent, auditable fairness system       | Third-party can verify game outcomes  | INFERRED   | User          |
| 4 | Achieve engaging 3D gameplay experience           | Three.js crash animation at 60fps     | INFERRED   | Architect     |
| 5 | Ensure regulatory compliance (responsible gambling) | Deposit limits, self-exclusion implemented | ASSUMPTION | User       |
| 6 | Establish secure auth & wallet infrastructure     | JWT auth + internal wallet ACID-compliant | INFERRED | User, Architect |

## OKRs

### OKR-1: Ship MVP Crash Game
**Confidence:** INFERRED
- KR1: Game lobby with bet placement UI ✓
- KR2: Crash multiplier visualization (Three.js) ✓
- KR3: SHA-256 commit-reveal provably-fair flow ✓
- KR4: Demo credit mode fully functional ✓

### OKR-2: Real-Money Integration
**Confidence:** INFERRED
- KR1: Stripe deposit → wallet credit ✓
- KR2: Stripe withdrawal → wallet debit ✓
- KR3: Webhook idempotency & fraud detection ✓
- **GATE:** Requires explicit user approval before implementation.

### OKR-3: Fairness Verification
**Confidence:** INFERRED
- KR1: Client can verify server seed (commit-reveal) ✓
- KR2: Historical game hash lookup API ✓
- KR3: Provable fair verification tool (client-side) ✓

### OKR-4: Responsible Gambling
**Confidence:** ASSUMPTION
- KR1: Daily/weekly/monthly deposit limits ✓
- KR2: Loss limits & self-exclusion ✓
- KR3: Cooling-off periods ✓
- **GATE:** Requires explicit user approval.

### OKR-5: Performance & Security
**Confidence:** INFERRED
- KR1: 60fps crash animation (Three.js) ✓
- KR2: JWT token expiry ≤ 15min, refresh ≤ 24h ✓
- KR3: API rate limiting enforced ✓

## Gate-Level Success Criteria

| Gate                    | Criteria                              | Approval Required |
|-------------------------|---------------------------------------|-------------------|
| Product Ready (MVP)     | All OKR-1 KRs met                     | Product          |
| Payment Ready           | All OKR-2 KRs met                     | User             |
| Fairness Ready          | All OKR-3 KRs met                     | User             |
| Responsible Gambling    | All OKR-4 KRs met                     | User             |
| Performance Ready       | All OKR-5 KRs met                     | Architect        |

## Confidence Legend
| Level      | Meaning                                                          |
|----------------|-----------------------------------------------------------------|
| CONFIRMED    | User-stated fact from README.md or direct instruction.          |
| INFERRED     | Derived from confirmed facts or standard industry practice.    |
| ASSUMPTION   | Reasonable guess; no user research conducted.                   |
| UNKNOWN      | Known to be unknown; requires investigation or decision.       |