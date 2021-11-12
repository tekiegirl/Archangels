[> Home](../README.md)    [> ADRs](README.md)

---

# Media will be split into admin and customer functionality

Date: 2021-11-11

## Status

Confirmed

## Context

The Media domain consists of three main sections: Administer Media, Access Media, and View Media. There is also the possibility that the storage and access of media would be solved using COTS. A split is required between admin and customer use, but also an interface between the admin/customer user and the Media storage/access, which could be COTS or home-grown. See [Architecture Analysis](../1.ProblemBackground/ArchitectureAnalysis.md) for more information.

## Decision

The Media domain will be split into Admin and Customer (access/view) functionality and provide an interface to Media Storage.

## Consequences

**Positive:**

- Functionality split with no overlap
- Faults do not bring unrelated functionality down
- Authorisation split between admin and customer areas
- Interfaces mean it is easy to swap out functionality, e.g. change between home-grown and COTS options for e.g. Media storage and access.

**Risks:**

- Some code may need to be shared, but this should only be code that is NOT high-security (i.e. only required by the Admin sub-domain).

---

[> Home](../README.md)    [> ADRs](README.md)