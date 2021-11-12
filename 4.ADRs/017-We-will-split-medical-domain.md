[> Home](../README.md)    [> ADRs](README.md)

---

# Medical will be split into Admin and Customer functionality

Date: 2021-11-11

## Status

Confirmed

## Context

The Medical domain consists of two main sections: Admin and Customer. A split is required between Admin and Customer, so that a fault in one does not affect the other, and from an authorisation perspective. An interface to the implementation of each of these 2 sub-domains would also be optimal. See [Architecture Analysis](../1.ProblemBackground/ArchitectureAnalysis.md) for more information.

## Decision

The Medical domain will be split into Admin and Customer functionality and provide an interface to each.

## Consequences

**Positive:**

- Functionality split with no overlap
- Faults do not bring unrelated functionality down
- Authorisation split between admin and customer areas
- Interfaces mean it is easy to swap out functionality, e.g. change between home-grown and COTS options for e.g. Messages.

**Risks:**

- Some code may need to be shared, but this could be split into its own sub-domain.

---

[> Home](../README.md)    [> ADRs](README.md)