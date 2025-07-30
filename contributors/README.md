---
description: Consistency, clarity, and collaboration in code
---

# Contributor Documentation

Welcome to the Contributors area of our documentation. This section provides internal developers and collaborators with the knowledge, structure, and shared understanding necessary to contribute effectively to the platform. Whether you're extending functionality, integrating services, or improving internal tooling, this is your hub for technical alignment and team standards.

> Please note this section is a work-in-progress, with a lot of content that is under review and revision, and not yet published. You are likely to see something new here every week, so check back regularly.

## Values

The principles that guide how we build, collaborate, and make decisions.&#x20;

This section anchors the technical documentation in the broader goals of quality, usability, and team trust. Here you'll find things like our design and engineering philosophy; details about accessibility, security, and performance priorities; and information about our collaboration and review culture

👉 _Keep these values in mind when making architectural and implementation choices._

***

## Architecture

Understand the high-level structure of the system, including service boundaries, deployment topology, and integration points.&#x20;

This section outlines how components interact, where responsibilities lie, and how the system scales and evolves. Here you'll find system overview diagrams, service boundaries, communication flows, and deployment models.

👉 _Start with this section to get a holistic view of how the system is designed._

***

## Domain models

Get familiar with the core business concepts and how they are represented in code.&#x20;

This section defines the primary entities, their relationships, and the domain-driven design principles that guide model construction. Here'll find things like entity definitions; specifications for aggregates, value objects, and invariants; and the mapping between business logic and technical implementation.

👉 _Use this section when designing features that touch core business logic._

***

## Coding conventions

Documented rules and stylistic preferences that keep our code and processes consistent.&#x20;

From naming conventions and folder structures to testing strategies, this section supports clarity and maintainability. Here you'll find guidelines for naming and structuring code; norms for writing tests and docs; as well as descriptions for our branching, commit, and review practices.

👉 _Follow these conventions when writing code, tests, or documentation._

***

## Implementation patterns

A library of reusable patterns for solving common problems in a consistent way. These include UI interaction patterns, error handling approaches, data loading strategies, and more.

👉 _Consult this section to follow (or contribute) standardized solutions._

***

## Tools and utilities

Tips and tricks to streamline platform development, debugging, and diagnostics.&#x20;

This section provides some "extra" information about the tools used (and recommended!) by our contributors. This includes things like IDE setup, command-line tooling, build and packaging scripts, and local development environment configuration.

👉 Use this section to align your local development environment with the core team.

***

## Internal code reference

A comprehensive, indexed and searchable reference of internal documentation generated directly from the source code using [DocFX](https://dotnet.github.io/docfx/), including interfaces, kernel libraries, application libraries, and infrastructure libraries. This section helps you understand existing capabilities and how to safely extend or consume them.

👉 _Reference this section when modifying platform source code._

***

{% hint style="info" %}
💡 **New here?** Start with the Architecture and Values sections before diving into code.
{% endhint %}
