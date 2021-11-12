[> Home](../README.md)    [> ADRs](README.md)

---

# Community will be split into admin and customer functionality and provide an interface to classes, forums and events

Date: 2021-11-11

## Status

Confirmed

## Context

The Community domain consists of three main sections: Events, Forums & Classes, but also the administration of these. There is also the possibility that one or more of these sections would be solved using COTS. A split is required between admin and customer use, but also an interface between the admin/customer user and the Event/Forum/Class management, which could be COTS or home-grown. See [Architecture Analysis](../1.ProblemBackground/ArchitectureAnalysis.md) for more information.

## Decision

The Community domain will be split into admin and customer functionality and provide an interface to classes, forums and events. This will produce 8 separate sub-domains within the domain, with Admin and Customer sub-domains (2) using the Class, Forum and Event interfaces (3). The Event, Class and Forum sub-domains (3) will then be implemented as appropriate, and possibly changed in the future with minimal changes to code.

## Consequences

**Positive:**

- Functionality split with no overlap
- Faults do not bring unrelated functionality down
- Authorisation split between admin and customer areas
- Interfaces mean it is easy to swap out functionality, e.g. change between home-grown and COTS options for e.g. Events.

**Risks:**

- Some code may need to be shared, but this should only be code that is NOT high-security (i.e. only required by the Admin sub-domain).

---

[> Home](../README.md)    [> ADRs](README.md)