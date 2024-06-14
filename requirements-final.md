# Architectural Requirements

This is a living document with the architectural requirements of FullSnack's new customer-facing web application.

For more information, check out the [Project Spec](./spec.md).

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

- Customers can browse the app without being authenticated.
- Customers can add food items to a shopping cart (with or without authentication).
  - We won't be able to assume a logged in customer at all times, so we might need to come up with the concept of a "visitor" customer to keep track of their actions (like adding items to the shopping cart).
- Customers can search for restaurants by name.
- Customers can search for restaurants by type of food.
  - Does search has an auto-complete UI? If so, do we have an API endpoint for the auto-complete feature?
- After placing an order, customers can see a real-time tracker of their order status.
- Once an order is out for delivery, customers can see a real-time map showing the driver's current location.
  - We'll need to connect to the web sockets server to show the real-time tracker and map.
- Customers can view ratings and reviews from other users.
  - Fetching reviews should not block the rendering of the restaurant page.

## Other Influencers

- Currently, the frontend team is a single team of 4 developers, but this is expected to change as the number of developers is expected to triple in size over the next year.
- Every frontend developer on the team has experience working with React and Next.js, and some of them are also comfortable working with Vue.js and Laravel.
- Not everyone on the team is comfortable working with TypeScript.
