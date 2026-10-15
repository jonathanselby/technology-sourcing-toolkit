# Build / Buy / Rent

## Purpose

Build, buy and rent are different allocations of control, responsibility and dependency.

The question is not which model is best in general. The question is which model best fits the capability being sourced.

## Compare the models

| Dimension | Build | Buy | Rent |
|---|---|---|---|
| Initial speed | Usually slower | Medium | Often fastest |
| Product control | High | Medium | Lower |
| Engineering burden | High | Medium | Lower infrastructure burden, not zero operating burden |
| Differentiation | Highest potential | Moderate | Usually lowest |
| Upgrade control | High | Medium | Low |
| Integration freedom | High | Depends on product | Depends on exposed interfaces |
| Supplier dependency | Lower product dependency, higher internal capability dependency | Medium/high | Usually high |
| Exit path | Code and knowledge retained if well managed | Data/config migration | Data/config/workflow migration plus service replacement |
| Cost shape | Labour + infrastructure + opportunity cost | Licence + implementation + operation | Subscription/usage + integration + administration |

## Questions that matter

### Build

- Does owning the behaviour create material advantage?
- Can the organisation maintain the engineering capability for the useful life of the system?
- Is the problem sufficiently bounded to avoid building a platform by accident?
- How often will requirements change?
- What operational burden follows ownership?

### Buy

- How much customisation is required before the package fits?
- Who owns upgrades and compatibility?
- Does the product constrain architecture or data ownership?
- Can the organisation operate it reliably?
- What is the realistic lifecycle of the product and supplier?

### Rent

- Which responsibilities genuinely disappear?
- Which responsibilities merely move to integration, administration and supplier management?
- How does cost behave with volume and growth?
- What changes without customer control?
- What must be extracted or rebuilt to leave?

## Decision rule

Do not choose build because the team can code it.

Do not choose buy because procurement can negotiate it.

Do not choose rent because infrastructure disappears from the diagram.

Choose the ownership model whose continuing responsibilities best fit the organisation and the capability.
