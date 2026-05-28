---
description: >-
  Key terms in our lexicon for designing, building, and managing the software,
  including libraries, namespaces, entities, and URLs
---

# Terminology

Here are some of the key terms in our lexicon for designing, building, and managing the software.

| **Term** | **Meaning** |
| --- | --- |
| **Partition** | A partition is a separate instance of the system, dedicated to a specific customer (or subset of customers. Aliases for this term include "Enterprise" (sometimes used by InSite in the past) and "Tenant" (used by Octopus). |
| **Environment** | An environment is a configured instance of the system designed for a specific purpose. Environments are isolated from one another to ensure stability, consistency, and the ability to perform tasks without interference across different phases of a release cycle. There are four (4) environments: <ol><li><strong>Local</strong>: This is an offline environment used by programmers to develop, test, and debug system changes.</li><li><strong>Development</strong>: This is an online testing environment used by QA teams to validate the system's functionality, performance, and reliability for a new release.</li><li><strong>Sandbox</strong>: This is a staging environment that mimics the production environment to validate deployment processes, simulate real-world scenarios, and test patches for a hotfix release.</li><li><strong>Production</strong>: This is the live system accessible to customers and end-users.</li></ol> |
| **Library** | A library is a source code project that defines and/or implements classes for reuse in other projects. There are four (4) types of library: <ol><li><strong>Base</strong> or <strong>Common</strong>: Implements basic reusable classes with no third-party dependencies.</li><li><strong>Toolbox</strong>: Implements advanced reusable classes with third-party dependencies.</li><li><strong>Contract</strong>: Defines and implements settings, rules, and constraints.</li><li><strong>Service</strong>: Implements logic specific to an application (e.g., persistence, domain).</li></ol> Historically, InSite libraries used naming conventions from Clean Architecture terminology. These older conventions are in the process of being replaced with conventions that are more suitable for a vertical slice architecture (i.e., the modular monolith pattern), which is a better representation of how we organize source code in our platform. |
| **Base** or **Common** | A common library implements general-purpose functionality where third-party dependencies are not permitted. A base (or common) library: <ul><li>Targets <strong>.NET Standard 2.0</strong> for maximum reusability.</li><li>Contains <strong>zero dependencies</strong> on third-party libraries.</li></ul> |
| **Toolbox** | A toolbox library implements general-purpose functionality where third-party dependencies are permitted and potentially necessary. A toolbox library: <ul><li>Targets .NET Standard 2.0 if possible, otherwise targets <strong>.NET Core 9.0</strong>. Targets .NET Framework 4.8 only if it is not possible to target .NET Standard or .NET Core.</li><li>May contain dependencies on third-party libraries.</li></ul> |
| **Contract** | A contract library defines the rules and constraints to help enforce consistency, validate inputs, and/or specify obligations and guarantees between different parts of the code. A contract library: <ul><li>Defines interfaces.</li><li>Implements classes for configuration settings.</li><li>Implements classes for request/response data types (i.e., input and output classes).</li><li>Targets <strong>.NET Standard 2.0</strong> for maximum reusability.</li><li>Contains <strong>zero dependencies</strong> on third-party libraries.</li></ul> Ideally, classes are plain old class objects (POCO) and data transfer objects (DTO). Constant literals and enumeration types are also appropriate in a contract library. |
| **Service** | A service library implements the features for a specific application. A service library: <ul><li>Targets <strong>.NET Core 9.0</strong> for maximum power and flexibility. Target .NET Standard only if it is useful and easy. If it is not possible to target .NET Core or .NET Standard for any reason, then target .NET Framework 4.8.</li><li>May contain dependencies on third-party libraries.</li></ul> |

Here is a summary of the main considerations for each type of **Library**:

| | **Base (Common)** | **Toolbox** | **Contract** | **Service** |
| --- | --- | --- | --- | --- |
| **Target Build** (in order of preference) | .NET Standard 2.0 | .NET Standard 2.0<br>.NET Core 9.0<br>.NET Framework 4.8 | .NET Standard 2.0 | .NET Core 9.0<br>.NET Framework 4.8 |
| **Dependencies** on Third-Party Libraries | Not Permitted | Permitted | Not Permitted | Permitted |
| **Directories** (typical focus for root-level folders) | Technical Aspects<br>e.g., Cache; IO; Mail; Sql; Text; Threading; Time; Web | Technical Aspects | Business Modules<br>e.g., Assessment; Billing; Contact; Learning; Survey; Workflow | Business Modules |

> Please note the InSite codebase is highly dependent on [Newtonsoft.Json](https://www.newtonsoft.com/json) for serialization, therefore this is the only exception to rules that disallow third-party library references.

## Namespaces

Here is a guideline for namespace structure:

| | |
| --- | --- |
| Functional Scope | Application; Infrastructure; Kernel |
| Layer (or Purpose) | Common (or Base or Fabric); Contract; Toolbox; Service (Data (or Persistence or Storage); State (or Domain); Process (or Logic or Business or Application)); Api; Sdk; Test (or Lab); Terminal (or Maintenance); UI (or Presentation) |
| Component Type | Composition; Feature; Internal; Plugin; Utility |
| Component | **Composition**: (none listed)<br>**Feature**: Achievement, Assessment; Billing; Calendar; Contact; Content; Course; Gradebook; Job; Location; Logbook; Message; Report; Site (Shell); Standard; Survey; Workflow<br>**Internal**: (none listed)<br>**Plugin**: Integration; Variant<br>**Utility**: Metadata; Security; Setup; Timeline |
| Subcomponent | There is no fixed list here. Subcomponents vary per component. For example, the Message component might have subcomponents that include Templates, Mailouts, and Recipients. |

In general (and if possible), a C# namespace should follow this convention:

`[developer].[scope].<product>.[component-type].[component].[subcomponent]`

> `[layer]` and/or `[purpose]` should be included in the namespace. These are not assigned a fixed location within the namespace segmentation because the product architecture determines the structure of project assemblies in the solution, and this structure decides the best placement of purpose and layer names within the space.

For example, in a traditional clean architecture pattern with horizontal layers based on technical function, namespaces might look like this:

* Product.Persistence.Contact.Groups
* Product.Persistence.Contact.People
* Product.Application.Contact.Groups
* Product.Application.Contact.People
* Product.UI

In a modular monolith architecture with vertical slices based on business category, namespaces might look like this:

* Product.Contact.Service.Groups.Data
* Product.Contact.Service.Groups.Process
* Product.Contact.Service.People.Data
* Product.Contact.Service.People.Process
* Product.Contact.UI

The name of a C# assembly should follow the same convention. Ideally, an assembly name should have a layer or purpose as its suffix.

***

Here is the convention decided in DEV-10637:

**Assembly.ComponentType.Component.Subcomponent.Layer**

… where:

* **ComponentType** = Internal | Composition | Feature | Plugin | Utility
* **Component** = (varies by component type; if ComponentType = Feature then Component = toolkit)
* **Subcomponent** (varies by component; if component = Feature then subcomponent = aggregate)
* **Layer** = (optional; only needed when the layer is not already specified in the Assembly name; if needed then = Common | Contract | Toolbox | Service | Api | Sdk | Test | Lab | Terminal | UI)

***

For the sake of example, so we can see how these conventions look and feel, I have applied them to the InSite.Test project as an experiment.

[https://github.com/InSite/code/pull/5793](https://github.com/InSite/code/pull/5793)

In this example:

* Assembly = InSite.Test
* Component Type = Internal | Composition | Feature | Utility
* Subcomponent = (varies by component type)
* Layer = (omitted because "Test" is in the Assembly name, and this is the purpose of all classes in all namespaces contained by this assembly)

> Notice I have added a Readme file to each subfolder in the project to help us remember the purpose of each main subfolder. If this proves to be a good idea, then we can continue with this approach and add Readme files to each Subcomponent sub-subfolder also.

## Entities

The mapping between SQL Server database table names and C# entity class names is formally defined in the database table `metadata.TEntity`. You can use this search page to explore the data in this table:

[https://dev-demo.shiftiq.com/ui/admin/database/entities/search](https://dev-demo.shiftiq.com/ui/admin/database/entities/search)

## URLs

Here are the correct terms for each type of URL:

1. [**https://example.com/hello**](https://example.com/hello) = **Absolute URL** (or fully qualified URL). Contains the complete address with scheme, domain, and path.
2. **/hello** = **Root-relative URL** (or absolute path). Starts with a forward slash and is relative to the domain root.
3. **hello** = **Relative URL** (or relative path). Relative to the current directory/location.

For example, if you are currently at `https://example.com/docs/guide.html` then:

* The absolute URL works from anywhere
* The root-relative URL `/hello` would resolve to `https://example.com/hello`
* The relative URL `hello` would resolve to `https://example.com/docs/hello`
