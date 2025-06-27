# Table of contents

## Getting Started

* [Developer Documentation](README.md)
* [Components](components/README.md)
  * [Utility Components](components/utility-components/README.md)
    * [Metadata](components/utility-components/metadata.md)
    * [Security](components/utility-components/security/README.md)
      * [Setting Up New Organizations](components/utility-components/security/setting-up-new-organizations/README.md)
        * [Organization Specific Settings (Advanced Configuration)](components/utility-components/security/setting-up-new-organizations/organization-specific-settings-advanced-configuration.md)
        * [Existing Organization Customization](components/utility-components/security/setting-up-new-organizations/existing-organization-customization.md)
      * [Impersonations](components/utility-components/security/impersonations.md)
      * [Permissions](components/utility-components/security/permissions.md)
      * [Permissions (Proposed Improvement)](components/utility-components/security/permissions-proposed-improvement.md)
      * [Organization Collections](components/utility-components/security/organization-collections.md)
    * [Setup](components/utility-components/setup/README.md)
      * [Colours](components/utility-components/setup/colours.md)

## API - v1

* [Introduction](api-v1/introduction.md)
* [API Reference](api-v1/api-reference/README.md)
  * ```yaml
    props:
      models: true
    type: builtin:openapi
    dependencies:
      spec:
        ref:
          kind: openapi
          spec: api-v1
    ```

## API - v2

* [API Reference](api-v2/api-reference/README.md)
  * ```yaml
    props:
      models: true
    type: builtin:openapi
    dependencies:
      spec:
        ref:
          kind: openapi
          spec: api-v2
    ```

## Resources

* [.NET Versions](dotnet-versions.md)

## Integrations

* [Safe Exam Browser](integrations/safe-exam-browser.md)
* [Single Sign-On](integrations/single-sign-on.md)
