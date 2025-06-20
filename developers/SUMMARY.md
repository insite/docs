# Table of contents

## Getting Started

* [Developer Documentation](README.md)

## Shift API (v1)

* [API Reference](shift-iq-api/api-reference/README.md)
  * ```yaml
    type: builtin:openapi
    props:
      models: true
    dependencies:
      spec:
        ref:
          kind: openapi
          spec: api-v1
    ```

## Shift API (v2)

* [API Reference](shift-api-v2/api-reference/README.md)
  * ```yaml
    type: builtin:openapi
    props:
      models: true
    dependencies:
      spec:
        ref:
          kind: openapi
          spec: api-v2
    ```

## Resources

* [.NET Versions](<README (1).md>)

## Integrations

* [Single Sign-On](integrations/single-sign-on.md)
