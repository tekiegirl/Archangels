[> Home](../README.md)    [> Solution Background](README.md)

---

# Datastore Solution Overview

When considering the Farmacy Foods system there are two needs for storing data

- data storage and retrieval
- analytics data storage and analytics of stored data

The need for analytics of some data stored in Farmacy Family means that more than one type of data store could be optimal for the system.

## Considered Data Store Approaches

### Relational

This type of data store is optimal for data that is not highly connected. The need to create relationships via extra tables and joins slows down the storage and retrieval of data and makes the design and maintenance more complex. **Simplicity is an inherent architecture characteristic.**

Relational is an option for data that is not highly connected and not involved in analytics.

### Document

This type of data store is also not optimal for data that is highly connected. It is good for data that is unstructured (not all the same), e.g. would not fit well into the tables in a relational database due to null entries in various columns in different rows.

Analysis of the data required for Farmacy Family may show that a document store would be optimal for all or some of the non-analytical or highly connected data, e.g. profiles (where some users fill in all fields and others only a selection).

### Graph

A graph database is optimal for highly connected data and can be very fast for performing analytics. It is also optimal for unstructured data, in the same way as a document store.

Without further analysis it would seem that a graph database would be optimal for the data that requires analytics and for also storing analytics of that data.

[ADR: 008 We-will-use-a-graph-store-for-analytics](../4.ADRs/008-We-will-use-a-graph-store-for-analytics.md)

## Next Steps

- [ ] Analyse data needs to decide upon storage of non-analytical data: document, relational, or graph.
- [ ] Create initial model for analytical data in a graph database.

---

[> Home](../README.md)    [> Solution Background](README.md)

