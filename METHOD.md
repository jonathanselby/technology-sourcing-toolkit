# Method

## Purpose

This method is for technology choices where technical design, operating responsibility and commercial structure are tightly coupled.

It is intentionally small. The aim is not to reproduce a full procurement lifecycle. The aim is to expose the assumptions that can make a technically plausible option become a poor long-term decision.

## 1. Frame the decision

Write the decision as a choice, not as a product search.

Bad:

> Select a warehouse platform.

Better:

> Decide how Bafflewick should provide warehouse routing for the next five years while reducing manual work, preserving operational resilience and avoiding an exit cost disproportionate to the capability.

Record:

- required business outcome;
- time horizon;
- hard constraints;
- material uncertainties;
- decisions already made;
- decisions deliberately still open.

## 2. Establish the technical baseline

Understand the current or target system before comparing suppliers.

At minimum identify:

- users and critical workflows;
- interfaces;
- data and state;
- deployment model;
- resilience and recovery expectations;
- security boundaries;
- volumes and growth assumptions;
- support model;
- known pain points.

For an inherited codebase, use a structured engineering baseline such as `codebase-to-edd` rather than relying on stakeholder recollection.

## 3. Define the meaningful options

Do not assume the decision is only vendor A versus vendor B.

Consider:

```text
BUILD      own the software and engineering responsibility
BUY        acquire software but retain substantial operation/control
RENT       consume a managed or SaaS capability
HYBRID     combine models where boundaries are explicit
DO NOTHING retain the current state for a defined period
```

An option belongs in the comparison only if it is plausible enough to execute.

## 4. Identify discriminating requirements

Separate mandatory requirements from preferences.

Then ask which requirements actually distinguish the options. A requirement met equally by every credible option should not dominate the decision simply because it is easy to score.

Useful discriminators often include:

- integration complexity;
- data residency/control;
- recovery requirements;
- release/change cadence;
- specialist skill dependency;
- portability;
- configuration limits;
- scale economics;
- contractual dependency;
- exit effort.

## 5. Convert claims into evidence

For each material claim:

1. write the claim precisely;
2. state which decision it affects;
3. define acceptable evidence;
4. collect the evidence;
5. classify what is proven, inferred or unknown;
6. record residual risk.

Supplier documentation is evidence of what a supplier states. It is not automatically evidence that the claim is true in your architecture.

## 6. Model the operating consequence

Ask what the organisation must do every week after implementation.

Cover:

- monitoring;
- support;
- incident ownership;
- releases;
- access administration;
- data operations;
- integration maintenance;
- supplier coordination;
- capacity/cost management;
- control evidence;
- skills and succession.

A product that reduces one class of engineering work may create another class of operational dependency.

## 7. Model commercial shape from architecture

Do not begin with quoted annual price.

Identify:

- one-off costs;
- recurring fixed costs;
- variable usage costs;
- required environments;
- resilience-related duplication;
- support tiers;
- implementation/integration;
- internal labour;
- migration;
- growth assumptions;
- renewal exposure;
- exit cost.

Test more than one usage scenario.

## 8. Assess dependency and exit

Map dependency across:

```text
DATA
INTERFACES
WORKFLOW / CONFIGURATION
IDENTITY / SECURITY
OPERATING KNOWLEDGE
PEOPLE / SKILLS
COMMERCIAL TERMS
CONTROL EVIDENCE
```

Then ask how each dependency would be removed or replaced.

The purpose is not to eliminate all lock-in. The purpose is to choose lock-in knowingly and make its consequences visible.

## 9. Run due diligence

Focus due diligence on the assumptions that could reverse the decision.

Do not ask fifty generic questions when five unresolved questions determine whether the option works.

## 10. Make the decision record

Record:

- decision;
- options considered;
- decisive evidence;
- material assumptions;
- accepted risks;
- conditions/commitments;
- exit position;
- review trigger.

A decision record should allow a future reviewer to understand why the decision was reasonable at the time.

## 11. Re-run at renewal

At renewal, replace forecast with operating evidence:

- actual usage;
- realised cost;
- incidents;
- support performance;
- integration burden;
- workarounds;
- roadmap delivery;
- switching cost;
- business dependence.

Renewal should not be an administrative extension of the original purchase.
