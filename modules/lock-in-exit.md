# Lock-in and Exit

## Purpose

Lock-in is not a binary property of a supplier. It is the accumulated cost of removing a dependency.

A proprietary API may be easy to replace. A nominally open platform may be difficult to leave if years of workflow, data, controls and operating knowledge have accumulated around it.

## Dependency map

Assess dependency across:

| Area | Questions |
|---|---|
| Data | Can it be exported completely, intelligibly and within useful time? |
| Interfaces | How many consumers depend on supplier-specific APIs or events? |
| Workflow/configuration | Can logic be exported or must it be rebuilt? |
| Identity/security | Which policies, roles, keys and control evidence are platform-specific? |
| Operations | Which runbooks, dashboards and recovery procedures depend on the platform? |
| Skills | Is knowledge portable or supplier-specific? |
| Commercial | Are minimum commitments, notice periods or transition charges material? |
| Control evidence | Can audit history and decision records be retained after exit? |

## Exit test

For each dependency record:

1. what must move or be replaced;
2. available export/transition mechanism;
3. destination or replacement assumption;
4. effort and elapsed time;
5. business interruption risk;
6. evidence that the path works;
7. contractual rights required.

## Lock-in is sometimes rational

Avoiding all lock-in can create worse systems.

A managed database, specialist SaaS platform or proprietary service may create enough value to justify dependency. The decision is sound when:

- the dependency is understood;
- the benefit is material;
- the concentration risk is acceptable;
- an exit path exists at a cost proportionate to the capability.

## Core rule

> **Choose dependency deliberately. Do not discover it later.**

See [`../templates/exit-plan.md`](../templates/exit-plan.md).
