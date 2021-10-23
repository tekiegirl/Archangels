# Clarifications

| Source                  | Clarification                                                |
| ----------------------- | ------------------------------------------------------------ |
| Kata Kick-Off Event Q&A | There is no tight feedback loop, as there is normally when architecting a solution, so it is part of the challenge to get clarity into the architecture as the judges cannot ask questions. |
|                         | Clinics only integrate with Farmacy Family, not Farmacy Food. |
|                         | Security/Authentication: yes, medical data integration with clinics is on on permission of the customer |
|                         | What is the IT department of the pharmacy foods? startup so has one, make reasonable assumptions |
|                         | Community is the priority feature.                           |
|                         | Off The Shelf is an option if it meets the requirements. There are trade-offs with this. |
|                         | There are new requirements compared to Farmacy Foods, so the solution may require something on-prem or not in AWS. |
|                         | If there is justification the Farmacy Foods architecture can be modified. Indicate it and use ADRs. |
|                         | For integration with 3rd party providers, can we assume any protocol, mechanism such as REST or is there any specific requirement here? No specific requirements, just document why. |
|                         | Geography: not multinational yet, so assume USA, Michigan, but could get larger, support community in a particular geographic location |
|                         | Farmacy Foods technical expertise: assume microservice and cloud. |
|                         | What type of communication is allowed in communities? in person and online |
|                         | Do we have plans to deal with large objects (BLOBs like video, sound, etc)? yes, permanent global resources |
|                         | Are Farmacy foods customers subscriptions based? Like monthly, yearly etc. Would that change for Farmacy family? no plan for membership fees, currently transactional. |
|                         | Is an engaged member == engaged customer? Or can anyone join the community? normal pipeline would be via Foods, but could sign up just to Family |



------

[> Home](README.md)
