# Table of contents

## Getting Started

* [Developer Documentation](README.md)

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

* [Introduction](api-v2/introduction.md)
* [Authentication and authorization](api-v2/authentication-and-authorization.md)
* [Endpoints](api-v2/endpoints/README.md)
  * [API Reference](api-v2/endpoints/api-reference/README.md)
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

## Resources

* [.NET versions](dotnet-versions.md)

***

* [Date and time values](date-and-time-values.md)

## Integrations

* [Safe Exam Browser](integrations/safe-exam-browser.md)
* [Single Sign-On](integrations/single-sign-on.md)
