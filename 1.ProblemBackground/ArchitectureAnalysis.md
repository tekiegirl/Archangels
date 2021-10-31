[> Home](../README.md)   [> Problem Background](README.md)

---

# Architecture Analysis

## Key Architecture Characteristics

By identifying the key architecture characteristics for this solution we can then identify the *least-worst* solution. Best practice is to identify no more than seven. These, along with the implicit architecture characteristics, will then feed into the overall architecture of the Farmacy Family system.

### Candidate Architecture Characteristics

performance    responsiveness    availability    fault-tolerance    scalability/elasticity    data integrity    data consistency    adaptability    extensibility    interoperability    concurrency    deployability    testability    abstraction    workflow    configurability    recoverability    reliability    authorisation    agility    cost    domain-partitioning    evolvability    integration

### Selected Architecture Characteristics

| Top 3 | Characteristic               | Source                                                       |
| ----- | ---------------------------- | ------------------------------------------------------------ |
| Y     | Interoperability/Integration | Integration with Farmacy Foods (converting Foods transactional customers to Family engaged customers, and analytics feedback), and with dieticians and clinics. |
|       | Data Integrity               | Generate analytical data from medical information, geographical data, etc, to demonstrate the benefits of FF, improve fridge supplies for Foods, and exchange analytical data with clinics. Must be correct as is medical data. |
|       | Scalability/Elasticity       | Analysis domain, and some other domains like reference material / media, likely to require more resources (especially computational) at different times. |
| Y     | Configurability              | Customers have fine-grained control what other customers can see on their profile, and give permissions for e.g. clinics to access their medical data. |
| Y     | Authorisation                | Although normally an implicit architecture characteristic (see below) this is promoted here due to clinician and dietician needing authorisation from a customer user to access medical information. |
|       | Workflow                     | Transactional Foods customers must be onboarded as engaged Family customers, with a completed profile. |
|       | Fault-Tolerance              | Community is the most important part of Family. It consists of many aspects, e.g. forums, events, classes, and so each community subdomain must be fault-tolerant of the others else one small problem could take the whole community domain down. |

### Implicit Architecture Characteristics

The following are a bedrock of architecture characteristics. They may not affect the *structure* but will feed into the overall architecture.

- Feasibility (cost/time)
- Security, authentication and authorisation
- Maintainability
- Simplicity

---

## Architectural Quanta

Of the characteristics identified above, do they apply to the whole system or are there clear sets applying to different parts of the system?

| Identified Domains                                    | Sub-domains and Considerations                               | Applicable Architectural Characteristics                     | Strategic Domain |
| ----------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ---------------- |
| Users                                                 | Customer, Preferences, Profile (Personal & Medical), Dietician, Clinic, Administrator?, Onboarding, Integration (Farmacy Foods) | - Interoperability<br />- Configurability<br />- Authorisation<br />- Workflow | Supportive       |
| Security                                              | Authentication, Authorisation                                | - Configurability<br />- Authorisation                       | Generic          |
| Data Store                                            | Database, Interface                                          | - Data Integrity<br />- Authorisation                        | Generic          |
| Class (localised, temporal)                           |                                                              | - Scalability/Elasticity<br />- Fault Tolerance              | Core             |
| Event (in-person, localised, temporal)                |                                                              | Fault Tolerance                                              | Core             |
| Forum (localised, temporal)                           |                                                              | - Configurability<br />- Authorisation<br />- Fault Tolerance | Core             |
| Reference Material / Media (global, reference/static) | Media Library, General Wellness                              | - Scalability/Elasticity                                     | Generic          |
| Analytics (geographical trend analysis)               | Geographical, Engagement?, Integration (Farmacy Foods), Reporting | - Interoperability,<br />- Data Integrity<br />- Scalability/Elasticity | Core             |
| Messaging                                             | Email, Message, Notification, Subscription?                  | - Interoperability<br />- Workflow                           | Supportive       |
| User Interface (Reactive Monolith)                    |                                                              | - Configurability<br />- Authorisation<br />- Fault Tolerance | Generic          |
| Medical                                               | Test, Result                                                 | - Authorisation                                              | Core             |

