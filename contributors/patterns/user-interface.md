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
For details, refer to the [API Reference](https://app.gitbook.com/s/yCodYcY9Svgs5pGsCpXh/api-v2/api-reference "mention")
{% endhint %}

### Using the API to query data

Here is a summary of the intended developer use case for similar endpoints in the API:

<table><thead><tr><th width="135">Query Type</th><th width="398">Query Purpose</th><th>Endpoint Pattern</th></tr></thead><tbody><tr><td><i class="fa-check">:check:</i> <strong>Assert</strong></td><td>Checks for the existence of one specific item in a collection using its primary key (returns true or false)</td><td><p><strong>HEAD</strong></p><p>api/collection/{id}</p></td></tr><tr><td><i class="fa-album-collection">:album-collection:</i> <strong>Collect</strong></td><td>Finds matching items in a collection (returns a list of heavyweight models, suitable for a detailed view of each item in a user interface; also suitable for integration with other systems)</td><td><strong>GET or POST</strong><br>api/collection</td></tr><tr><td><i class="fa-tally">:tally:</i> <strong>Count</strong></td><td>Counts the matching items in a collection (returns an integer)</td><td><strong>GET or POST</strong><br>api/collection/count</td></tr><tr><td><i class="fa-album">:album:</i> <strong>Retrieve</strong></td><td>Finds one specific item in a collection using its primary key (returns a heavyweight model suitable for a detailed view of the item in a user interface)</td><td><p><strong>GET</strong></p><p>api/collection/{id}</p></td></tr><tr><td><i class="fa-magnifying-glass">:magnifying-glass:</i> <strong>Search</strong></td><td>Find matching items in a collection (return a list of lightweight models intended for search results, combo boxes, lookups, etc.)</td><td><strong>GET or POST</strong><br>api/collection/search</td></tr></tbody></table>

