# Technology Sourcing Skill

## Purpose

Use this skill to analyse a technology sourcing decision where architecture, operations, supplier dependency and commercial structure interact.

The output should support judgement. It should not imitate a procurement policy or manufacture precision from weak evidence.

## Inputs

Use whatever is available, including:

- business problem and constraints;
- current-state architecture or EDD;
- requirements;
- supplier responses;
- product documentation;
- commercial assumptions;
- usage/volume data;
- operating evidence;
- contract excerpts where the user is entitled to analyse them.

If important information is missing, distinguish known, inferred and unknown facts.

## Method

1. Frame the decision as an outcome and choice.
2. Establish the technical baseline.
3. Identify plausible build / buy / rent / retain options.
4. Separate mandatory requirements from discriminators.
5. Convert material supplier statements into testable claims.
6. Map the continuing operating model for each option.
7. Model commercial shape from the architecture and realistic usage.
8. Identify dependency and credible exit paths.
9. Ask only due-diligence questions capable of changing the decision.
10. Produce a compact decision record with assumptions, accepted risks and review triggers.

## Evidence discipline

For material points classify evidence as:

- **proven**;
- **partly proven**;
- **inferred**;
- **unknown**;
- **contradicted**.

Do not convert an unknown into a high-confidence recommendation merely because the surrounding material is detailed.

## Architecture discipline

When an existing system or codebase is material to the decision, request or create a technical baseline before judging replacement options.

A suitable baseline covers:

- purpose;
- components;
- runtime behaviour;
- interfaces;
- state and persistence;
- dependencies;
- failure modes;
- security boundaries;
- unresolved questions.

The `codebase-to-edd` method is one way to create this baseline.

## Commercial discipline

Do not compare headline prices only.

Separate:

- one-off;
- recurring fixed;
- variable;
- contingent;
- exit/transition costs.

Make architecture and usage assumptions visible.

## Dependency discipline

Assess dependency across data, interfaces, workflow/configuration, identity/security, operations, skills, commercial terms and control evidence.

Do not treat all lock-in as bad. State the benefit received in exchange for the dependency.

## Output structure

```markdown
# Decision

## Required outcome
## Constraints and unknowns
## Technical baseline
## Options considered
## Discriminating requirements
## Claim vs evidence findings
## Operating consequences
## Commercial shape
## Dependency and exit
## Focused due diligence
## Recommendation
## Assumptions that could reverse the recommendation
## Accepted risks
## Review trigger
```

## Guardrails

- Do not expose confidential employer, client or board information.
- Do not invent supplier pricing, contract rights or technical capabilities.
- Do not reproduce confidential contracts or negotiations in public examples.
- Prefer public or fictional examples for reusable output.
- Do not let scoring hide the underlying evidence.
- State uncertainty directly.
