# Project Spec

![Cover](./Cover.png)

## 0. Project Overview

**FullSnack** is a recently launched **food delivery service** (similar to Uber Eats, or DoorDash) that is looking to **rebuild their customer-facing web application**, following a successful MVP.

FullSnack currently has a small team of four frontend engineers, but the team is expected to triple in size in the next 12 months. It's clear that the current customer-facing web app used for the MVP will not scale to the needs of a larger team.

Your goal as the frontend architect of this project is to **design the architecture of FullSnack's customer-facing web application**. This includes gathering requirements, designing an architecture that meets those requirements, and support the frontend team during implementation.

## 1. FullSnack Software System

_This section describers the entire FullSnack software system. This includes the users of the system, as well as all the applications, databases, and APIs the system is made of. The application that we're building (the customer-facing web app) is a part of this system._

### System Context

_This is a zoomed out view of the FullSnack system and the context around it. The system context diagram below follows the guidelines of the C4 Model for visualizing software architecture._

#### System Users

- **👩🏻 Customer** — Buyers purchasing food through FullSnack. They use the Customer Web App client to search restaurants and food options, make orders, pay for them, and keep track of the order status.
- **🧑🏽‍🍳 Restaurant** — Restaurant owners and employees. They use the Restaurant Web App client to receive orders made by customers, update the order's status, and update their menu options in the system.
- **🛵 Driver** — Delivery drivers. They use the Driver Mobile App client to collect orders from restaurants and deliver them to customers.

#### External Systems

- **Third-party Payment System** — Third-party software system used by FullSnack's applications to manage payments, refunds, and credit card information.
- **FullSnack Admin System** — Software system used by FullSnack's employees such as system administrators and customer support agents to manage and moderate the FullSnack system.

#### System Context Diagram

![System Context Diagram](./System%20Context%20Diagram.png)

### System Containers

_These are the building blocks of the system. Use this list as well as the system context diagram above to build the container diagram for the FullSnack software system._

- **Customer Web App** — This is the app that we're designing the architecture for. It's a web application used by customers to search for restaurants and make food delivery orders.
- **Restaurant Web App** [React SPA] — The web application used by restaurants to receive orders and update their status and manage their menu options.
- **Driver Mobile App** [Native iOS + Android] — The app used by Drivers to collect orders from restaurants and deliver them to customers.
- **Core API** [Java Spring Boot] — REST API used by all mobile and web apps within the system to manage customer information, orders, and restaurant menu items. The Core API also acts as a gateway to external systems (i.e. third-party payment and admin systems.)
- **Core Database** [MySQL] — Main data store for the application. The Core API reads from and writes to this database.
- **WebSockets Server** [Socket.io] — Used to communicate real-time events with registered clients (e.g. updating order status or broadcasting a driver's location.)

#### Container Diagram

_To be completed... by you! See Exercise 1 for more details._

---

## 2. FullSnack Customer Web Application

_This section describes the customer-facing application in more detail. It's meant to give you a high-level understanding of the app we're designing the architecture for, and it should have enough information to complete the exercises in the workshop._

### UI Designs

You can find detailed UI Designs in this Figma file.

// SCREENSHOT

### Functional Requirements

_This section lists some of the main functional requirements of FullSnack's web app. This is more of a functionality overview to help guide some of your architectural decisions._

- Customers can browse the app without being authenticated.
- Customers can search restaurants by name and type of food.
- Customers can create an account and authenticate at any point.
- Authenticated customers can add restaurants and food items to their favorites.
- Authenticated customers can add food items to a shopping cart.
- Customers can order food from a restaurant, including multiple items per order.
- After placing an order, customers can see a real-time tracker of their order status.
- Once an order is out for delivery, customers can see a real-time map showing where the driver is currently at.

### Constraints

- Backend is already developed
- Must be responsive and fully functional on mobile devices
- Performance is very important
- A functional version must be shipped in 4 months

### Quality Attributes

- UX and Performance is really important. There's a lot of competition out there, so if the app is slow, or the UX is confusing, people will go to a competitor.

As an incentive, FullSnack is offering various promotions and discounts to get customers to use the app instead of a competitor's.

### Team Composition

The FullSnack Frontend Team consists of:

- 3 frontend engineers - they have experience with React and Tailwind
- 2 senior frontend engineers - they have experience with React, Tailwind, Svelte, and TypeScript
- 1 senior full-stack engineer
- You ()
