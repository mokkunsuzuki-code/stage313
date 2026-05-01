Stage313 REMEDA Signed Responsibility

Stage313 introduces **cryptographic responsibility** into REMEDA.

The verification result is no longer just computed.

It is explicitly approved and signed by a human.

---

## Core Concept

Before Stage313:

- decision = system output
- no explicit human responsibility

After Stage313:

- decision + signature = accountable approval
- the result is cryptographically bound to the signer

---

## Signed Statement

"I approve this verification result as accept."

This statement is **digitally signed**.

---

## Files

- decision.json → final decision (authoritative)
- decision.json.sig → detached signature (GPG)
- signed_decision.json → signed metadata structure
- manifest.json → verification input
- verification.json → verification result

---

## How to Verify

Anyone can verify the signature locally:

```bash
gpg --verify decision.json.sig decision.json

Expected output:

Good signature from "Motohiro Suzuki"
Security Model
The signature cannot be forged without the private key
The decision cannot be altered without breaking verification
Anyone can independently verify the result
Responsibility is explicit and non-repudiable
Responsibility Model

Stage313 introduces a critical shift:

The system computes the result
A human explicitly approves it
The approval is cryptographically signed

This establishes:

Accountability
Non-repudiation
Verifiable human intent
Stage Position
Stage312 → Sellable verification (API)
Stage313 → Signed responsibility ← current stage
Stage314 → Public verification URL (next)
Why This Matters

Verification alone is not enough.

To be trusted in real-world systems:

Someone must take responsibility
That responsibility must be provable

Stage313 makes responsibility:

Visible
Verifiable
Immutable
License

MIT License (2025)

This project is released under the MIT License.
You are free to use, modify, and distribute this software.

See the LICENSE file for details.

Summary

Stage313 transforms verification into responsibility.

It ensures that:

A decision is not just generated
It is explicitly approved
It is cryptographically proven
It is globally verifiable
Author

Motohiro Suzuki