[> Home](../README.md)    [> ADRs](README.md)

---

# Use Secure data solution to secure medical records

Date: 2021-10-29

## Status

Confirmed

## Context

The systems needs to collect and store sensitive customer medical records. So a high security COTS product will be considered for giving 3rd parties access to shared medical data, to avoid reinventing the wheel and the possibility of making mistakes.

## Decision

Use a standard solution to store medical data. We suggest considering [Skyflow](https://www.skyflow.com/).

## Consequences

**Positive:**

- Increase customer confidence in sharing medical records.

**Risks:**

- Evaluating the right security solution  considering multiple vendors may be time consuming.

---

[> Home](../README.md)    [> ADRs](README.md)