---
description: Guidelines for the layout and structure of a scalable, readable codebase
---

# Folder structure and project names

## Root folder structure

A git repository should contain some (or all) of the following root-level folders:

<table><thead><tr><th width="120" valign="top">Folder</th><th valign="top">Purpose</th></tr></thead><tbody><tr><td valign="top"><strong>build</strong></td><td valign="top"><p><strong>Build configuration and tooling</strong></p><p>Developer-written scripts, configuration files, environment setup files, and utilities to automate and orchestrate build-related tasks such as linting,  compiling, bundling, transforming, and deploying source code.</p></td></tr><tr><td valign="top"><strong>config</strong></td><td valign="top"><p><strong>Project configuration files</strong></p><p>Configuration files, environment settings, dependency injection configuration, etc.</p></td></tr><tr><td valign="top"><strong>data</strong></td><td valign="top"><p><strong>Project data and schema</strong></p><p>Database schema definitions (DDL), migrations, seed and reference data, example datasets, fixtures, and any persistent project data files.</p></td></tr><tr><td valign="top"><strong>dist</strong></td><td valign="top"><p><strong>Build output artifacts</strong></p><p>Compiled, bundled, and/or generated files produced by the build process. This folder represents the deployable or distributable form of the project. (It should be excluded from version control.)</p></td></tr><tr><td valign="top"><strong>docs</strong></td><td valign="top"><p><strong>Project documentation</strong></p><p>Technical documentation related to the project. Includes markdown files, HTML files, API references, user guides, architecture overviews, or other documents that provide instructions, tutorials, and reference materials for developers.</p></td></tr><tr><td valign="top"><strong>public</strong></td><td valign="top"><p><strong>Static web-visible resources</strong></p><p>Static files used in the project and intended to be publicly accessible. These might include images, icons, fonts, HTML/CSS/JS files, and other media assets.</p></td></tr><tr><td valign="top"><strong>src</strong></td><td valign="top"><p><strong>Application source code</strong></p><p>Source code files for the project.</p></td></tr><tr><td valign="top"><em>assets</em></td><td valign="top"><em>(Optional)</em> Private static resources used in the project and not intended to be publicly accessible. These might include images, fonts, and other media files.</td></tr><tr><td valign="top"><em>source</em></td><td valign="top"><em>(Optional)</em> Source code files that specifically target Microsoft .NET Framework 4.8. This is not necessarily legacy code, therefore the term “legacy” is normally avoided. (This is intentionally separated from other source code because .NET Framework 4.8 projects are difficult to work with using VS Code.)</td></tr></tbody></table>

## Source code project names

The name of a source code project that targets .NET uses Pascal Case: the first letter of each word in a multi-word identifier is capitalized, and there are no spaces or separators between words.

Use dots in the project name (as needed) to indicate architectural boundaries. For example:

* src/api/DanielMiller.Api
* src/cli/Workday.Integration
* src/lib/Shift.Assessment.Sdk
