[> Home](../README.md)    [> ADRs](README.md)

# Use blob storage for static content

Date: 2021-10-29

## Status

Confirmed

## Context

Analysis of the options for storing data for static and potentially large data show blob storage to be optimal for fast analysis, access and storage of unstructured and highly connected data.

## Decision

Use a blob storage for larger and static data, e.g. videos and images. For Amazon this would suggest using an S3 Bucket.

## Consequences

**Positive:**

- Meets the requirements of large and static content.
- Matches the architecture of Farmacy Foods.

**Risks:**

- Storing data in different ways in the system means the technical team need to have wider knowledge, but the knowledge should already be there from Farmacy Foods being implemented first.

[> Home](../README.md)    [> ADRs](README.md)