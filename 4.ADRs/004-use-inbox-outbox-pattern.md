# Use Inbox and Outbox Pattern When Publishing/Subscribing to Events

Date: 2021-10-21

## Status

Accepted

## Context

In a system that uses an event based approach, generally when triggering a system event we would want to save the event and
publish it to some form of message broker. This introduces a common cause of data inconsistencies, often referred to the duel write problem.

On the subscription side we would often be dealing with at least once delivery, therefore we need to be able to handle the same event being received more than once

## Decision

* Use the outbox pattern when publishing events - save the event to a data store, ack, and have a separate process send the event and mark as sent
* Use the inbox pattern when subscribing to events - save the event to a data store,ack, and have a separate process handle the event and mark as handled

## Consequences

**Positive:**

- Outbox
  - Guarantees that the message was sent at least once as we are making sure the event data is not lost
  - Easy to add re sending logic if needed
- Inbox
  - Messages can be handled at a convenient pace
  - Easy to implement idempotency, can ignore events we have already logged in the data soter 

**Negative:**

- inbox requires polling or change detection process
- adds complexity as we need processes to handle the inboxes/outboxes separatly form the publisher or subscriber

**Risks:**

- TODO

**Bonus Features:**

