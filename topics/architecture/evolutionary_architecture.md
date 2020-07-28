# Evolutionary Architecture

## Characteristics

### Modularity & Coupling

- Ability to separate components along well defined boundaries
- Evolutionary architecture supports some level of modularity, typically at the technical architecture(for example, the classic layerd architecture)

### Organized Around Business Capabilities

- Features modularity at the domain architecture level as well, inspired by Domain Driven Design.
- SOA architecture : Partitioning along technical layers
- Serice-based architecture: Partitioning along microservice's inspired Domain

### Experimentation

- Often designed around routing between services to define applications, allowing several versions of particular service to exist within ecosystem.
- It allows experimentation and gradual replacement of existing functionality.

## Principles

### Fitness Functions

- An architectural fitness function specifies what our target architecture looks like. Some systems need `high uptime` while others `throught` or `security`.
- Architectural decisions are scored relative to the fitness function so that we can see that architecture is evolving in right direction.
- Emergent architecture:
- Evolutionary architecture:

![Radar Chart](https://insights-images.thoughtworks.com/Microservices20as20an20Evolutionary20Architecture01_ad97c413fac60136c38d5de6dd203711.png)

### Bring the Pain Forward

- Inspired by eXtreme Programming community
- Identify potential pain cause and force yourself to do it more often and earlier, which encourages you to automate the pain away and identify issues early.
- Practices like CI/CD, auto-provisioning, database migrations make evolutionary architecture easier by removing common pain points for change.

### Last Responsible Moment

- Wait for last responsible moment to make architecture decisions.
- Fitness function provides the guidance for that decision.
- Critical success decisions should however be made earlier.


> Reference
- https://www.thoughtworks.com/insights/blog/microservices-evolutionary-architecture