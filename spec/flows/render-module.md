# Rendering a module

Rendering a module is the process that creates a finished book.

This process combines the information in the schema and content to create
human-readable output.

The order in which the content will be rendered on is defined in the following
manner:

- Each schema will be rendered in the order based on:
  - the `renderOrder` property of the schema, from lower to highest
  - the `name` of the schema, alphabetically
- Each content piece for a given schema will be rendered in the order based on:
  - the `renderOrder` property of the content, from lower to highest
  - the `id` of the content, alphabetically
