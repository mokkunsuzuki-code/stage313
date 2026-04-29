# Stage311 REMEDA Sigstore Real Verification

Stage311 introduces **real Sigstore verification** into REMEDA Trust Score.

---

## Core Concept

Before Stage311:

sigstore = declared (true / false)

After Stage311:

sigstore = verified (cosign verify-blob)

---

## What Stage311 Adds

- Real Sigstore verification (cosign verify-blob)
- Signature bundle verification
- Public key based validation
- Fail-closed behavior for invalid signatures
- Integration into Trust Score

---

## Trust Model

Trust Score = average(
  integrity,
  execution,
  identity,
  time,
  sigstore (real verification)
)

---

## Sigstore Verification

The system runs:

cosign verify-blob

and evaluates:

- signature validity
- bundle integrity
- public key verification

---

## Decision Policy

trust_score >= 0.85 → accept  
trust_score >= 0.45 → pending  
trust_score < 0.45 → reject  

Fail-closed is enabled.

---

## Why This Matters

Stage310 made trust visible and shareable.

Stage311 makes trust **real and cryptographically verifiable**.

This transforms REMEDA from a visualization tool into a **verifiable trust system**.

---

## Run

pip install -r requirements.txt  
python app.py  

http://127.0.0.1:3110

---

## API

POST /api/verify  
GET /api/trust/<id>

---

## Security Notes

- cosign.key is never committed
- verification uses public key (cosign.pub)
- signature bundle (artifact.bundle) is verifiable

---

## Next Stage

Stage312 introduces API Key and SaaS monetization.

---

## License

MIT License

Copyright (c) 2025 Motohiro Suzuki
