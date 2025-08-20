# Table of contents

## Getting Started

* [Developer Documentation](README.md)

***

* [Queries and commands](queries-and-commands.md)

## API - v1

* [Introduction](api-v1/introduction.md)
* [Endpoints](api-v1/api-reference/README.md)
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

* [Introduction](api-v2/introduction.md)
* [Authentication](api-v2/authentication.md)
* [Endpoints](api-v2/navigating-the-api.md)
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

***

* [Request and response formats](request-and-response-formats.md)
* [Rate limits and throttling](rate-limits-and-throttling.md)

## Resources

* [.NET](dotnet-versions.md)

***

* [Date and time values](date-and-time-values.md)

## Integrations

* [Safe Exam Browser](integrations/safe-exam-browser.md)
* [Single Sign-On](integrations/single-sign-on.md)
