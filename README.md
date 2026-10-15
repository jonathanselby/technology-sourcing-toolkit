# Technology Sourcing Toolkit

**Lightweight tools for making technology sourcing decisions where architecture, operations and commercial terms interact.**

Technology buying decisions are architecture decisions with a contract attached.

A technically attractive product can still be a poor choice if it creates an operating model the organisation cannot sustain, moves critical knowledge outside the firm, makes exit prohibitively hard, or prices badly at the scale the architecture requires. The reverse is also true: the cheapest commercial offer can be expensive once integration, migration, resilience, people, controls and exit are included.

This repository provides a small method for examining those questions together rather than handing them to separate teams and reconciling the answers at the end.

## The core test

> **What must be true for this option to remain a good decision after the sales process is over?**

That question forces the evaluation beyond feature lists and headline price.

A credible technology sourcing decision should be able to explain:

- what problem is actually being solved;
- which requirements materially distinguish the options;
- what evidence supports important supplier claims;
- what architecture and operating model each option creates;
- where knowledge, control and dependency will sit;
- what the full commercial shape looks like at realistic usage;
- how the organisation changes course if the decision proves wrong.

## Decision model

```text
BUSINESS NEED / CONSTRAINTS
            |
            v
   ARCHITECTURE BASELINE
            |
            v
 OPTIONS: BUILD / BUY / RENT
            |
            v
 +-------------------------------+
 | technical fit                 |
 | operating fit                 |
 | evidence quality              |
 | commercial shape              |
 | dependency / lock-in          |
 | exit / reversibility          |
 +-------------------------------+
            |
            v
      DUE DILIGENCE
            |
            v
       DECISION RECORD
            |
            v
     REVIEW AT RENEWAL
```

See [`METHOD.md`](METHOD.md) and [`decision-flow.txt`](decision-flow.txt).

## Modules

### 1. Vendor claim vs evidence

Turn important supplier statements into claims that can be tested.

A claim such as *"the platform is highly portable"* is not evidence. The module separates the claim, the decision it affects, the proof required, the source of that proof, and the residual uncertainty.

See [`modules/vendor-claim-vs-evidence.md`](modules/vendor-claim-vs-evidence.md).

### 2. Build / buy / rent

Compare three different ownership models rather than treating them as interchangeable implementation choices.

The method looks at differentiation, time, capability, operating burden, change rate, integration, economics, control and exit.

See [`modules/build-buy-rent.md`](modules/build-buy-rent.md).

### 3. SaaS renewal review

A renewal is a fresh sourcing decision with better evidence than the original purchase.

Usage, incidents, workarounds, integration cost, support experience, price movement and switching cost should replace assumptions made during the first sales cycle.

See [`modules/saas-renewal-review.md`](modules/saas-renewal-review.md).

### 4. Lock-in and exit

Lock-in is not a binary property of a product. It is the accumulated cost of moving data, interfaces, operating knowledge, controls, workflow and people away from a dependency.

See [`modules/lock-in-exit.md`](modules/lock-in-exit.md).

### 5. Commercial comparison

Compare options using the architecture they actually require, not isolated licence prices.

The module separates one-off, fixed, variable and contingent costs and makes usage assumptions visible.

See [`modules/commercial-comparison.md`](modules/commercial-comparison.md).

### 6. Due-diligence questions

Use questions that expose architecture, operating and commercial assumptions before commitment.

See [`modules/due-diligence-questions.md`](modules/due-diligence-questions.md).

## Worked example

[`examples/bafflewick-consolidated/`](examples/bafflewick-consolidated/) applies the full method to a fictional sourcing decision at **Bafflewick Consolidated Pty Ltd**.

Bafflewick needs to replace a warehouse-routing application assembled over many years from spreadsheets, scripts and manual dispatch knowledge. The example compares:

- rebuilding a small internal service;
- buying and hosting a specialist package;
- renting a SaaS platform.

The example deliberately does **not** manufacture a universal winner. It shows how different evidence and operating assumptions can change the answer.

## Reusable artefacts

- [`templates/vendor-evidence-matrix.md`](templates/vendor-evidence-matrix.md) — claims, evidence and residual uncertainty;
- [`templates/decision-record.md`](templates/decision-record.md) — compact sourcing decision record;
- [`templates/exit-plan.md`](templates/exit-plan.md) — minimum viable exit assessment;
- [`tests/decision-quality-test.md`](tests/decision-quality-test.md) — tests whether a decision is ready to approve.

## Relationship to Codebase to EDD

When the decision involves an existing application, inherited codebase or software acquisition, commercial review should not substitute for technical understanding.

Use [`codebase-to-edd`](https://github.com/jonathanselby/codebase-to-edd) to establish a defensible system baseline: purpose, components, runtime behaviour, state, interfaces, persistence, dependencies, failure modes and unresolved questions. Bring that baseline into this toolkit as evidence.

The two methods answer different questions:

```text
codebase-to-edd                  technology-sourcing-toolkit
-----------------                ----------------------------
What is this system?             Should we depend on this option?
How does it behave?              Under what assumptions?
Where is state/control?          At what cost and operating burden?
What can fail?                   How reversible is the decision?
```

## Design choices

### Architecture and commercial terms are evaluated together

The contract follows the architecture. Data volumes, resilience requirements, deployment topology, environments, interfaces, support model and change frequency all affect cost and dependency.

### Evidence beats scoring theatre

Weighted scorecards can create false precision. A score is useful only when the underlying evidence and assumptions remain visible. This toolkit therefore records evidence first and permits scoring only as a summary.

### Exit is part of entry

If an option is difficult to leave, that is a property of the decision being made now. Exit should be considered before commitment, not discovered at renewal.

### The operating model counts

People, support, skills, on-call load, release ownership, incident recovery, controls and supplier coordination are part of the system.

### Build is not automatically strategic

Owning code creates control and responsibility at the same time. Build only earns its place when ownership creates enough advantage or flexibility to justify the continuing engineering burden.

### SaaS is not automatically low effort

A hosted product may remove infrastructure while leaving substantial integration, identity, data, configuration, operating-control and supplier-management work behind.

## Limitations

This is a decision aid, not a procurement policy, legal review, financial model or substitute for specialist security and architecture assurance.

The examples are fictional. Real decisions should use verified technical evidence, actual commercial terms, appropriate legal review and organisation-specific risk tolerances.

The toolkit intentionally avoids prescriptive scoring weights. Importance depends on the decision.

## Version

Current version: **0.1.0**

See [`CHANGELOG.md`](CHANGELOG.md).

## Licence

MIT. See [`LICENSE`](LICENSE).
