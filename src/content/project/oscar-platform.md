---
name: Oscar P1
shortName: oscar-platform
shortDescription: Micro frontend based next-gen ERP
languages: ['TypeScript', 'Java']
frameworks: ['Vue', 'Spring']
other: ['AWS', 'Architecture Design', 'GH Actions']
type: work
start: 2023-01
---

# Oscar Web Platform (cERP Next Gen)

A container application for next generation web-based ERP solution.

## Work

Working as part of the initial design team, and development team after that. 

Before development, different frameworks were compared and small proof-of-concepts were
written for them to give better insight. Compared frameworks were [Astro](https://astro.build/), 
[Webpack Module Federation](https://webpack.js.org/concepts/module-federation/) 
and [Bit](https://bit.dev/). From these, Module Federation was chosen and development began.
Module Federation was eventually exchanged to Vite's similar plugin.

Development consisted of implementing the container itself, with some applications used through
module federation. The applications were written in a way, which allowed using them as standalone
applications or through the platform.

## Technical specs

Container with Vite and Vue 3. Module federation implemented with non-framework specific
ideology: container can run applications using any framework, sharing dependencies as needed.

Applications written so far in Vue 3. Applications represent portlets ported from [Oscar cERP](/project/cerp/).
Each application can be thought of as a subdomain, in the context of domain driven design. The first application
implemented was related to timetracking.

Stack:
- Vue 3 with TypeScript
- Vite + module federation

## Notable features and work

My most significant contributions in this project.

### Architecture Design

Starting from the beginning with the smaller team doing the initial comparison on the frameworks, we went 
through the options and possibilites in terms of enabler and business features  we want, and some preliminary implementation details.
I took part in the decision making, giving a lot of insight into the details. I had previously done 
[Microfrontends with React](https://www.udemy.com/certificate/UC-a0712b34-c6ba-41a7-a9cc-64d3fe80cd3a/) course from Udemy,
which gave me good expertise on the subject. From the course I also learned the principles for good micro frontend design,
which I would then take into the decision making process.

Throughout the project, working closely with the Product Owner(s), to discuss the features and requirements for
implementing them.

### Module Federation proof-of-concept

Somewhat relating to previous paragraph, implementing a proof-of-concept container application and a low code application
inside it. In the POC, low code functionality was written in the container. Container would then share predefined datasources
and actions etc. with the applications, and the applications could communicate between each other through these features. 
The implementation also tested compatability between frameworks, with Svelte-component talking to Vue-component through
the platform and vice versa. 

The POC was a success and module federation was chosen as the way to proceed. The design relating to low code functionality
was left out of the final platform project, but the design principles were later applied to a low code application, basically
moving the design and logic one step higher. More about the low code application in Generic Editor project.

### AWS and DevOps

Configuring AWS services to enable deploying and displaying the whole platform. Lots of cache and CORS configuration,
routing etc. Configurations to the project and related packages and applications, to support multiple environments.

Implementing workflows to GitHub for automatic testing and deployment:
- Automatic build on pull requests to test integration
  - Aiming for no broken code ever deployed
- Automatic build and deployment from selected branches to AWS

### Testing

Testing configuration for Vitest in a monorepo environment for micro frontend based application.

A lot of time spent on developing internal tools for testing.

Organizing a unit and browser testing workshop to kickstart the testing process for the team.
