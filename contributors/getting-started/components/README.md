---
hidden: true
---

# Components

### Purpose

The Components documentation is intended for internal use. Its purpose is to describe Shift iQ features in such a way that administrators and developers can understand the steps to perform more advanced tasks when learning the system, troubleshooting issues, and/or assisting customers with their accounts.

> Note: The term **Toolkit** will be deprecated because it sounds a little too technical. In business contexts we will use these terms in its place: **App**, **Plugin**, and **Utility**.
>
> The term **App** is considered synonymous with **Feature Set**, and the term Feature Set may be abbreviated **Features** or **Feature** in documentation and code.
>
> From a technical perspective, App (or Feature), Plugin, and Utility are component types, where a “component” is understood to be a logical, high-level, module (i.e., a vertical slice of features). The Shift iQ platform contains several components, and each component represents a bounded context of the overall application domain. For example, the Contact component contains functionality related to contact information management.
>
> Refer to this article for a technical discussion of the modular (vertical) software architecture pattern: [Modular Monolithic Architecture](https://medium.com/design-microservices-architecture-with-patterns/microservices-killer-modular-monolithic-architecture-ac83814f6862)

### Convention

The steps to perform an application task should be described in such a way that anyone can follow the steps as a test case to confirm the behaviour of the system meets expectations.

A brief, point-form list of steps is the ideal format, written as a simple, user-friendly “how-to” guide. Screen captures and/or videos are very helpful, whenever possible.

Try to apply a consistent approach to all public customer-facing help topics.

> Note: Many articles on the topic of software help documentation reference Stripe as an excellent example. While authoring and reviewing help content for Shift iQ, if you want to see an example of best practices applied to a real-world documentation site, then visit [Stripe Docs](https://docs.stripe.com/) and [Stripe API Reference](https://docs.stripe.com/api).

#### Content Structure

Help topics are structured like this:

* Component
  * Subcomponent (or Part)
    * Task (a brief sentence phrased as an imperative)

For example:

* Assessment
  * Banks
    * Create a new assessment bank

> Note: We might want to group tasks into scenarios; this will become clear as documentation evolves.

### Help Topic Checklist

Each page in the internal documentation here is intended for platform administrators and developers.

Each page in the external Help Portal ([https://www.shiftiq.com/help](https://www.shiftiq.com/help)) is intended for customers.

In both places we should follow the same general principles. Here is a checklist to guide the work when we write a new help topic (or update an existing one):

* [ ] The content is a list of numbered steps. If the content includes supportive text that is not explicitly related to specific steps in the task, then this is clearly distinguished in its style/formatting.
* [ ] The content is user-friendly; it is written from a business perspective for a non-technical person.
* [ ] The content can include screen captures and/or videos. This is optional, and can be very useful when it eliminates a lot of text that would otherwise need to be written.
* [ ] The content includes links that cross-reference to related documentation, where applicable.
* [ ] The content does not include any personal information (e.g., email addresses, phone numbers).
* [ ] If a developer changes a part of the system related to the help topic, then anyone (business or technical) can follow the steps to confirm the system’s behaviour is not broken by the change. In other words, the content for the help topic can serve as a test case and as a feature description .
* [ ] The URL for a help topic is readable and SEO-friendly. (This applies to external documentation only.)

### Components (Toolkits) = Apps (or Features), Plugins, and Utilities

Each component is a subsystem within the platform. (Technical software architecture documentation often uses the term “module” for this concept. Shift iQ is a modular platform.) Each component contains one or more subcomponents (or parts), and each subcomponent relates to one or more domain entities.

> For example, the Contact component contains subcomponents such as Groups, People, and Memberships. Within the Groups subcomponent are specific domain entities such as Group, GroupAddress, and GroupSetting.
>
> As another example, the Security component contains a Users subcomponent, which contains entities for individual user accounts, connections between users, login failures, and authenticated user sessions.

Shift iQ contains:

* **17 Feature Components**
* **2 Plugin Components**
* **4 Utility Components**

<figure><img src="../../components/.gitbook/assets/components.png" alt=""><figcaption></figcaption></figure>

#### Features (Apps)

**Features** deliver end-user features to learners, instructors, and administrators.

1. Achievement
2. Assessment
3. Billing
4. Calendar
5. Contact
6. Content
7. Course
8. Gradebook
9. Job
10. Location
11. Logbook
12. Message
13. Report
14. Site
15. Standard
16. Survey
17. Workflow

#### Plugins

**Plugins** implement integration with external third-party platforms and customizations for specific partitions (or tenants) and organizations.

1. Integration
2. Variant

#### Utilities

**Utilities** are intended for internal use by platform administrators and developers for system setup, instrumentation, and telemetry. Some limited access may be granted to some customers.

1. Metadata (platform and database structure)
2. Security (accounts and permissions)
3. Setup
4. Timeline (CQRS+ES backbone and service bus)

#### Component Aliases

For technical reasons, the following names have aliases:

* Calendar also known as Events and/or Schedule
* Cases also known as Issues
* Content also known as Assets
* Learning also known as Courses
* Timeline also known as Logs and/or Bus
  * Note: Commands, queries, and changes (aka events) are parts of the service bus implementation

In a future release, it may become worthwhile to consider a stricter alignment between the business (UI) and technical (API) lexicons for the platform.
