[> Home](../README.md)  [> Problem Background](README.md)
[< Prev](ArchitectureAnalysis.md)  |  [Next >](ConstraintsAndAssumptions.md)

---
# Actors, Actions & Significant Scenarios

The Actors on the system (typically the human users but can also include other systems) and the actions they take help to form the key scenarios, or flows, of the system. The following identifies the significant actors, actions and key scenarios that will inform the architecture of the Farmacy Family system.

## Actors & Actions

The identified actors of Farmacy Family and their actions are as follows:

| Actor                  | Actions                                                      |
| ---------------------- | ------------------------------------------------------------ |
| Transactional Customer | * Places meal order on Farmacy Foods<br />* Registers on Farmacy Family to become an engaged customer<br /> |
| Engaged Customer       | * Creates Farmacy Family profile/account (onboarding) <br />* Shares medical profile with Clinic/Dietician<br />* Interacts with fellow Engaged Customer <br />* Interacts with Dietician<br />* Registers for Event<br />* Registers for Class |
| Dietician              | * Interacts with Engaged Customer<br />* Accesses health data of the Engaged Customer<br />* Gives customized diet plan to the Engaged Customer |
| Administrator          | * Manages Class<br />* Manages Event<br />* Manages Farmacy Family User (Clinic, Dietician, Customer, Admin) |
| Clinic                 | * Provides analytics data to Farmacy Family, to improve engagement<br />* Accesses health data of the Engaged Customer (as Dietician user) |

## Architecturally Significant Scenarios

The following are the most architecturally significant scenarios/flows, derived from the Actors and Actions above, which will shape the architecture of the Farmacy Family system.

### 01  Onboard Farmacy Foods Customer to Farmacy Family

A Transactional Customer (Farmacy Foods customer) joins Farmacy Family to become an Engaged Customer.

![Scenario-OnboardFFoodsCustomer](../assets/diagrams/Scenario-OnboardFFoodsCustomer.png)

### 02 Share Medical Data with Clinic

An Engaged Customer (Farmacy Family customer), chooses to share their medical data with a specific Clinic.

![Scenario-ShareProfileWithClinic](../assets/diagrams/Scenario-ShareProfileWithClinic.png)

### 03 Request Dietician Advice

An Engaged Customer (Farmacy Family customer) requests advice from a Clinic, based on the Engaged Customer's medical profile.

![Scenario-RequestDieticianAdvice](../assets/diagrams/Scenario-RequestDieticianAdvice.png)


------

[> Home](../README.md)  [> Problem Background](README.md)
[< Prev](ArchitectureAnalysis.md)  |  [Next >](ConstraintsAndAssumptions.md)
