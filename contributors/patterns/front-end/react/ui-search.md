---
description: >-
  Standardized patterns developers can follow to create a consistent and
  user-friendly experience
---

# UI Search

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
For details, refer to the [Developer Documentation](broken-reference).
{% endhint %}

