[> Home](README.md)
[< Prev](README.md)  |  [Next >](Glossary.md)

---

# Clarifications

The following are verbal clarifications to the original requirements set out in the [2021-fall-kick-off presentation](assets/docs/2021-fall-kick-off.pdf). These have been taken into account in our problem analysis and solution design.

| Clarification Id | Clarification                                                | Source                  |
| ---------------- | ------------------------------------------------------------ | ----------------------- |
| 01               | There is no tight feedback loop, as there is normally when architecting a solution, so it is part of the challenge to get clarity into the architecture as the judges cannot ask questions. | Kata Kick-Off Event Q&A |
| 02               | Clinics only integrate with Farmacy Family, not Farmacy Food. | Kata Kick-Off Event Q&A |
| 03               | Security/Authentication: yes, medical data integration with clinics is on on permission of the customer | Kata Kick-Off Event Q&A |
| 04               | What is the IT department of the pharmacy foods? startup so has one, make reasonable assumptions | Kata Kick-Off Event Q&A |
| 05               | Community is the priority feature.                           | Kata Kick-Off Event Q&A |
| 06               | Off The Shelf is an option if it meets the requirements. There are trade-offs with this. | Kata Kick-Off Event Q&A |
| 07               | There are new requirements compared to Farmacy Foods, so the solution may require something on-prem or not in AWS. | Kata Kick-Off Event Q&A |
| 08               | If there is justification the Farmacy Foods architecture can be modified. Indicate it and use ADRs. | Kata Kick-Off Event Q&A |
| 09               | For integration with 3rd party providers, can we assume any protocol, mechanism such as REST or is there any specific requirement here? No specific requirements, just document why. | Kata Kick-Off Event Q&A |
| 10               | Geography: not multinational yet, so assume USA, Michigan, but could get larger, support community in a particular geographic location | Kata Kick-Off Event Q&A |
| 11               | Farmacy Foods technical expertise: assume microservice and cloud. | Kata Kick-Off Event Q&A |
| 12               | What type of communication is allowed in communities? in person and online | Kata Kick-Off Event Q&A |
| 13               | Do we have plans to deal with large objects (BLOBs like video, sound, etc)? yes, permanent global resources | Kata Kick-Off Event Q&A |
| 14               | Are Farmacy foods customers subscriptions based? Like monthly, yearly etc. Would that change for Farmacy family? no plan for membership fees, currently transactional. | Kata Kick-Off Event Q&A |
| 15               | Is an engaged member == engaged customer? Or can anyone join the community? normal pipeline would be via Foods, but could sign up just to Family | Kata Kick-Off Event Q&A |

------

[> Home](README.md)
[< Prev](README.md)  |  [Next >](Glossary.md)
