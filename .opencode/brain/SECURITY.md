# Security Model

> **Status:** INFERRED — Awaiting security review before implementation.
> All secrets must be stored in environment variables. Never commit secrets.

## Authentication
| Aspect            | Approach                        | Confidence |
|-------------------|---------------------------------|------------|
| Primary auth      | Username/password + JWT         | CONFIRMED  |
| Password storage  | bcrypt/argon2 hash (never plain) | INFERRED  |
| Token type        | JWT (access + refresh)          | INFERRED   |
| Token storage     | httpOnly cookie or secure storage | ASSUMPTION |

## Threat Model
| # | Threat                          | Likelihood | Impact | Mitigation                      |
|---|---------------------------------|------------|--------|---------------------------------|
| 1 | SQL injection                   | MEDIUM     | HIGH   | Parameterized queries           |
| 2 | XSS                             | MEDIUM     | HIGH   | CSP, input sanitization         |
| 3 | CSRF                            | MEDIUM     | MEDIUM | CSRF tokens                     |
| 4 | JWT theft                       | MEDIUM     | HIGH   | Short expiry, httpOnly, HTTPS   |
| 5 | Stripe webhook forgery          | LOW        | HIGH   | Signature verification          |
| 6 | Wallet manipulation             | LOW        | CRITICAL | Server-side validation, ACID   |
| 7 | Provably-fair seed tampering    | LOW        | CRITICAL | Commit-reveal, immutable log   |
| 8 | Brute force login               | MEDIUM     | MEDIUM | Rate limiting, lockout          |
| 9 | DDoS                            | MEDIUM     | HIGH   | Rate limiting, CDN              |
| 10| Insider abuse                   | LOW        | HIGH   | Audit logging, least privilege  |

## Secrets Management
- All secrets via environment variables. [CONFIRMED — policy]
- Stripe keys: STRIPE_SECRET_KEY, STRIPE_WEBHOOK_SECRET. [CONFIRMED — placeholder names]
- JWT signing key: JWT_SECRET. [CONFIRMED — placeholder name]
- Database credentials: DATABASE_URL. [CONFIRMED — placeholder name]
- **Never** commit actual secret values to the repository.

## Data Classification
| Data Type        | Classification | Storage                          |
|------------------|----------------|----------------------------------|
| Passwords        | SECRET         | Hashed (bcrypt/argon2)           |
| JWT tokens       | SENSITIVE      | Client secure storage            |
| Wallet balances  | CONFIDENTIAL   | PostgreSQL (encrypted at rest)   |
| Game history     | INTERNAL       | PostgreSQL                       |
| Payment data     | RESTRICTED     | Stripe (PCI DSS compliant)       |
| Personal data    | CONFIDENTIAL   | PostgreSQL (GDPR/CCPA compliant) |

## Approval Requirements
- All payment, wallet, fairness, and auth engineering decisions require explicit user approval. [CONFIRMED]

## Confidence Legend
| Level      | Meaning                                                          |
|------------|-----------------------------------------------------------------|
| CONFIRMED  | User-stated fact from README.md or direct instruction.          |
| INFERRED   | Derived from confirmed facts or standard industry practice.    |
| ASSUMPTION | Reasonable guess; no user research conducted.                   |
| UNKNOWN    | Known to be unknown; requires investigation or decision.       |