---
description: >-
  Use the API, SDK, and developer tools to build custom integrations, streamline
  workflows, and create tailored solutions for your learning, assessment, and
  competency management solutions
icon: square-terminal
---

# Developer documentation

Welcome to the developer documentation for Shift iQ. These docs are intended for external developers consuming our public APIs directly, technical partners embedding or extending our platform, and integration teams implementing custom or third-party connectors. Whether you're building a new integration, connecting between platforms, or creating shared tooling, you'll find technical guidance and reference information here to help you get started.

## Overview

The public API enables external systems to interact programmatically with key features of our platform, including data access, automation, and synchronization. It follows REST principles, is secured via token-based authentication, and supports both synchronous and event-driven interactions.

### What you’ll find in this section

* A structured overview of how the API works
* Authentication and permission models
* Endpoint specifications
* Data format conventions
* Usage policies and operational limits
* Technical resources beyond the API reference
* Additional information about integrations with specific products and platforms

***

## API Reference (v1 and v2)

Our API is organized around RESTful principles, with resource-oriented URLs and predictable HTTP response codes. It supports standard operations—such as create, read, update, and delete—on core objects within the system.

Start by reviewing:

* Base URL and versioning strategy
* Key resources and endpoints
* Getting your first successful request

👉 _New to the API? Begin with the Quickstart Guide to authenticate and make your first call._

### Authentication and authorization

Access to the API requires secure authentication and permission management. We support:

* **Bearer tokens** for trusted service-to-service interactions
* **OAuth 2.0** flows for delegated access and third-party apps
* **Scoped access tokens** to enforce least-privilege permissions

This section explains how to:

* Register clients and manage credentials
* Request and refresh access tokens
* Use scopes to restrict permissions

### Endpoints

A complete reference of all public API endpoints, including:

* Resource paths and supported HTTP methods
* Required and optional parameters
* Sample requests and responses
* Error conditions and response codes

Browse by resource type to find exactly what you need.

### Request and response formats

To ensure consistency and predictability, the API adheres to established conventions for:

* **HTTP verbs**: `GET`, `POST`, `PUT`, `DELETE`
* **Pagination**: `limit`, `offset`, and cursor-based flows
* **Payloads**: structured JSON request/response bodies
* **Status codes**: success, client error, and server error semantics
* **Headers**: `Content-Type`, `Authorization`, and pagination links

This section defines how to format requests and interpret responses reliably.

### Rate limits and throttling

To protect system stability and ensure fair usage, the API enforces rate limits per client. This includes:

* Default rate limits and per-endpoint constraints
* Retry-after guidance and exponential backoff behavior
* Headers (`X-RateLimit-*`) for tracking current usage
* Best practices for rate-aware integrations

***

## Resources

Broader developer resources to support developers and integrators beyond the API reference. For example:

* SDKs and client libraries in multiple languages
* Code samples and community-contributed tools
* Environment configuration and testing guides
* Webhook configuration and event schemas

👉 _Use these resources to speed up development and simplify integration._

***

## Integrations

We offer and maintain a growing set of pre-built integrations with popular third-party platforms. These ready-to-deploy connectors reduce implementation time and ensure best-practice alignment.

* Native integrations with platforms like Moodle, Canvas, SCORM Cloud, Prometric, and others
* Webhook-based automation flows
* Integration templates and deployment instructions
* Configuration options and supported use cases

👉 _Explore these options to avoid building from scratch and go live faster._

***

{% hint style="info" %}
💡 **Need help?** If you're running into issues, contact our service and support team.
{% endhint %}
