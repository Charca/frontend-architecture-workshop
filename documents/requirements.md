# Architectural Requirements

This is a living document with the architectural requirements of FullSnack's new customer-facing web application.

For more information, check out the [Project Spec](./project-spec.md).

## Business Goals

| Stakeholder                 | Goal                                                                                         | Context                                                                                              |
| --------------------------- | -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Julio (CEO)                 | Increase number of customer orders by 100% in one year                                       | As a new player in the market, FullSnack needs to attract new customers with their exciting new app. |
| Megan (VP of Engineering)   | Improve team velocity and cycle time by 25%                                                  | The new architecture should allow developers to ship features faster without compromising quality.   |
| Lauren (Frontend Developer) | Ship code to production confidently, without fear of breaking her teammate's features        | The current big ball of mud architecture makes it hard to visualize the impact of a code change.     |
| Maxi (Customer Persona)     | Order delicious food from his phone or computer and have it delivered as quickly as possible | Maxi is hungry and wants to eat a taco plate right now.                                              |

## Contraints

| Constraint                                                              | Context                                                                                                                              |
| ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| [Technical] Must be deployed on AWS infrastructure                      | Our DevOps team only provides support and monitoring for AWS services.                                                               |
| [Technical] Must be responsive and fully functional on mobile devices   | Over half of our traffic comes from mobile devices and our native mobile application won't be ready to launch for at least 6 months. |
| [Business] Must ship to production by November 2024 (4 months from now) | FullSnack is planning a massive marketing launch in November and this product is a key component of the marketing strategy.          |

## Quality Attributes

| Quality Attribute | Scenario                                                                                                      | Priority |
| ----------------- | ------------------------------------------------------------------------------------------------------------- | -------- |
| Performance       | A user on a mobile device with a 4G connection can load the app in 5 seconds or less.                         | High     |
| Scalability       | The codebase should be modularized to allow and increasing number of frontend developers to work in parallel. | High     |
| Accessibility     | The app should comply with WCAG 2.2 accessibility standards.                                                  | Medium   |
| Performance       | Real-time updates should be broadcast to all listening clients within 15 seconds.                             | Low      |
| Deployability     | Code changes should be deployed to production within 10 minutes of starting a release.                        | Low      |

## Influential Functional Requirements

_To be completed... by you! See Exercise 2 for more details._

## Other Influencers

- Currently, the frontend team is a single team of 4 developers, but this is expected to change as the number of developers is expected to triple in size over the next year.
- Every frontend developer on the team has experience working with React and Next.js, and some of them are also comfortable working with Vue.js and Laravel.
- Not everyone on the team is comfortable working with TypeScript.
