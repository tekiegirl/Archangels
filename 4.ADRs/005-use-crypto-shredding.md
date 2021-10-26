# Record architecture decisions

Date: 2021-10-21

## Status

Accepted

## Context

The FarmacyFamily will have to hold personal and even medical data about its users. Therfore its reasonable to
assume that users may want all of their data removed from the system, which can prove difficult in distributed systems, especially where
data backups are involved. We need a way of easily removing user data

## Decision

Hold a separate crypto key store that holds a key per user that is used to encrypt that particular users data. This will live
in a separate data store and will never be kept alongside the encrypted data. Therefore to delete all records we can simply remove the key.
Once all backups of the keystore or data have been removed the data will become unrecoverable.

## Consequences

**Positive:**

- A good secure approach
- Easy to effectively delete a users' data - 


**Negative:**

- Need to introduce a short-lived cache of unecrypted data for querying so that the system can remain performant

**Risks:**

- If a key is leaked it becomes effectively impossible to delete a users data via crypto shredding

**Bonus Features:**

- Adds another layer of security