[> Home](../../README.md)    [> Views & Perspectives](../README.md)

---

# C4 Infrastructure Models

A C4 model is a common set of abstractions to create used to describe the static structure of a software system; these abstractions having four levels: **software system**, **containers**, **components** and **code**. **People** use the software system.

The following diagrams use the standard C4 notation.

## C4 Model Key

![C4ModelKey](../../assets/diagrams/C4ModelKey.png)

## Context Diagram (Level 1 - top level)

A **System Context** diagram provides a starting point, showing how the software system in scope fits into the world around it.[^](#expl) 
This diagram shows how the main users of Farmacy Family interact with the system, and the other systems that Farmacy Family system interacts with.

![Context Diagram](../../assets/diagrams/ContextDiagram.png)

## Container Diagram (Level 2)

A Container diagram zooms into the software system in scope, showing the high-level technical building blocks.[^](#exp1) The following diagram breaks down the Farmacy Family system into groups of related functionality, or domains, and shows how they interact with each other and how the users of the system interact with the functionality.

![Container Diagram](../../assets/diagrams/ContainerDiagram.png)

## Component Diagrams (Level 3)

A **Component** diagram zooms into an individual container, showing the components inside it.[^](#expl)
The following diagrams break down the containers/functionality shown above further, into components which represent individually deployable services.

#### Relevant ADRs

- 

### Medical Management

The following diagram shows the individually deployable services in the Medical Management domain, and how they interact with each other, users and other domains.

#### Relevant ADRs

- 

![Medical Component Diagram](../../assets/diagrams/MedicalComponentDiagram.png)


### Analytics Management

The following diagram shows the individually deployable services in the Analytics Management domain, and how they interact with each other, users and other domains.

#### Relevant ADRs

- 

### User Management

The following diagram shows the individually deployable services in the User Management domain, and how they interact with each other, users and other domains.

#### Relevant ADRs

- 

### Events Management

The following diagram shows the individually deployable services in the Events Management domain, and how they interact with each other, users and other domains.

#### Relevant ADRs

- 

### Datastore Management

The following diagram shows the individually deployable services in the Datastore Management domain, and how they interact with each other, users and other domains.

#### Relevant ADRs

- 

### Messaging Management

The following diagram shows the individually deployable services in the Messaging Management domain, and how they interact with each other, users and other domains.

#### Relevant ADRs

- 



---

<a id="expl"></a>^ explanations from https://c4model.com/

---

[> Home](../../README.md)    [> Views & Perspectives](../README.md)