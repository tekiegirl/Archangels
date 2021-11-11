[> Home](../README.md)    [> ADRs](README.md)

# Separate Users into Customer, Administrator & Medical

Date: 2021-11-11

## Status

Confirmed

## Context

The User domain is responsible for various processes. Granularity analysis is required to decide if this domain needs to be broken down further. See [Architecture Analysis](../1.ProblemBackground/ArchitectureAnalysis.md) for more information.

## Decision

The User domain will be split into Customer, Administrator & Medical, with Clinic being a Medical Admin role.

## Consequences

- **Positive:**

  - Functionality split with no overlap
  - Faults do not bring unrelated functionality down

  **Risks:**

  - Clinic and Dietician users will have some differences, which will need to be taken into account in code structure, with a Clinic being a Medical Admin role.

[> Home](../README.md)    [> ADRs](README.md)