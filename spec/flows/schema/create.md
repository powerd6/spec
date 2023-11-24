#### Creating a schema

When creating a schema define it with the appropriate fields.

Schemas have two components: validation, and rendering logic.

Schema validation is defined with [JSON schema](https://json-schema.org/) formats.

Schema rendering logic are defined with [tera templates](https://github.com/Keats/tera).

While rendering logic is not required, rendering is not possible without it.

Its possible to keep rendering logic as a separate module, but that may complicate things for users wanting to use your schema.
