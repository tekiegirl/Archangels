[> Home](../README.md)    [> ADRs](README.md)

# Community will be split into admin and customer functionality and provide an interface to classes, forums and events

Date: 2021-11-11

## Status

Confirmed

## Context

The Community domain consists of three main sections: Events, Forums & Classes, but also the administration of these. There is also the possibility that one or more of these sections would be solved using COTS. A split is required between admin and customer use, but also an interface between the admin/customer user and the Event/Forum/Class management, which could be COTS or home-grown. See [Architecture Analysis](../1.ProblemBackground/ArchitectureAnalysis.md) for more information.

## Decision

The Community domain will be split into admin and customer functionality and provide an interface to classes, forums and events. This will produce 8 separate elements within the domain, with admin and customer elements using the class, forum and event interfaces. The Event, Class and Forum elements will then be implemented as appropriate, and possibly changed in the future.

## Consequences

- **Positive:**

  - The system needs both authorisation and authentication, and cannot operate if one goes down, so the overhead of splitting is avoided.
  - Security code is easily shared.

  **Risks:**

  - There are different workflows, but these can be handled by orchestrators.
  - If the domain gets large it will be a bottleneck for deployment.

[> Home](../README.md)    [> ADRs](README.md)