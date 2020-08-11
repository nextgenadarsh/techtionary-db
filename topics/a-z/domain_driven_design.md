# Domain Driven Design

- is a method and a process for designing complex systems
- objective is to understand exact domain problems and then draft a model that can be written in any language or set of technologies
- is a blueprint which can be implemented by microservices

## Characteristics of domain-driven model

- should focus on a specific business model not multiple
- should be reusable
- should be designed to be called in a loosly coupled way
- should be designed independent of persistence implementation
- should not be based on any infrastructure framework

## Guiding Principles

- ### Capture the domain model, in domain terms, through interactions with domain experts.
### 
- ### Embed the domain terminology in the code
- ### Protect the domain knowledge from corruption by other domains, technical subdomains, etc.
  - Put `translators` at the boundaries between subdomains to keep them from depending upon each other's structures unnecessarily, and also to prevent the blurring of the meaning of domain terms.

## Things To Remember

- If you find yourself modeling computer-y things. stop. You have gone too dip.
- **Intension-revealing interfaces:** When you being to embed the domain model in your code you should name classes as well as methods same as real world counterparts.
- **Context Mapping:** It consists of identifying and classifying the relationships between bounded contexts within a domain.


