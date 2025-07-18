---
description: >-
  Standardized patterns developers can follow to create a consistent and
  user-friendly experience
---

# User interface

## Introduction

This section provides a curated set of user interface patterns to help developers build consistent, intuitive, and accessible user experiences.&#x20;

Each pattern addresses a common scenario — such as navigation, selection, input, and feedback — with instructions and implementation examples.&#x20;

## Combo boxes and search modals

When you implement a user interface feature that allows a user to find an item in a collection, if you need to select data from the API, then use the Search endpoint for the collection.

A search query is specifically designed for this purpose.&#x20;

* It selects the minimum number of columns required from the database to find matching criteria.
* It returns the minimum number of properties required for typical search results.&#x20;
* Therefore, it is optimized for server-side performance and download speed.

For example, if you are building a combo box in React to find and select a gradebook, then use the **Search** endpoint in the API:

<mark style="color:blue;">**progress/gradebooks/search**</mark>

{% hint style="info" %}
For details, refer to the [OpenAPI Specification](https://app.gitbook.com/s/yCodYcY9Svgs5pGsCpXh/api-v2/endpoints/api-reference "mention")
{% endhint %}

### Sending queries to the API

The API provides support for several distinct types of database query. Here is a summary of the purpose (and intended developer use case) for each type of query:

<table><thead><tr><th width="135">Query Type</th><th width="398">Query Purpose</th><th>API Endpoint Template</th></tr></thead><tbody><tr><td><i class="fa-check">:check:</i> <strong>Assert</strong></td><td>Check for the existence of one specific item in a collection using a key value (returns true or false)</td><td><p><strong>HEAD</strong></p><p>api/collection/{id}</p></td></tr><tr><td><i class="fa-album-collection">:album-collection:</i> <strong>Collect</strong></td><td>Collect the list of items that match specific criteria in a collection (returns a paged list of heavyweight models, suitable for a detailed view of each item in a user interface; also suitable for integration with other systems)</td><td><strong>GET or POST</strong><br>api/collection</td></tr><tr><td><i class="fa-tally">:tally:</i> <strong>Count</strong></td><td>Count the list of items that match specific criteria in a collection (returns an integer)</td><td><strong>GET or POST</strong><br>api/collection/count</td></tr><tr><td><i class="fa-download">:download:</i> <strong>Download</strong></td><td>Download the list of items that match specific criteria in a collection (returns an unpaged list of heavyweight models, suitable for a detailed view of each item in a user interface; also suitable for integration with other systems)</td><td><strong>GET or POST</strong><br>api/collection/download</td></tr><tr><td><i class="fa-file-export">:file-export:</i> <strong>Export</strong></td><td>Export the list of items that match specific criteria in a collection (returns a private and secure link to download the export file; link expires after 1 hour)</td><td><strong>POST</strong><br>api/collection/export</td></tr><tr><td><i class="fa-album">:album:</i> <strong>Retrieve</strong></td><td>Retrieve one specific item in a collection using a key value (returns a heavyweight model suitable for a detailed view of the item in a user interface)</td><td><p><strong>GET</strong></p><p>api/collection/{id}</p></td></tr><tr><td><i class="fa-magnifying-glass">:magnifying-glass:</i> <strong>Search</strong></td><td>Search for the list of items that match specific criteria in a collection (returns a paged list of lightweight models intended for search results, combo boxes, lookups, etc.)</td><td><strong>GET or POST</strong><br>api/collection/search</td></tr></tbody></table>

