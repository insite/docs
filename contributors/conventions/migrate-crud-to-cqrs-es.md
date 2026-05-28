---
description: >-
  Concepts and a step-by-step pattern for migrating a CRUD entity to a CQRS+ES
  Timeline aggregate
---

# Migrate CRUD to CQRS+ES

## Queries

A query in a CQRS implementation can be thought of as a system message that is handled by a handler or subscriber. In CQRS, the architecture is often designed to separate the handling of commands (which modify state) from queries (which read state). Here's a more detailed explanation:

### Key Concepts in CQRS:

1. **Commands**: These are messages that represent an intent to change the state of the system. Commands are typically handled by command handlers, which process the command and apply the necessary changes to the write model.
2. **Queries**: These are messages that represent a request to read data from the system. Queries are handled by query handlers, which retrieve and return the data from the read model.
3. **Read Model**: The read model (or projection) is an optimized view of the data designed specifically for querying. It is kept in sync with the write model (often using events in an event-sourced system) to reflect the current state.

### Handling Queries:

* **Query Handlers**: In a CQRS implementation, a query handler is responsible for processing a query message. The handler retrieves the necessary data from the read model and returns the result to the caller.
* **Subscribers**: While the term "subscriber" is more commonly used in the context of event handling (where components subscribe to events and react to them), in some architectures, the concept of handling queries can also be seen as subscribing to query messages.

### Example:

Consider an e-commerce system using CQRS:

* **Command**: `PlaceOrderCommand` is sent to a command handler to place a new order. The handler processes this command and updates the write model.
* **Event**: `OrderPlacedEvent` is generated as a result of the command and is published to update projections or read models.
* **Query**: `GetOrderDetailsQuery` is sent to a query handler to retrieve the details of an order. The handler queries the read model (e.g., a denormalized table or a projection) and returns the order details.

## Projections

In a CQRS (Command Query Responsibility Segregation) implementation, the term "projection" is used to refer to a table or other data structure that stores information about the current state of the system. Projections are read models that are built from the event stream (event sourcing) or from other sources of data to provide an optimized, read-only view of the data, tailored to specific query needs and are continuously updated to reflect the latest state of the system.

Here's a more detailed explanation:

1. **Projections**: Projections are created by processing events and transforming them into a format that is optimized for querying. Each projection is typically designed to support specific queries or views in the system. The process of creating and updating projections is known as "event projection" or "view generation".
2. **Read Models**: In CQRS, the read model is a general term for any data structure that is used to serve read queries. Projections are a type of read model. The read model can be in the form of SQL tables, NoSQL documents, in-memory data structures, etc. Projections specifically refer to read models that are built from event streams.
3. **Current State**: When referring to the current state of the system, projections are often used because they provide an up-to-date view of the data based on the latest events. These projections are continuously updated as new events are processed.

### Example Scenario

Imagine an e-commerce system using CQRS and event sourcing. When an order is placed, several events are generated (e.g., `OrderPlaced`, `ItemAddedToOrder`, `OrderShipped`). Projections are created to provide different views of the data, such as:

* **Order Summary Projection**: A table that stores summarized information about each order, such as order ID, customer ID, total amount, and status.
* **Inventory Projection**: A table that stores the current inventory levels for each product.
* **Customer Orders Projection**: A table that stores a list of orders for each customer.

These projections are updated whenever relevant events are processed, ensuring they reflect the current state of the system.

### Note

A projection table in a CQRS implementation can be considered a type of "memoization". I have never seen the term "memoization" used in any article on the topic of CQRS, but it is a helpful term when we think about projection tables, and this Wikipedia article describes the concept better than many articles written about CQRS. [https://en.wikipedia.org/wiki/Memoization](https://en.wikipedia.org/wiki/Memoization)

## Timeline Implementation Pattern

In reality, the insert, update, and delete methods in an entity Store class implement commands to change the state of an entity.

The clue to a possible solution lies inside the previous statement...

Suppose the state of an entity is modified **only** by one of these methods, and not by any another method outside the Store.

In theory, this means we can rewrite the Insert, Update, and Delete methods in a Store class so they generate and send Timeline commands - instead of writing directly to the database.

In theory, this means we can substantially decrease the impact of migrating a CRUD entity to a Timeline aggregate, because the code that invokes these methods does not require any modification.

Here are the steps I followed in my initial experiment, using the Membership entity as the subject of the experiment:

1. Improve the MembershipStore class so the number of Insert, Update, and Delete operations is as small as possible. Ideally, there should be no more than one of each. (Sometimes it is useful to have Insert and Update combined into one Save method.)
2. Search existing stored procedures and code to ensure there are no write operations on the old CRUD table outside the MembershipStore class.
3. Create a new projection table contacts.QMembership.
4. Copy existing rows from the old CRUD table contacts.Membership to the new projection table.
5. Drop the old CRUD table.
6. Create a view on the projection table to mimic the existence of the old CRUD table. This ensures existing views, stored procedures, and classes that read from the original table continue to work with no modification.
7. Refactor the MembershipStore class into a command generator class. Instead of writing directly to the Membership collection through DbContext, the methods in this class generate and send Timeline commands.
   1. Implement a new aggregate class: MembershipAggregate
   2. Implement new command classes, as required by the new command generator.
      1. Add a Command Receiver.
   3. Implement new change classes for the new commands.
      1. Add a Change Projector.
   4. Implement a new MembershipStore class to write to the projection table.
   5. Implement a maintenance action to generate all the log.Change entries needed to reproduce the data in the new projection table. After this is done, we should be able to replay all changes for all membership aggregates to produce a table with data that exactly matches the original CRUD table.

Implementation time for this experiment: 3:24 PM to 5:19 PM = 115 minutes
