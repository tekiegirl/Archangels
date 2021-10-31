[> Home](../README.md)    [> ADRs](README.md)

# Use a graph data store for analytics

Date: 2021-10-28

## Status

Confirmed

## Context

Analysis of the options for storing data for analytics and analytics data show a graph database to be optimal for fast analysis, access and storage of unstructured and highly connected data.

## Decision

Use a graph data store for analytics data.

## Consequences

**Positive:**

- Meets the requirements of analytics.

**Risks:**

- Likely requires training of current staff on this technology, or employment of staff already skilled

**Bonus Features:**

- Can model the database exactly how things are in the real world, with no joins or trying to fit data into a relational format

[> Home](../README.md)    [> ADRs](README.md)