---
description: Lions, and tigers, and bears — oh my!
icon: timeline-arrow
---

# Queries and commands

## Introduction

Queries and commands are a fundamental concept to working with the API.

A **query** is an interrogative to request data. It is expressed as a verb or as a verb-noun phrase. For example:

* Count Answers
* Search Groups

A **command** is an imperative to execute a function. It is expressed as a verb or as a verb-noun phrase. For example:

* Add Question
* Delete
* Join Group
* Send Email

## Queries

The API provides support for several distinct types of query. Here is a summary of the purpose and intended developer use case for each type:

<table><thead><tr><th width="135">Query Type</th><th width="398">Query Purpose</th><th>API Endpoint Template</th></tr></thead><tbody><tr><td><i class="fa-check">:check:</i> <strong>Assert</strong></td><td>Check for the existence of one specific item in a collection using a key value (returns true or false)</td><td><p><strong>HEAD</strong></p><p>api/collection/{id}</p></td></tr><tr><td><i class="fa-album-collection">:album-collection:</i> <strong>Collect</strong></td><td>Collect the list of items that match specific criteria in a collection (returns a paged list of heavyweight models, suitable for a detailed view of each item in a user interface; also suitable for integration with other systems)</td><td><strong>POST</strong> (or GET)<br>api/collection/collect</td></tr><tr><td><i class="fa-tally">:tally:</i> <strong>Count</strong></td><td>Count the list of items that match specific criteria in a collection (returns an integer)</td><td><strong>POST</strong> (or GET)<br>api/collection/count</td></tr><tr><td><i class="fa-download">:download:</i> <strong>Download</strong></td><td>Download the list of items that match specific criteria in a collection (returns an unpaged list of heavyweight models, suitable for a detailed view of each item in a user interface; also suitable for integration with other systems)</td><td><strong>POST</strong> (or GET)<br>api/collection/download</td></tr><tr><td><i class="fa-file-export">:file-export:</i> <strong>Export</strong></td><td>Export the list of items that match specific criteria in a collection (returns a private and secure link to download the export file; link expires after 1 hour)</td><td><strong>POST</strong><br>api/collection/export</td></tr><tr><td><i class="fa-album">:album:</i> <strong>Retrieve</strong></td><td>Retrieve one specific item in a collection using a key value (returns a heavyweight model suitable for a detailed view of the item in a user interface)</td><td><p><strong>GET</strong></p><p>api/collection/{id}</p></td></tr><tr><td><i class="fa-magnifying-glass">:magnifying-glass:</i> <strong>Search</strong></td><td>Search for the list of items that match specific criteria in a collection (returns a paged list of lightweight models intended for search results, combo boxes, lookups, etc.)</td><td><strong>POST</strong> (or GET)<br>api/collection/search</td></tr></tbody></table>
