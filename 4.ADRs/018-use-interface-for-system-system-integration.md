[> Home](../README.md)    [> ADRs](README.md)

---

# An Interface will be used for system-system interfacing

Date: 2021-11-11

## Status

Confirmed

## Context

There are three types of system to system integration required for Farmacy Family: two with Farmacy Foods (Customer and Analytics), and one with Clinics (Data for analytics). Where integration with another system is required we will require authentication and authorisation of that external system, via an Interface. See [Architecture Analysis](../1.ProblemBackground/ArchitectureAnalysis.md) for more information.

## Decision

An Interface will be used for system to system interfacing, with authentication and authorisation of that external system required.

## Consequences

**Positive:**

- Makes adding interfaces to new systems in the future much easier.
- One point in the system to defend (see risk below).
- Authorisation and authentication protect the system.

**Risks:**

- If access to the system was gained by another method the attacker would skip the Interface authentication and authorisation. Zero-trust and further authorisation checks should be implemented also.

---

[> Home](../README.md)    [> ADRs](README.md)