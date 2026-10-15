# Vendor Claim vs Evidence

## Purpose

Important sourcing decisions often turn on statements that sound precise but are not yet decision-grade evidence.

Examples:

- "portable";
- "highly available";
- "AI-ready";
- "low-code";
- "open";
- "easy to integrate";
- "enterprise support";
- "predictable pricing".

The method is simple: turn the statement into a testable claim and preserve the gap between what is known and what is merely asserted.

## Claim structure

For each material claim record:

| Field | Question |
|---|---|
| Claim | What exactly is being asserted? |
| Decision affected | Why does it matter? |
| Evidence required | What would constitute proof? |
| Evidence source | Demo, test, reference, contract, documentation, benchmark? |
| Status | Proven, partly proven, inferred, unknown, contradicted? |
| Residual uncertainty | What still has to be accepted? |

## Example

Claim:

> "Workflows are portable if Bafflewick later leaves the platform."

Weak evidence:

> Supplier presentation states that configuration can be exported.

Better evidence:

- export format documented;
- Bafflewick exports a configured workflow;
- exported artefact is inspected;
- dependencies on proprietary runtime services are identified;
- re-import or translation path is demonstrated;
- commercial right to export is confirmed.

The answer may still be "portable enough". The point is to know what that means.

## Rules

1. Test claims that could change the decision.
2. Do not spend equal effort on immaterial claims.
3. Prefer direct evidence over adjectives.
4. Separate product capability from capability in your architecture.
5. Record uncertainty instead of hiding it in a score.
6. Treat reference customers as evidence of their context, not automatically yours.

See [`../templates/vendor-evidence-matrix.md`](../templates/vendor-evidence-matrix.md).
