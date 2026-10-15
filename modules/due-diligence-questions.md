# Due-Diligence Questions

## Purpose

Due diligence should concentrate on assumptions capable of changing the decision.

Generic questionnaires create volume. Good due diligence creates evidence.

## Architecture

- What is the actual deployment and tenancy model?
- Which components are supplier-managed and which remain ours?
- Which interfaces are contractual/stable and which are implementation details?
- What limits exist on throughput, concurrency, storage or API usage?
- Which dependencies become ours during an outage or degraded mode?
- How are backward compatibility and breaking changes handled?

## Data

- Where is authoritative data held?
- How is data exported in bulk?
- What metadata, history and relationships are lost on export?
- What are deletion and retention behaviours?
- How are backups restored and tested?

## Resilience and operations

- What failure modes sit outside the headline SLA?
- How are incidents communicated and escalated?
- What evidence exists for recovery performance?
- What must our operators do during a supplier incident?
- Which diagnostics are exposed to customers?

## Security and control

- How are identities, privileges and service accounts managed?
- Which controls are configurable versus fixed?
- What audit evidence can be exported and retained?
- How are vulnerabilities and urgent patches handled?
- Which subcontractors or services form part of the control boundary?

## Change

- Which changes can the supplier make without customer approval?
- How are deprecations announced?
- What is the practical upgrade burden?
- Can we test future versions before production change?

## Commercial

- Which technical actions trigger additional charges?
- How does price change with realistic growth?
- Which minimum commitments survive a reduction in use?
- What support, environment or integration charges sit outside the headline price?

## Exit

- What can be exported, in which format and within what timeframe?
- Which configuration or workflow must be rebuilt?
- What assistance is provided during transition?
- Which rights survive termination?
- How long is data retained after termination and how is deletion evidenced?

## Supplier evidence

For any answer that materially affects the decision ask:

> **What evidence would allow us to rely on this answer?**

A useful answer may be a test, contract clause, architecture document, service report, customer reference or observed demonstration. The correct evidence depends on the claim.
