[> Home](../README.md)    [> Solution Background](README.md)
[< Prev](ArchitecturePatterns.md)  |  [Next >](DataStore.md)

---

# Conceptual System Design

The following show the conceptual design for the Farmacy Family system. More information about C4 modelling can be found in the [C4 Models section](../3.ViewsAndPerspectives/C4Models/README.md) of this documentation.

## C4 Model Key

![C4ModelKey](../assets/diagrams/C4ModelKey.png)

## Farmacy Family Context Diagram

The Context diagram shows how the Farmacy Family system interacts with people and systems outside of the Farmacy Family system, and how it fits in to the overall landscape.

Four types of user have been identified; Transactional Customer, Engaged Customer, Dietician and Administrator. These are further defined in [Actors, Actions & Significant Scenarios](../1.ProblemBackground/ActorsActionsAndSignificantScenarios.md), with full definitions in the [Glossary](../Glossary.md).

- The Administrator is required in order to manage other users, settings and data within the system. These privileges should only be given to specific, trusted employees of Farmacy Family.
- The Dietician is a user employed by a Clinic. The link to the Clinic gives the Dietician permission to access medical profiles and messages that have been shared with / sent to the Clinic. It is expected that there will be fine-grained authorisation controls so that a Dietician can be authorised to have this access, partial access (e.g. just read messages or see the inbox), or not have access at all.
- A Transactional Customer receives an invitation from Farmacy Foods to become an Engaged Customer of Farmacy Family.

![Context Diagram](../assets/diagrams/ContextDiagram.png)

## Farmacy Family Container Diagram

The Container diagram shows elements/domains (containers) within the Farmacy Family system and how they relate to each other and to people and systems outside of the Farmacy Family system. Domains within the system are further broken down into Component diagrams at the next level, and so the Container diagram hides implementation details in order to see the larger picture.

![Container Diagram](../assets/diagrams/ContainerDiagram.png)

## Architecturally Significant Component Diagrams

The following are the most architecturally significant Component diagrams for the Farmacy Family system. Further Component diagrams can be created when other domains in the system are required to be developed in the [Roadmap](Roadmap.md).

### Medical Management

#### Relevant ADRs

- [005 use-crypto-shredding](../../4.ADRs/005-use-crypto-shredding.md)
- [010 We-will-use-a-secure-data-solution](../../4.ADRs/010-We-will-use-a-secure-data-solution.md)
- [017 Separate the Medical domain](../../4.ADRs/017-We-will-split-medical-domain.md)

![Medical Component Diagram](../assets/diagrams/MedicalComponentDiagram.png)

### User Management

#### Relevant ADRs

- [011 Separate the User domain](../../4.ADRs/011-We-will-separate-the-user-domain.md)
- [019 Use Authentication and Authorisation for human-system integration](019-use-auth-for-human-system-integration.md)

![User Component Diagram](../assets/diagrams/UserComponentDiagram.png)

---

[> Home](../README.md)    [> Solution Background](README.md)
[< Prev](ArchitecturePatterns.md)  |  [Next >](DataStore.md)