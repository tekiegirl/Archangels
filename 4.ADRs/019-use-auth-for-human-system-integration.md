[> Home](../README.md)    [> ADRs](README.md)

---

# Authentication and Authorisation of users will be used for human-system integration

Date: 2021-11-11

## Status

Confirmed

## Context

Excepting Customers, there are six types of human to system integration required for Farmacy Family: two with a Dietician (Customer Profile and Message), and four with Clinics (Customer Profile, Message, Analytics and Data). Where integration with a human is required we will require authentication and authorisation of that user via a User Account and related Permissions. See [Architecture Analysis](../1.ProblemBackground/ArchitectureAnalysis.md) for more information.

## Decision

A User Account will be used for human to system interfacing, with authentication and authorisation of that User Account required. Extra Authentication and/or 'prove you are a human' prompts will be used when data is considered high-security.

## Consequences

**Positive:**

- Makes adding new authorisations/integrations in the future much easier.
- Authorisation and authentication protect the system (see risk below).

**Risks:**

- If access to the system was gained by another method the attacker would skip the User authentication and authorisation. Zero-trust and further authorisation checks should be implemented also.

---

[> Home](../README.md)    [> ADRs](README.md)