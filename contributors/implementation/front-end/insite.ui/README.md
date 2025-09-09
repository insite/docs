---
description: >-
  Guidelines for implementing intuitive, consistent page layout for ASP.NET web
  forms throughout the platform
---

# ASP.NET web forms

## Page layouts

{% tabs %}
{% tab title="Admin" %}
The **Admin** area serves as the comprehensive management interface for system administrators and instructors who need full control over the learning environment.&#x20;

This area prioritizes functionality and efficiency, featuring dense information layouts, advanced configuration options, and administrative tools.&#x20;

The design emphasizes clear data hierarchies, robust navigation systems, and streamlined workflows that enable power users to quickly access deep system functionality.&#x20;

Interface elements should support complex tasks like user management, course authoring, analytics review, and system configuration while maintaining clarity even with high information density.
{% endtab %}

{% tab title="Portal" %}
The **Portal** area provides the core learning experience for authenticated learners engaging with course content and educational activities.&#x20;

This learner-focused environment emphasizes clean, distraction-free layouts that promote focus and engagement with educational materials.&#x20;

The design should prioritize content readability, intuitive progress tracking, and seamless navigation between learning modules.&#x20;

Interface elements should support various learning modalities while maintaining a welcoming, accessible experience that encourages continued engagement and learning progression.
{% endtab %}

{% tab title="Lobby" %}
The **Lobby** area serves as the first impression and entry point for unauthenticated visitors exploring the system.&#x20;

This public-facing space focuses on clear value proposition communication, easy navigation to key information, and frictionless pathways to registration and login.&#x20;

The design should balance marketing appeal with professional credibility, featuring prominent calls-to-action, accessible content previews, and trust-building elements.&#x20;

Interface layouts should be optimized for conversion while providing sufficient information for users to understand the platform's offerings and benefits.
{% endtab %}
{% endtabs %}

## Admin page layout guidelines

### Button placement

(Updated content is pending.)

### Form layout to create a new entity

(Updated content is pending.)

### Form layout to modify an existing entity

(Updated content is pending.)

### Form layout to delete an entity

(Updated content is pending.)

# Admin Portal

- [Admin Portal](#admin-portal)
  - [Simple Input Screens](#simple-input-screens)
  - [Outline Pages](#outline-pages)
  - [Cards with Search Results](#cards-with-search-results)
  - [Cards with Inputs](#cards-with-inputs)

On this page we focus on describing a set of guidelines on how to place buttons on different screens in different *boxes* from the admin site.

> **Note**  
> This is just a **Draft**. Let us all collaborate on achieving the best possible outcome and create the best standards together for button placement.

---

## Simple Input Screens

**Description:**

Every normal input screen like **Create**, **Edit**, **Change/Update (from Outline)** or **Delete** can be done using this approach:  
- Input fields are implemented in different cards with additional titles and description (if necessary).  
- Main action buttons for **Saving/Updating** or **Canceling** should be placed in the **bottom left**.

⚠️ If screens are longer and buttons don’t fit, try to make the buttons **sticky at the bottom of the screen**.  
[Reference: Position sticky button bar (bottom)](https://codepen.io/jaakritso/pen/zMXRaw)

**Examples:**

| | |
|---|---|
| ![Edit Seat — bottom-left Save/Cancel](https://github.com/user-attachments/assets/54583a6f-9a36-4a9e-9a3a-b1607c4f8c29) | ![Schedule a New Class — bottom-left Save/Cancel](https://github.com/user-attachments/assets/3947dbb0-9449-4abd-b84e-bda3e912ba41) |
| ![Describe Class — bottom-left Save/Cancel](https://github.com/user-attachments/assets/af93fba0-142d-484c-87bf-251f60eb87dd) | ![Delete Person — bottom-left Delete/Cancel](https://github.com/user-attachments/assets/c597d148-d60e-497e-b652-3eecffd289dc) |


## Outline Pages

**Description:**

An outline page displays combined information for a specific *Toolkit Object*.  
- The practice so far: keep all **outline object control buttons** on the **top left**.  
- The entirety of the information is locked within one card and separated with grouping dividers.

**Examples:**

**Examples:**

| | |
|---|---|
| ![Class Outline — top-left action buttons](https://github.com/user-attachments/assets/45c1c5bc-06f8-439f-bdf8-86358a5cbb47) | ![Outline — 2020 ISO Policies with top-left action buttons](https://github.com/user-attachments/assets/9deaf45e-5aa3-405e-9148-004ccb7d8b58) |


## Cards with Search Results

**Description:**

Some cards may gather and display data in a *Search Results* way. These cards usually:  
- Have a **Card Title** or **Filter** on the **top left**.  
- Include additional **Action Buttons** (e.g., Downloading, Adding to results) on the **top right**.  
- Item rows may include action links/buttons such as **View/Edit/Delete**, placed on the **right side** of the item row.

| | |
|---|---|
| <img width="1903" height="454" alt="image" src="https://github.com/user-attachments/assets/d95f1704-389d-4cb5-bf5e-43d732e5ccaa" /> | <img width="1891" height="643" alt="image" src="https://github.com/user-attachments/assets/01c38731-5b97-42fe-b96e-55072cac5157" /> |
| <img width="947" height="367" alt="image" src="https://github.com/user-attachments/assets/115bb8b8-6202-4b9d-803d-8b20e90a4828" /> | <img width="1891" height="425" alt="image" src="https://github.com/user-attachments/assets/a6bc7eb8-04df-4603-aae4-4fa333097174" /> |


## Cards with Inputs

**Description:**

Some cards, in addition to regular **Save/Update/Delete** actions, may have extra actions such as adding data to a *Toolkit Object*.  
Example: a card with an **Upload** button. (Placement for this is still under discussion.)

**Examples:**

<img width="1152" height="838" alt="image" src="https://github.com/user-attachments/assets/5d1bed96-76c0-4881-9ada-4ff70ec32883" />

# Form Layout

## Create

<img width="1862" height="930" alt="image" src="https://github.com/user-attachments/assets/92d4dd29-ec0e-4d7e-8e0d-b3e9a0a51781" />

## Modify

(Some documentation/description is needed here, of course.)

<img width="1538" height="923" alt="image" src="https://github.com/user-attachments/assets/a25f68f1-b9e0-4d96-8a6e-7526477e7a5a" />

## Nested Tabs

The topic was discussed here: [DEV-5903: Upgrade UI\Desktops\Admin\Courses2\Manage.aspx from B3 to B5
Closed](https://insite.atlassian.net/browse/DEV-5903)
  

If the form has nested tabs then:

1. The main/parent card should have shadowed borders
2. Internal panel(s) should be wrapped into cards with non-shadowed borders

<img width="1021" height="755" alt="image" src="https://github.com/user-attachments/assets/2045d766-4253-4c81-8fed-93737d8b1c69" />
