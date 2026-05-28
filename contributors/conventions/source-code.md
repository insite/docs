---
description: >-
  Naming and coding conventions for InSite source code, including telemetry,
  options and settings, lines of code, regions, TypeScript, and third-party code
---

# Source code

## Introduction

Some of the naming conventions documented here are new, and some are revised from older existing conventions.

Existing code and existing database objects are **not** expected to follow these conventions perfectly. New code and new database objects should follow these conventions whenever possible.

Historically, our naming conventions have been driven by the [Clean Architecture](https://matthewrenze.com/presentations/clean-architecture/) pattern, especially the organization of our source code into packages. As we transition from Microsoft .NET Framework to Microsoft .NET Standard and .NET Core, we are taking the opportunity to begin to follow a [Vertical-Slice Architecture](https://www.youtube.com/watch?v=_1rjo2l17kI) (VSA) pattern instead.

> In reality, much of the Shift iQ code base is already organized like a [Modular Monolith](https://www.milanjovanovic.tech/blog/what-is-a-modular-monolith), and VSA is a better fit for this purpose.

Recent changes and improvements to naming conventions are also motivated by the need to design and implement code that is easier to read, easier to test, and better aligned with CQRS+ES patterns and principles.

VSA improves maintainability and flexibility because changes and improvements to an application feature are localized within its vertical slice. In other words, VSA does a better job of keeping tightly coupled classes in close proximity to one another, rather than spreading them across many different layers, in many different packages, where the stratification of layers and packages is determined by the technical responsibility rather than product feature or use case.

Refer to this article for a good explanation of VSA and its benefits:

[https://www.ghyston.com/insights/architecting-for-maintainability-through-vertical-slices](https://www.ghyston.com/insights/architecting-for-maintainability-through-vertical-slices)

### Legacy Code Standards (PDF)

Here is a copy of the InSite coding standard initially drafted and published in 2010. It was updated in January 2025, but time did not permit a careful review. Therefore, a careful review and revision of this PDF is still pending; when this is done, the standards should be extracted into Confluence pages here.

## Telemetry

### Serilog

The physical path to the Serilog log file follows this convention:

`C:\Base\Data\{Partition}\{Environment}\Logs\{Package}.Serilog-.txt`

Note the trailing hyphen in the file name. This improves the readability of log file names when rolling intervals are enabled.

### Sentry

The physical path to the Sentry log file follows this convention:

`C:\Base\Data\{Partition}\{Environment}\Logs\{Package}.Sentry.txt`

When an error is reported to Sentry, it is understood that this identifies a problem that requires a solution. (For example, the solution may be a security improvement, a bug fix, or a performance optimization.) An error in Sentry is Resolved only after the problem is solved.

If the cause of an error in Sentry is understood, but there is no immediate need for a solution (perhaps because it occurs infrequently, and/or more occurrences of the error are needed to obtain more information for an optimum solution), then - at a minimum - our code should be improved as follows:

1. Catch the exception that causes the error.
2. Instead of sending the message to Sentry as an Error, send it as a Warning message (or as an Information message).

In effect, this serves as documentation for the knowledge that the problem is identified, its impact is understood to be low, and messages related to the problem will be monitored at a lower priority. If the problem begins to occur more frequently, or its impact becomes more severe, then this decision can be revisited, and then perhaps enough information for a solution is available.

### Options and Settings

Use the suffix `Options` or `Settings` to name a class that relates to configuration. For example:

* `AppSettings`
* `DatabaseOptions`

The choice between the suffixes `Options` and `Settings` depends on context and usage.

* Use `Options` if the class is used with DI and `IOptions<T>`, or if it uses the Options Pattern in .NET Core.
* Otherwise use `Settings`.

## Source Code

### Recommendations

* A file should **contain one class**. Multiple classes within the same file is discouraged.
* A **class name should be a noun**, according to its domain and architectural meaning.
* A **function name should be a verb** or verb-phrase, according to its context and what it does.
* A function should be **as small as possible**.
* A function should have an **explicit intent**, both in its name and code.
* A function should **do one thing only** and do it well. One thing means one level of abstraction (manipulating strings is one level, manipulating business rules is another level), or when nothing else can be extracted and meaningfully reused in another function or method.
* Methods in a class should be **organized per level of abstraction**, where the methods used by a method sit directly below it.
* Choose **descriptive names**, for **small functions**, that **do one thing**.
* A function should have **at most 3 arguments**. If we need more than 3 and if they are conceptually related, then we should group them in an object.
* Avoid output arguments (i.e., arguments to output data from a function).
* Avoid Boolean arguments. Use two functions instead.
* Comply to Command Query Segregation principles. Either:
  * Do something (**change state**), **or**
  * Get something (**return information** about an object),
  * and **not both**!
* Avoid returning an error code. Instead, **throw an exception**.
* Ideally, the block inside a conditional or inside a loop should be **one line long**: a function call that is correctly named and therefore documents itself.
* Avoid platform-dependent code. For example, use `Path.DirectorySeparatorChar` rather than assuming a forward-slash (Linux and MacOS) or a backward-slash (Windows) in code that interacts with file system paths.

A method invocation with a long parameter list that exceeds the length of one line of text should separate the parameter list: one parameter per line, with consistent indentation.

* Each parameter is clearly visible and easy to identify
* It is easy to add, remove, or reorder parameters
* It is simple to spot differences in code reviews
* Consistent vertical alignment improves scanning

For example:

```csharp
SomeMethod(
    parameterOne,
    parameterTwo,
    parameterThree,
    parameterFour
);
```

### Lines of Code

1. Ideally, a single line of code should not exceed 120 characters. In VS Code you can add this to display a guideline on the right page margin: `"editor.rulers": [120]`
2. A function should not exceed the number of lines of text that fit on the screen. In other words, no vertical scrolling should be necessary to read a function from start to finish.

### Regions

1. If the number of lines of code in a class is less than 200 then the class should **not** contain any code regions.
2. If the number of lines of code in a class is much larger than 200 then organize the code into logical regions. When possible, these logical groups should be based upon categorical organization rather than functional organization (i.e., business subdomain rather than method type). Either is acceptable, but categorical organization is preferred, because it helps guide refactoring when a large class needs to be broken down into multiple smaller classes.

   For example, functional organization looks like this:

   * Initialization and Loading
   * UI Event Handling
   * Database Operations

   ... whereas categorical organization looks like this:

   * Candidates
   * Forms
   * Registrations
3. The code behind a user interface control (ASCX) should be broken down into these groups:

   * region Control State = Model(s)
   * region Security
   * region Initialization and Loading
   * region Binding Models to Controls (control setters)
   * region Binding Controls to Models (control getters)
   * region UI Navigation
   * region UI Event Handling
   * region Validation and Integrity
   * region Database Operations
   * region Sending Commands
   * region (Other)
4. It should be possible (at least in theory) to refactor some of these regions into separate classes.

   For example, consider the user control `ExamMarkGrid.ascx`. The code-behind class is a **Controller** because it contains only Web.UI code (`System.Web.UI, InSite.Common.Web.UI, Telerik.Web.UI`). All its methods are small and simple. The methods themselves are not sorted alphabetically, but rather in order of their corresponding controls on the page. Also notice this class contains less than 200 LOC.

   The file `ExamMarkGridModel.cs` contains a separate class with NO dependencies on any Web.UI library. It encapsulates the logic that is needed by the ExamMarkGrid control. Because this class has no `Web.UI` dependencies, it can (in theory) be moved down the stack into the InSite.Application layer, where its methods might become useful to other parts of the system. Also notice this class contains less than 200 LOC.

### TypeScript

1. Do not use **any** type.\
   The compiler will complain if you try, this is intentional.
2. Terminate the operator with semicolon\
   Typescript allows omitting a semicolon in most cases, however, I think we should always use a semicolon to avoid confusion.\
   `doSomething();`
3. Always wrap the code block in braces, even if it is one-line code.\
   `if (isLoading) {`\
   `return;`\
   `}`
4. Use a Pascal Case for TSX file names:\
   `AdminGradebookSearch.tsx`
5. Use Camel Case for TS, CSS and JSON file names:\
   `gradebookSearch.ts`
6. Use a Pascal Case for class names, interface names and components:\
   `interface Props {`\
   `...`\
   `}`\
   `export default function AdminGradebookSearchCriteria(...`\
   `...`
7. Use a Camel Case for variable names, parameters, and function names:\
   `function doSomething(param1: string) {`\
   `const localVariable1 = "hello world";`\
   `}`
8. Use underscore when the global variable is defined:\
   `let _queryResult: QueryResult<GradebookRow, GradebookFilter> | null = null;`
9. Give preference to function declarations over function expressions where it is possible and reasonable:\
   `function doSomething() {`\
   `...`\
   `}`\
   **vs**\
   `const doSomething = () => {`\
   `...`\
   `}`
10. Use double quotes to specify string literals:\
    `const stringValue1 = "value in double quotes";`\
    It can be convenient if we want to copy JavaScript objects to JSON because JSON requires text to be enclosed in double quotes.

### Third-Party Source Code

Never integrate source code that is private property owned by another company, unless:

1. We have a license that permits us to do so, and
2. An InSite manager has reviewed and approved the decision.

This is necessary to ensure InSite is always in compliance with copyright laws and intellectual property laws.

Never integrate source code that is subject to a license that requires changes to the license for InSite source code. This is necessary to ensure InSite is always in compliance with copyright laws and intellectual property laws.

Do not integrate a new third-party component without first reviewing the decision with the team. This is necessary to ensure we do not introduce unnecessary risk to the overall quality of the system (e.g., its security, stability, maintainability, etc.).