---

## System Granularity

A breakdown of the key granularity analysis and links to ADRs.

### Users

| Functionality | Volatility | Scalability             | Fault Tolerance                | Data Security | Data Transactions | Data Dependencies | Workflow |
| ------------- | ---------- | ----------------------- | ------------------------------ | ------------- | ----------------- | ----------------- | -------- |
| Customer      | Low        | Unlikely to be required | Split required                 | High          |                   |                   |          |
| Dietician     | Low        | Unlikely to be required | Could be merged with Clinic    | Med           |                   |                   |          |
| Clinic        | Low        | Unlikely to be required | Could be merged with Dietician | Med           |                   |                   |          |
| Administrator | Low        | Unlikely to be required | Split required                 | High          |                   |                   |          |

[ADR: ...]()

### Security

| Functionality  | Volatility | Scalability             | Fault Tolerance                                              | Data Security | Data Transactions                                    | Data Dependencies | Workflow |
| -------------- | ---------- | ----------------------- | ------------------------------------------------------------ | ------------- | ---------------------------------------------------- | ----------------- | -------- |
| Authentication | Low        | Unlikely to be required | Don't want one without the other, could be merged with Authorisation | High          | User email/username, User password (hashed/salted)   | User              | Separate |
| Authorisation  | Low        | Unlikely to be required | Don't want one without the other, could be merged with Authentication | High          | User Roles / Permissions, User authentication status | User              | Separate |

[ADR: ...]()

### Community

| Functionality    | Volatility | Scalability  | Fault Tolerance                                              | Data Security | Data Transactions | Data Dependencies | Workflow                              |
| ---------------- | ---------- | ------------ | ------------------------------------------------------------ | ------------- | ----------------- | ----------------- | ------------------------------------- |
| Administer Forum | Medium     | Low usage    | Split required from customer functionality                   | High          |                   | Forum             | Similar to Administer Event and Class |
| Access Forum     | Low        | Medium usage | Split required from admin functionality, could be merged with Write | Low           |                   | Forum             | Similar to Access Event and Class     |
| Write to Forum   | Low        | Medium usage | Split required from admin functionality, could be merged with Access | Low           |                   | Forum             | Similar to Write to Event and Class   |
| Administer Event | Medium     | Low usage    | Split required from customer functionality                   | High          |                   | Event             | Similar to Administer Forum and Class |
| Access Event     | Low        | Medium usage | Split required from admin functionality, could be merged with RSVP | Low           |                   | Event             | Similar to Access Forum and Class     |
| RSVP to Event    | Low        | Medium usage | Split required from admin functionality, could be merged with Access | Low           |                   | Event             | Similar to Write to Forum and Class   |
| Administer Class | Medium     | Low usage    | Split required from customer functionality                   | High          |                   | Class             | Similar to Administer Event and Forum |
| Access Class     | Low        | Medium usage | Split required from admin functionality, could be merged with Take | Low           |                   | Class             | Similar to Access Event and Forum     |
| Take Class       | Low        | Medium usage | Split required from admin functionality, could be merged with Access | Low           |                   | Class             | Similar to Write to Event and Forum   |

[ADR: ...]()

### Reference Material / Media 

| Functionality        | Volatility | Scalability  | Fault Tolerance                            | Data Security | Data Transactions | Data Dependencies | Workflow          |
| -------------------- | ---------- | ------------ | ------------------------------------------ | ------------- | ----------------- | ----------------- | ----------------- |
| Administer Media     | Medium     | Low usage    | Split required from customer functionality | Medium        | Media             | Media             | Separate          |
| View Available Media | Low        | Medium usage | Split required from admin functionality    | Low           | Media             | Media             | Similar to Access |
| Access Media         | Medium     | Medium usage | Split required from admin functionality    | Low           | Media             | Media             | Similar to View   |

