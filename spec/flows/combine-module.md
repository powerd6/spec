# Combining modules

Combining modules means that you will merge the contents of one module with another.

In this process, some rules apply, however their simplest form is as follows:

- All unique content is maintained in both sides;
- Content with the same ID is merged as a patch;
- Content can be deleted by a special mechanism.

Combining modules is the main mechanism for players to interact with published
modules in order to craft their custom experiences.

## Combination rules

In the following section, modules will be named by capital letters
(`A`, `B`, `C`, etc) and the plus sign (`+`) will be used to represent a combination.
The symbol `{}` will be used to represent a blank module,
and the symbol `ø` will be used to represent a blank property.

For example, `A+B=C` means: "Module `A` being combined with module `B`, resulting in module `C`".

### Blanks

`A+{}=A`

When combining a module with a blank module, the results is the same as the first module.


### Identity

`A+A=A`

When combining a module with itself, the result is the same as the first module.

### Non-commutative property

`A+B<>B+A`

When combining two modules, the order on which they are combined is meaningful and
may produce different results.

### Combination

Combining a module `A` with an empty module will result in a exact copy of `A`

Combining a module `A` with itself will result in an exact copy of `A`

When combining a module `A` with another module `B` (in the order `A+B`),
resulting in the module `C`, the following rules apply:

- The module `C` will contain authorship information from `A` and `B`
- For schemas:
   - Schemas defined only on `A` will be present in the module `C` without changes
   - Schemas defined only on `B` will be present in the module `C` without changes
   - Schemas defined on `A` and `B` will be present in the module `C` with
      modifications as follows:
      - All properties that exist only on `A` will be unchanged
      - All properties that exist only on `B` will be unchanged
      - Properties that exist on `A` and `B` will be modified as follows:
         - If `B` has the property with a `null` value, then the property is
            removed from `C`
         - If `B` has a property with a non-`null` value, then the value from `B`
            will be present in `C`
- For content:
   - Content defined only on `A` will be present in the module `C` without changes
   - Content defined only on `B` will be present in the module `C` without changes
   - Content defined on `A` and `B` will be present in the module `C` with
      modifications as follows:
      - All properties that exist only on `A` will be unchanged
      - All properties that exist only on `B` will be unchanged
      - Properties that exist on `A` and `B` will be modified as follows:
         - If `B` has the property with a `null` value, then the property is removed
            from `C`
         - If `B` has a property with a non-`null` value, then the value from `B`
            will be present in `C`

## Order of operations

When combining modules, the order of the operations matter.

Take for example the two modules `A` and `B`. The result of combining `A+B` vs
`B+A` might differ based on the nature of the modules.
