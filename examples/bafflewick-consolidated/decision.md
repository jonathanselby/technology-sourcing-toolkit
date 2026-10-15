# Bafflewick Consolidated — Warehouse Routing Decision

## Context

Bafflewick Consolidated operates three warehouses and still relies on a routing application assembled from spreadsheets, scripts and manually maintained dispatch rules.

The system works, but recovery depends on a small number of people who understand its accumulated exceptions. Bafflewick wants to reduce manual dispatch effort and improve recoverability without turning a modest capability into a major platform programme.

## Decision

> Decide how Bafflewick should provide warehouse routing for the next five years while reducing manual work, preserving operational resilience and keeping exit cost proportionate to the capability.

## Technical baseline

The current system:

- receives orders from the ERP;
- applies warehouse eligibility and routing rules;
- returns a selected warehouse and dispatch priority;
- holds limited operational state;
- has modest transaction volume but is business-critical during warehouse hours;
- has several manual exception paths;
- has weak automated recovery and limited documentation.

The current baseline would be suitable for a deeper `codebase-to-edd` review before implementation planning.

## Plausible options

### A — Build a small internal routing service

A bounded service owns rules, API and state. Existing corporate identity, monitoring and database capabilities are reused.

### B — Buy a specialist routing package

Bafflewick licenses a specialist product and operates it on its standard infrastructure.

### C — Rent a SaaS routing platform

Bafflewick configures routing rules in a hosted service and integrates ERP and warehouse systems through vendor APIs.

## Discriminating needs

All credible options can route orders. The useful distinctions are:

1. speed of implementation;
2. recoverability and operational transparency;
3. ability to express Bafflewick's unusual routing exceptions;
4. integration burden;
5. skills required to maintain the capability;
6. cost behaviour as transaction volume grows;
7. effort to change supplier or model later.

## Claim-vs-evidence exercise

The SaaS supplier says:

> "Customers can export all configuration at any time, so there is no lock-in."

Evidence collected:

- routing tables can be exported as JSON;
- customer master data can be exported;
- workflow scripts use supplier-specific functions;
- audit history is exportable only as reports;
- there is no automated importer for another product;
- the API is documented and versioned.

Judgement:

**Partly proven.** Data portability is reasonable. Workflow portability is not. The supplier has demonstrated export, not replacement.

## Build / buy / rent judgement

### Build

Strengths:

- routing logic is small and directly controlled;
- unusual exceptions can be represented without product customisation;
- integration can fit existing systems;
- exit from the application itself is simple because Bafflewick owns code and data.

Weaknesses:

- Bafflewick must own testing, releases, support and recovery;
- the application needs durable internal engineering ownership;
- poorly bounded scope could expand into a custom logistics platform.

### Buy

Strengths:

- mature routing capability;
- greater product depth if requirements expand;
- lower initial product-engineering effort.

Weaknesses:

- Bafflewick still owns infrastructure and upgrades;
- several existing exceptions require product-specific configuration;
- the package introduces a specialist skill requirement for a relatively small capability.

### Rent

Strengths:

- fastest implementation path;
- supplier operates infrastructure;
- standard routing needs are already covered.

Weaknesses:

- supplier-specific workflow functions create growing dependency;
- API usage is a variable cost;
- Bafflewick still owns integration, identity, data quality and operational coordination;
- supplier release timing is outside Bafflewick's control.

## Commercial shape

Rather than invent exact prices, the comparison records cost drivers.

| Driver | Build | Buy | Rent |
|---|---|---|---|
| Initial engineering/implementation | High | Medium | Medium |
| Infrastructure | Low/medium | Medium | Included |
| Internal support | Medium/high | Medium | Low/medium |
| Specialist product skill | Low | High | Medium |
| Variable transaction cost | Low | Low | High |
| Upgrade effort | Internal change | Product upgrade | Supplier managed, integration impact remains |
| Exit effort | Low/medium | Medium/high | Medium/high and rises with workflow accumulation |

At current modest volume, all three remain commercially plausible. A growth scenario materially worsens the SaaS variable-cost profile. A requirement for sophisticated routing optimisation would materially improve the case for the specialist package.

## Exit assessment

### Build

Exit means replacing an internally owned service. Data structures and interfaces are known. The largest dependency is internal knowledge, so documentation and tests are part of the exit control.

### Buy

Exit requires configuration extraction, data migration, interface replacement and removal of specialist operating skills.

### Rent

Data exit is plausible. Workflow logic requires translation or rebuild. Audit history must be retained separately if long-term evidence is required.

## Focused due diligence

Questions capable of changing the decision:

1. Can Bafflewick implement its three hardest routing exceptions in each option without architectural workarounds?
2. What is the measured recovery path when routing is unavailable?
3. For SaaS, how does transaction pricing behave at 3x current volume?
4. For the package, what upgrade work is required for configured routing extensions?
5. For build, can Bafflewick name the team that will own the service for five years?
6. Can each option export sufficient data, configuration and evidence to support replacement?

## Decision

**Preferred option for this fictional case: build a deliberately small internal routing service, subject to confirming durable ownership.**

Why:

- the capability is narrow;
- the unusual rules are material but technically simple;
- transaction volume is modest;
- existing corporate infrastructure can be reused;
- SaaS removes less operating responsibility than the first diagram suggests;
- the specialist package adds product depth Bafflewick does not currently need;
- owning a small bounded service keeps the exit path straightforward.

## Condition that could reverse the decision

If Bafflewick cannot name and fund durable internal ownership, build stops being the preferred option. In that case SaaS becomes attractive despite the greater dependency because unowned internal software is a larger operational risk than managed supplier dependency.

That condition is why the method records assumptions explicitly rather than presenting the chosen option as universally superior.
