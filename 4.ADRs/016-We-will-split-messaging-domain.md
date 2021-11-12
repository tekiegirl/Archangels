[> Home](../README.md)    [> ADRs](README.md)

---

# Messaging will be split into Subscription, Message, Notification and Email functionality

Date: 2021-11-11

## Status

Confirmed

## Context

The Messaging domain consists of four main sections: Notification, Message, Email and Subscription. There is also the possibility that one or more of these may be solved using COTS. A split is required between subscriptions and other messaging, so that a fault in messaging does not affect customers being able to subscribe/unsubscribe/view subscriptions to Forums, Events, etc. Separating Notifications from other sections is a functionality split as Notifications are not related to Email, but are related to Message AND Subscription, so cannot be combined with only one of these. An interface to the implementation of each of these 4 sub-domains would also be optimal. See [Architecture Analysis](../1.ProblemBackground/ArchitectureAnalysis.md) for more information.

## Decision

The Messaging domain will be split into Subscription, Message, Notification and Email functionality and provide an interface to each.

## Consequences

**Positive:**

- Functionality split with no overlap
- Faults do not bring unrelated functionality down
- Interfaces mean it is easy to swap out functionality, e.g. change between home-grown and COTS options for e.g. Messages.

**Risks:**

- Some code may need to be shared, but this could be split into its own sub-domain.

---

[> Home](../README.md)    [> ADRs](README.md)