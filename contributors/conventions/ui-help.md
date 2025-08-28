---
description: >-
  Conventions for a consistent, unified approach to layout and style throughout
  the user interface
---

# Style guide

## Overview

As a general rule, we follow the principles and practices in Google's Material Design style guide. Any time you are uncertain about how to proceed with a style decision, please refer to to it for guidance.

The official reference is here: \[Material Design style guide]\([https://m3.material.io/foundations/content-design/style-guide/ux-writing-best-practices](https://m3.material.io/foundations/content-design/style-guide/ux-writing-best-practices))

## Buttons

On web pages and web forms, buttons should be placed at the bottom of the form, aligned to the left margin.

In a list of buttons, those that perform affirmative actions should be left-most, and dismissive actions should be right-most, with utility and/or destructive actions in between.

Affirmative (Primary) → Utility → Destructive → Dismissive

> Buttons that perform destructive actions, such as Delete, may be placed separate from all other actions, if/as needed.

For example, if an edit form contains Save, Copy, Delete, and Cancel buttons, the correct sequence is:

**Save | Copy | Delete | Cancel**

Notice:

* **Save** (affirmative action) goes on the left
* **Cancel** (dismissive action) goes on the right
* **Copy** and **Delete** are placed between the affirmative and dismissive actions

## Tooltips

Tooltips provide brief, contextual help for UI elements. They should be concise, scannable, and easy to understand.

**Tone:**

* Use a clear, neutral, and instructional tone.
* Avoid jargon, unless it is widely understood by users.

**Length:**

* Aim for one sentence or less.
* Avoid multiple sentences or blocks of text.

**Punctuation:**

* **Do not use ending punctuation** (like periods) **for short phrases or fragments**.\
  &#xNAN;_&#x45;xample: "Displays on the learner's dashboard"_
* **Use a period** if the tooltip is a complete sentence.\
  &#xNAN;_&#x45;xample: "This text appears under the achievement title."_

**Grammar:**

* Use sentence case (capitalize the first word).
* Use active voice when possible.

**Icons:**

* Including an icon is optional.
* When you include an icon in a tooltip, follow a consistent semantic hierarchy:
  * <i class="fa-circle-question">:circle-question:</i> question mark for help/documentation
  * <i class="fa-circle-info">:circle-info:</i> info for basic information
  * <i class="fa-lightbulb-on">:lightbulb-on:</i> lightbulb for insights and quick tips

**Examples:**

* ❌ "this text will be shown under the achievement title."
* ✅ "This text appears under the achievement title."
* ✅ "Appears under the achievement title"
