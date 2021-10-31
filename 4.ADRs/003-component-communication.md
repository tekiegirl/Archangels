[> Home](../README.md)    [> ADRs](README.md)

# Use Domain Events as the primary mechanism of communication

Date: 2021-10-21

## Status

Accepted

## Context

We need a way in which we can pass data and allow different components of the system to communicate
in a way that can maximise decoupling

## Decision

Use Domain Events as the primary mechanism of communication. These events should use ubiquitous language and should represent state of fact so to be easy to understand 
by all areas of the business.

Events should be constructed using the [[Cloud Events](https://cloudevents.io)] specification. 

## Consequences

**Positive:**

* Events using business language can be understood by all areas of the business
* Pub Sub like model allows arbitrary number of subscriptions, can add to the system in a plug and play manner. Promotes Open/closed principle, aids evolution
* Fault tolerance and recover
* Able to provide a real time (ish) view of whats going on in the system

**Negative:**

* Eventual consistency may be a new approach for some developers used to a more synchronous or transactional system
* At least once delivery generally adds complexity as we need to ensure subscribers are idempotent
* Duel write Problem - See next ADR TODO add link

**Risks:**

* could be a new pattern for some developers

[> Home](../README.md)    [> ADRs](README.md)