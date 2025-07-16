---
description: Consistency, clarity, and collaboration in code
---

# Contributors

Welcome to the Contributors area of our documentation. This section is designed to provide internal developers and collaborators with the knowledge, structure, and shared understanding necessary to contribute effectively to the platform. Whether you're extending functionality, integrating services, or improving internal tooling, this is your hub for technical alignment and team standards.

> Please note this is (very much!) a work-in-progress, with a lot of content still "under construction" and not yet published. You're likely to see something new here every week, so check back regularly.

***

## Architecture

Understand the high-level structure of the system, including service boundaries, deployment topology, and integration points. This section outlines how components interact, where responsibilities lie, and how the system scales and evolves.

* System overview diagrams
* Service boundaries and communication flows
* Deployment models and infrastructure considerations

👉 _Start with this section to get a holistic view of how the system is designed._

***

## Domain models

Get familiar with the core business concepts and how they are represented in code. This section defines the primary entities, their relationships, and the domain-driven design principles that guide model construction.

* Entity definitions and responsibilities
* Aggregates, value objects, and invariants
* Mapping business logic to implementation

👉 _Use this section when designing features that touch core business logic._

***

## Internal code reference

A comprehensive, indexed and searchable reference for internal documentation generated directly from the source code using [DocFX](https://dotnet.github.io/docfx/), including interfaces, kernel libraries, application libraries, and infrastructure libraries. This section helps you understand existing capabilities and how to safely extend or consume them.

* Class/method/property definitions

👉 _Reference this section when modifying platform source code._

***

## Patterns

A library of reusable patterns for solving common problems in a consistent way. These include UI interaction patterns, error handling approaches, data loading strategies, and more.

* UI patterns and component behaviors
* Backend workflow patterns
* Async communication and retries

👉 _Consult this section to follow or contribute standardized solutions._

***

## Conventions

Documented rules and stylistic preferences that keep our code and processes consistent. From naming conventions and folder structures to testing strategies, this section supports clarity and maintainability.

* Naming and structuring code
* Test writing and documentation norms
* Git branching, commit, and review practices

👉 _Follow these conventions when writing code, tests, or documentation._

***

## Values

The principles that guide how we build, collaborate, and make decisions. This section anchors the technical documentation in the broader goals of quality, usability, and team trust.

* Design and engineering philosophies
* Accessibility, security, and performance priorities
* Collaboration and review culture

👉 _Keep these values in mind when making architectural or implementation choices._

***

> 💡 **New here?** Start with the Architecture and Values sections before diving into code.
