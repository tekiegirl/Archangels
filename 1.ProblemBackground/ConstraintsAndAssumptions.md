# Constraints

1. Farmacy Family must integrate seamlessly with the design for Farmacy Foods, although some changes to Farmacy Foods may be required for the integrations required.
2. The onboarding process for Farmacy Family will be initiated by an invitation to join Farmacy Family, sent by Farmacy Foods to a transactional Farmacy Foods customer, and will need to integrate with Farmacy Foods to retrieve the customer's Farmacy Food account details, securely, and cope with not finding a match for some reason.
3. Anyone could sign up for an account with Farmacy Family, so the onboarding process will need to be able to onboard an engaged customer without a connection to a transactional customer in Farmacy Foods.
4. Medical data is highly sensitive and so the system must implement high security around this data as a minimum.
5. The initial architecture in this repository must be completed by midnight US Eastern Time, 31st October 2021.

# Assumptions

1. All medical and dietary information relating to a customer will be added by the customer themselves. A clinic will not update or add medical information for a customer, only access the medical information when given permission to by the customer.
2. Analytics is not required for the forums, events, classes and static media provided by Farmacy Family. This enables COTS software to be more easily assessed against the requirements for Farmacy Family. Bespoke options could be added at a later date, or analytics built around COTS if needed in the future.

------

[> Home](../README.md)  [> Problem Background](README.md)

