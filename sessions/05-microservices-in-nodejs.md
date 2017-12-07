# Building Microservices in NodeJS
Small, independently developed services that perform specific tasks. Should be small enough to be torn down and rewritten completely within 1-2 sprints.

## Advantages
* Separation of concerns
* Smaller, faster deployments
* Technological heterogeneity
* Resilience

## Common Stumbling Blocks
1. **Infrastructural Complexity**   
   Large number of services with heterogeneous stacks becomes a devops issue.
   * Pick a CI/CD tool
   * Pick a good platform service with good APIs for quick build-up/tear-down
   * Containerization technologies (Docker, etc.)
     * Build once, run everywhere; single image used in all environments
   * kubernetes (container orchestration platform) for monitoring, management (automatic scaling, etc.), service discovery, logging
1. **Microservice Overhead**   
   How to deal with standardization and tooling across all service repositories.
   * NodeBootstrap helps to create new microservices using templates and code generation
   * Some kind of scaffolding tool to help with the problem of bootstrapping, maintenance, tooling, etc.
1. **Lock-step Deployments**   
   How to deal with all the insane interdependencies in deployment.
   * Eliminate lock-step deployment by attempting to ensure that services are autonomous and have minimal interdependencies.
   * Domain-driven design can be used to ensure that all domains are correctly and comprehensively defined.
   * Eventstorming (from "brainstorming"). Get everyone together and figure out all events possible and then organize them visually. Use post-it notes. Where are the boundaries?
   * When dependencies exist, implement changes from leaf to root.
1. **Inside vs. Outside**   
   Differentiate between internal use and external use; conflating the two into one service means they both have to change at the same time.
   * Create discrete microservices for external APIs so that they can change independently.
     * These act as a facade for access to the internal APIs.

## People and the Organization
* Employees/teams have to move to this pattern conceptually/mentally.
* Engage the whole company to figure out what the impacts are and what the whole picture is for the change.
