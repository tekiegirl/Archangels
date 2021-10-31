[> Home](../README.md)    [> ADRs](README.md)

# Use and event-driven architecture

Date: 2021-10-27

## Status

Confirmed

## Context

Analysis of the architecture characteristics required of the system and the possible architecture styles concluded that an event-driven architecture would suit the system, with less trade-offs than other options.

## Decision

Use an event-driven architecture for the backend of the system.

## Consequences

**Positive:**

- Four of seven characteristics score highly.

**Negative:**

- Interoperability needs to be mitigated.

**Risks:**

- Interoperability and configurability may still be high trade-offs after mitigation.

**Bonus Features:**

- 

[> Home](../README.md)    [> ADRs](README.md)