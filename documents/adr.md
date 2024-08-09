# ADR 1: Using Next.js for FullSnack's Customer Web Application

## Status

Accepted

## Context

As we prepare to begin development of FullSnack's new customer web application, one key decision that we need to make is which UI framework we're going to use and what infrastructure we need to deploy it.

The objective is to create a robust, scalable, and performant web application that can meet our customers' needs efficiently, and given our tight timeline of 4 months, we need to be strategic about tech stack decisions to ensure rapid development and high-quality output.

## Decision

We have decided to use Next.js as the framework for developing FullSnack's new customer web application and host it on our own AWS infrastructure using SST.

## Consequences

### Positive Consequences

- **Rapid Development:** Given that all team members are already familiar with Next.js, we can leverage this expertise to accelerate the development process. This will help us meet our tight deadlines without sacrificing quality.

- **Feature-Rich Framework:** Next.js offers a range of features that are beneficial for modern web development, including server-side rendering, static site generation, and API routes. These features will enable us to build a performant and SEO-friendly application.

- **Flexibility in Deployment:** Although we cannot use Vercel for deployment, our prototype with the devops team using SST (Serverless Stack) on AWS has shown that we can successfully deploy Next.js applications on our own infrastructure. This ensures that we can leverage Next.js features without being dependent on a specific hosting provider.

- **Community and Ecosystem:** Next.js has a strong community and ecosystem, providing us with a wealth of resources, plugins, and third-party integrations that can enhance our development process and application capabilities.

### Negative Consequences

- **Initial Setup and Configuration:** Deploying Next.js on our own AWS infrastructure requires an initial setup and configuration phase. While our prototype indicates feasibility, this setup will still require coordination with the devops team and some initial effort.

- **Learning Curve for Custom Deployment:** The team will need to familiarize themselves with SST and the specifics of deploying Next.js on AWS, which may take some time initially, even though it won’t affect the overall development timeline significantly.

- **Dependence on Internal Infrastructure:** By choosing to deploy on our own infrastructure, we assume full responsibility for the management, scaling, and maintenance of the deployment environment. This requires a reliable and well-coordinated devops team to ensure smooth operations.

Overall, the decision to use Next.js aligns well with our current capabilities, resources, and project requirements, allowing us to deliver a high-quality customer web application within the desired timeline.
