# Combining modules

Combining modules means that you will merge the contents of one module with another.

Combining modules is the main mechanism for players to interact with published
modules in order to craft their custom experiences.

## Combination rules

In the following section, modules will be named by capital letters
(`A`, `B`, `C`, etc) and the plus sign (`+`) will be used to represent a combination.

For example, `A+B=C` means: "Module `A` being combined with module `B`, resulting
in module `C`".

### Blanks

`A+{}=A`

When combining a module with a blank module, the results is the same as the first
module.

### Identity

`A+A=A`

When combining a module with itself, the result is the same as the first module.

### Non-commutative property

`A+B<>B+A`

When combining two modules, the order on which they are combined is meaningful and
may produce different results (due to the combination rules detailed below).

### Combination

For `A+B=C`, module `C` will follow these rules:

#### Authorship

Module `C` will contain all the authorship information from `A` and `B`.

#### Module information, Content and Schemas

Module information, content and schemas that are defined only on `A` or only on
`B` will be present in `C` without changes.

Module information, content and schemas that exist in  `A` and `B` will be merged
as follows:

- All properties that exist only on `A` or only on `B` will be unchanged.
- Properties that exist in `A` and `B` are modified:
  - If the property in `B` is `null`, then the property is removed from `C`.
  - If the property in `B` is not `null`, the the property in `C` will use the
    value from `B`

This set of rules is also known as a [JSON merge patch](https://datatracker.ietf.org/doc/html/rfc7386).
