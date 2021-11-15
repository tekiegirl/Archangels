[> Home](../README.md)    [> Solution Background](README.md)
[< Prev](Deployment.md)  |  [Next >](../4.ADRs/README.md)

---

# Project Roadmap

The following roadmap assumes Farmacy Foods is already in existence. If both systems were developed in parallel it is suggested that they could be more closely linked within AWS, possibly using the same event log and therefore not requiring specific interfaces between Farmacy Foods and Farmacy Family.

## Current System

The following diagram shows the conceptual design of the Farmacy Foods system, expected to be in existence:

![ff-archcolider-services](../assets/images/ff-archcolider_Overview_v1.png)

[image source: [Archcolider GitHub](https://github.com/ldynia/archcolider/blob/master/img/FF_Overview_v1.PNG)]

## First Iteration

**Aim**: Implement interfaces between Farmacy Foods and Farmacy Family, identifying if any unexpected changes are required to Farmacy Foods other than adding an interface.

### Main Tasks

- Develop Interface component within Farmacy Foods, for interfacing with Farmacy Family (and potentially other systems in the future)
- Develop Interface component within Farmacy Family, for interfacing with Farmacy Family, Clinic data (and potentially other systems in the future)
  - Only Farmacy Family interface to be developed in this iteration
- Components required to be set up in AWS for testing to take place against components not currently developed (event log, etc).
- Develop Tests and test data (especially for Family where there will be no other components built yet) to ensure interfaces are working as desired.
  - Development team to decide whether to use BDD, TDD or similar, in line with current testing and skills.
- Develop required Authentication and Authorisation components for Interface.

## (Suggested) Second Iteration

**Aim**: Implement Analytics and the Analytics Datastore (data to analyse and storage of analytics results), so that analytics can be run on Farmacy Foods data, even before the rest of the Farmacy Family system is operational.

### Main Tasks

- Develop graph datastore for analytics data and results
- Develop Analytics component
  - Elements for Farmacy Foods only
- Any additional authentication and authorisation development required
- Integration testing, in line with testing developed for first iteration

## Subsequent Iterations

The following is a suggested order of priority for developing the remainder of the Farmacy Family system, and in based on the concerns of stakeholders, although stakeholder priorities may change. 

### Considerations

- Development could be done in tandem for different components (including those in iteration one and two).
- Tandem development should be planned with consideration for when other components will be required
  - Especially in relation to the format of event messages in order to avoid volatility in interface contract code
- Mocks and test data should be used for integration with other components within the system when developing, and for testing in general.

### Suggested Prioritisation

- User Management (including onboarding and profiles)
- Community (Forums, Events, Classes - possibly prioritise one and then add others after Medical)
- Medical (Customer Results, Clinic Tests, secure medical data sharing, etc)
- Medical Analytics & Medical Interface (Clinic, for loading data for analytics)
- Resources (Educational, etc)

## Intended System

The following diagram shows the intended conceptual design of the Farmacy Family system, including the interface to Farmacy Foods:

![ContainerDiagram](../assets/diagrams/ContainerDiagram.png)

---

[> Home](../README.md)    [> Solution Background](README.md)
[< Prev](Deployment.md)  |  [Next >](../4.ADRs/README.md)
