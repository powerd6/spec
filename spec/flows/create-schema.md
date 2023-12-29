# Creating a schema

Schemas are contextual pieces of information that help creators build content.

Schemas have two components: validation rules and rendering logic.

## Validation rules

Validation is defined with JSON Schema formats and they help ensure that the
"shape" of the data is correct.

## Rendering logic

Rendering logic is defined with [`tera` templates](https://github.com/Keats/tera),
and they are executed by tools when rendering a module.

These templates are executed with the following information present in their context:

| Property | Description |
| --- | --- |
| `content` | The current piece of content that is being rendered |
| `module` | The entire module that contains the content piece |

When creating writing the template, you can use both of these properties to implement
rich logic and referencing within your rendering template.

For example, you could implement a feature that renders an `effect` schema for
each referenced effect inside of an `item`.