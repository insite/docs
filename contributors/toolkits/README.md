---
description: >-
  Internal documentation describing Shift iQ features so administrators and
  developers can perform advanced tasks, troubleshoot, and assist customers
---

# Toolkits

## Purpose

The Toolkits documentation is intended for internal use. Its purpose is to describe Shift iQ features in such a way that administrators and developers can understand the steps to perform more advanced tasks when learning the system, troubleshooting issues, and/or assisting customers with their accounts.

> Note: The term **Toolkit** will be deprecated because it sounds a little too technical. In business contexts we will use these terms in its place: **Domain**, **Plugin**, **Utility**, and **Shell**.
>
> The term **Domain** is considered synonymous with **App** and **Feature Set**, and the term Feature Set may be abbreviated **Features** or **Feature** in documentation and code.
>
> From a technical perspective, Domain, Plugin, Utility, and Shell are toolkit types, where a “toolkit” is understood to be a logical, high-level, subsystem (i.e., a vertical slice of features). The Shift iQ platform contains several toolkits, and each toolkit represents a bounded context of the overall application domain. For example, the Contact toolkit contains functionality related to contact information management.
>
> Refer to this article for a technical discussion of the modular (vertical) software architecture pattern: [Modular Monolithic Architecture](https://medium.com/design-microservices-architecture-with-patterns/microservices-killer-modular-monolithic-architecture-ac83814f6862)

## Convention

The steps to perform an application task should be described in such a way that anyone can follow the steps as a test case to confirm the behaviour of the system meets expectations.

A brief, point-form list of steps is the ideal format, written as a simple, user-friendly “how-to” guide. Screen captures and/or videos are very helpful, whenever possible.

Try to apply a consistent approach to all public customer-facing help topics.

> Note: Many articles on the topic of software help documentation reference Stripe as an excellent example. While authoring and reviewing help content for Shift iQ, if you want to see an example of best practices applied to a real-world documentation site, then visit [Stripe Docs](https://docs.stripe.com/) and [Stripe API Reference](https://docs.stripe.com/api).

### Content structure

Help topics are structured like this:

* Toolkit
  * Subsystem (or Part)
    * Task (a brief sentence phrased as an imperative)

For example:

* Assessment
  * Banks
    * Create a new assessment bank

> Note: We might want to group tasks into scenarios; this will become clear as documentation evolves.

## Help topic checklist

Each page in the internal documentation here is intended for platform administrators and developers.

Each page in the external Help Portal ([https://www.shiftiq.com/help](https://www.shiftiq.com/help)) is intended for customers.

In both places we should follow the same general principles. Here is a checklist to guide the work when we write a new help topic (or update an existing one):

* [ ] The content is a list of numbered steps. If the content includes supportive text that is not explicitly related to specific steps in the task, then this is clearly distinguished in its style/formatting.
* [ ] The content is user-friendly; it is written from a business perspective for a non-technical person.
* [ ] The content can include screen captures and/or videos. This is optional, and can be very useful when it eliminates a lot of text that would otherwise need to be written.
* [ ] The content includes links that cross-reference to related documentation, where applicable.
* [ ] The content does not include any personal information (e.g., email addresses, phone numbers).
* [ ] If a developer changes a part of the system related to the help topic, then anyone (business or technical) can follow the steps to confirm the system’s behaviour is not broken by the change. In other words, the content for the help topic can serve as a test case and as a feature description.
* [ ] The URL for a help topic is readable and SEO-friendly. (This applies to external documentation only.)

## Toolkits = Domains, Plugins, Utilities, and Shells

Each toolkit is a subsystem within the platform. (Technical software architecture documentation often uses the term “module” for this concept. Shift iQ is a modular platform.) Each toolkit contains one or more subsystems, and each subsystem relates to one or more domain entities.

> For example, the Contact toolkit contains subsystems such as Groups, People, and Memberships. Within the Groups subsystem are specific domain entities such as Group, GroupAddress, and GroupSetting.
>
> As another example, the Security toolkit contains a Users subsystem, which contains entities for individual user accounts, connections between users, login failures, and authenticated user sessions.

Shift iQ contains:

* **12 Domain Toolkits**
* **2 Plugin Toolkits**
* **7 Utility Toolkits**
* **3 Shell Toolkits**

### Domains

**Domains** (aka Features or Apps) deliver end-user features to learners, instructors, and administrators.

1. Billing
2. Booking
3. Competency
4. Content
5. Directory
6. Evaluation
7. Learning
8. Messaging
9. Progress
10. Reporting
11. Workflow
12. Workspace

### Plugins

**Plugins** implement integration with external third-party platforms and customizations for specific partitions (or tenants) and organizations.

1. Integration
2. Extension

### Utilities

**Utilities** are intended for internal use by platform administrators and developers for system setup, instrumentation, and telemetry. Some limited access may be granted to some customers.

1. Diagnostic
2. Internal
3. Lab
4. Metadata (platform and database structure)
5. Security (accounts and permissions)
6. Setup (configuration)
7. Timeline (CQRS+ES backbone and service bus)

### Shells

**Shells** are responsible for composition of front-end and back-end features from multiple subsystems to deliver unified, session-aware views for client applications. They act as a bridge between domain-specific subsystems and the user interface, assembling contextual models such as user session state, dashboard metadata, and cross-subsystem summaries. Shells are not responsible for business logic or data ownership, but instead coordinate and shape data from underlying services to support runtime experience delivery, particularly for dynamic front-end rendering and role-based navigation.

1. Lobby
2. Me
3. Portal (orchestration)

### Toolkit aliases

For technical reasons, the following names have aliases:

* Billing also known as Invoices and/or Payments and/or Sales
* Booking also known as Calendar and/or Events and/or Schedule
* Cases also known as Issues
* Competency also known as Standards
* Content also known as Assets
* Directory also known as Contacts
* Learning also known as Courses
* Messaging also known as Messages
* Progress also known as Records
* Timeline also known as Logs and/or Bus
  * Note: Commands, queries, and changes (aka events) are parts of the service bus implementation
* Workflow also known as Surveys
* Workspace also known as Sites and/or Pages

In a future release, it may become worthwhile to consider a stricter alignment between the business (UI) and technical (API) lexicons for the platform.
