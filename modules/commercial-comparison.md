# Commercial Comparison

## Purpose

Headline licence price is not a technology cost model.

Commercial comparison should use the architecture and operating model each option actually requires.

## Cost structure

Separate cost into:

### One-off

- implementation;
- migration;
- integration;
- data conversion;
- testing;
- training;
- initial controls and assurance;
- transition or parallel-run effort.

### Recurring fixed

- subscriptions or licences;
- support tiers;
- reserved infrastructure;
- minimum commitments;
- internal support capacity.

### Variable

- users;
- transactions;
- API calls;
- storage;
- compute;
- environments;
- network/egress;
- premium support events.

### Contingent

- growth beyond committed bands;
- acquisitions or divestments;
- regulatory change;
- major version change;
- termination;
- data extraction;
- exit/transition assistance.

## Compare scenarios, not one forecast

At minimum test:

```text
LOW / DOWNSIDE USAGE
EXPECTED USAGE
HIGH / GROWTH USAGE
EXIT OR REPLACEMENT
```

Make assumptions visible so reviewers can change them without rebuilding the argument.

## Avoid false precision

A five-year total cost estimate containing uncertain future usage is not a fact merely because it contains dollars and cents.

Record ranges or sensitivities where appropriate. Identify which assumptions materially change the ranking.

## Architecture drives commercial shape

Examples:

- active-active resilience may double some capacity commitments;
- multiple non-production environments may create additional licence consumption;
- high-volume event integration may alter API economics;
- data export or egress may make exit materially more expensive;
- a managed service may reduce infrastructure labour but require higher supplier-management and integration effort.

## Core rule

> **Price the system you will operate, not the product on the quote.**
