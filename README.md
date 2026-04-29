# Stage312 REMEDA SaaS API (Trust Verification Engine)

Stage312 turns REMEDA into a **SaaS verification system** with API Key control.

---

## Core Concept

Before Stage312:

Verification was open and unrestricted.

After Stage312:

Verification is controlled and monetizable via API Key.

---

## What Stage312 Adds

- API Key authentication
- Access control for verification requests
- SaaS-ready architecture
- Integration with:
  - Trust Score (Stage310)
  - Sigstore real verification (Stage311)
  - Policy-based decision engine

---

## Architecture

Client → API Key → Verification Engine → Decision

---

## API

### POST /api/verify

Headers:

x-api-key: your-api-key

Returns:

- decision (accept / pending / reject)
- score (0.0 - 1.0)
- sigstore_verified
- breakdown

---

## Example

curl -X POST http://127.0.0.1:3120/api/verify \
-H "x-api-key: test-key-123"

---

## Decision Model

trust_score >= 0.85 → accept  
trust_score >= 0.45 → pending  
trust_score < 0.45 → reject  

Fail-closed is enabled.

---

## Why This Matters

Stage310 → visible trust  
Stage311 → verifiable trust  
Stage312 → monetizable trust  

This transforms REMEDA into a **trust infrastructure service**.

---

## Security

- cosign.key is never committed
- verification uses public key
- Sigstore verification enforced

---

## Next Stage

Stage313 introduces public endpoint deployment and external access.

---

## License

MIT License

Copyright (c) 2025 Motohiro Suzuki