[ADR: ...]()

### Analytics 

| Functionality                      | Volatility | Scalability | Fault Tolerance | Data Security | Data Transactions | Data Dependencies  | Workflow |
| ---------------------------------- | ---------- | ----------- | --------------- | ------------- | ----------------- | ------------------ | -------- |
| Run medical-geographical analysis  | High       | Required    | Not required    | High          |                   | User               | Separate |
| Run engagement-customer analysis   | High       | Required    | Not required    | Medium        |                   | User               | Separate |
| Run medical-user-wellness analysis | High       | Required    | Not required    | High          |                   | User, Test, Result | Separate |

[ADR: ...]()

### Messaging

| Functionality             | Volatility | Scalability  | Fault Tolerance                                   | Data Security | Data Transactions                                            | Data Dependencies                         | Workflow |
| ------------------------- | ---------- | ------------ | ------------------------------------------------- | ------------- | ------------------------------------------------------------ | ----------------------------------------- | -------- |
| Create Notification       | Low        | Medium usage | Split required from Subscription                  | Low           | Notification (inc. status), Message status, Subscription event | User, Subscription, Message, Notification | Separate |
| Send Message              | Low        | Low usage    | Split required from Subscription                  | High          | User Id, Message, Message Id                                 | User (Customer, Dietician), Message       | Separate |
| Send Email                | Low        | Medium usage | Split required from Subscription                  | Medium        | User email address                                           | User                                      | Separate |
| Subscription (add/remove) | Medium     | Medium usage | Split required from Notification, Message & Email | Low           | User Id, Forum/Event/Class Id, Subscription                  | User, Forum, Event, Class, Subscription   | Separate |

[ADR: ...]()

### Medical

| Functionality         | Volatility | Scalability  | Fault Tolerance              | Data Security | Data Transactions     | Data Dependencies  | Workflow                |
| --------------------- | ---------- | ------------ | ---------------------------- | ------------- | --------------------- | ------------------ | ----------------------- |
| Test Administration   | Medium     | Medium usage | Split required from customer | Medium        | Test                  | Test               | Separate                |
| Result Administration | Medium     | Medium usage | Split required from customer | High          | Test, User Id, Result | Test, Result, User | Similar to Add/Update   |
| Add/Update Result     | Medium     | Medium usage | Split required from admin    | High          | Test, User Id, Result | Test, Result, User | Similar to Result Admin |

[ADR: ...]()

### Data Store

See [Datastore Solution Overview](../2.SolutionBackground/datastore/README.md).

---

## Integration points for Farmacy Family

| System        | Direction           | Elements         | Reasoning                                                    |
| ------------- | ------------------- | ---------------- | ------------------------------------------------------------ |
| Farmacy Foods | 2-way               | Customer         | So that Farmacy Foods can identify transactional customers who have not become Engaged customers of Farmacy Family in order to retry engagement. |
| Farmacy Foods | Family to Foods     | Analytics        | Optimise the content of geographically located smart fridges (medical data linked to geographical location), optimise engagement programme for transactional customers (onboarding analytics to inform the engagement programme for transactional customers of Farmacy Foods) |
| Dietician     | Family to Dietician | Customer Profile | Dieticians can be given permission to access customer medical information in the customer profile (inherit permission from an associated clinic) |
| Dietician     | 2-way               | Message          | Dieticians and customers can message each other              |
| Clinic        | Family to Clinic    | Customer Profile | Clinics can be given permission to access customer medical information in the customer profile |
| Clinic        | 2-way               | Message          | Clinics and customers can message each other                 |

Next Steps:

- [ ] Make decisions and record in ADRs about system granularity.

---

[> Home](../README.md)   [> Problem Background](README.md)
