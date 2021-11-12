[> Home](../README.md)    [> ADRs](README.md)

---

# Analytics will be split into Administration, Run and Store/Access functionality

Date: 2021-11-11

## Status

Confirmed

## Context

The Analytics domain consists of three main sections: Administer Analytics, Run Analytics, and Store/Access Analytics Results. There is also the possibility that the running or administration would be solved using COTS. A split is required between admin and run/access use, so that a fault in administration does not affect previous result access or running current analytics. The running and storage/access of analytics results will also be split, not because of fault tolerance as storage of results is required by the running of analytics, but because of code volatility causing headaches in deploying run and store/access functionality together. An interface to the implementation of each of these 3 sub-domains would also be optimal. See [Architecture Analysis](../1.ProblemBackground/ArchitectureAnalysis.md) for more information.

## Decision

The Analytics domain will be split into Administration, Run and Store/Access functionality and provide an interface to each.

## Consequences

**Positive:**

- Functionality split with no overlap
- Faults do not bring unrelated functionality down
- Authorisation split between admin and non-admin areas
- Interfaces mean it is easy to swap out functionality, e.g. change between home-grown and COTS options for e.g. running analytics.

**Risks:**

- Some code may need to be shared, but this should only be code that is NOT high-security (i.e. only required by the Admin sub-domain). This could be split into its own sub-domain.

---

[> Home](../README.md)    [> ADRs](README.md)