# Architecture Analysis

## Key Architecture Characteristics

By identifying the key architecture characteristics for this solution we can then identify the least-worst solution. Best practice is to identify no more than seven.

| Characteristic | Source |
| -------------- | ------ |
|                |        |
|                |        |
|                |        |
|                |        |
|                |        |
|                |        |
|                |        |

## Architectural Quanta

Of the characteristics identified above, do they apply to the whole system or are there clear sets applying to different parts of the system?

- [ ] divide into supportive, core and generic?

| Identified Domains                                           | Applicable Architectural Characteristics |
| ------------------------------------------------------------ | ---------------------------------------- |
| Users (profile - fine grained control, dietary needs, prefs) |                                          |
| Authentication                                               |                                          |
| Data Store                                                   |                                          |
| Community (connections, subscriptions to forums, etc)        |                                          |
| Class (localised, temporal)                                  |                                          |
| Event (in-person, localised, temporal)                       |                                          |
| Forum (localised, temporal)                                  |                                          |

Reference material (static), general wellness education, other material? - global, reference

Analytics (geographical trend analysis)

Messages/emails

onboarding - separate from users?

UI - add to reactive monolith - can be modified



Integration points

- Foods: user (2-way)
- Foods: fridges (analytics feedback to optimise)
- Dietician (eDietician) - profile and messaging
- Clinics - permissions to share medical info in profile with clinics 
  - analytical data from these clinics into Family?
  - clinics access analytical data in Family?