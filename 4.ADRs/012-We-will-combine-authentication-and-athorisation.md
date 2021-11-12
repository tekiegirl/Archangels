[> Home](../README.md)    [> ADRs](README.md)

---

# Combine Authentication and Authorisation into one Security Domain

Date: 2021-11-11

## Status

Confirmed

## Context

The Security domain is responsible for both making sure the user is who they say they are and can only access what they are allowed to access. It is considered to be too large a trade-off to separate these concerns. See [Architecture Analysis](../1.ProblemBackground/ArchitectureAnalysis.md) for more information.

## Decision

The Security domain will not be split.

## Consequences

- **Positive:**

  - The system needs both authorisation and authentication, and cannot operate if one goes down, so the overhead of splitting is avoided.
  - Security code is easily shared.

  **Risks:**

  - There are different workflows, but these can be handled by orchestrators.
  - If the domain gets large it will be a bottleneck for deployment.

---

[> Home](../README.md)    [> ADRs](README.md)