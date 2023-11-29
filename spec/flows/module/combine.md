# Combining modules

Combining modules is the mechanism offered by powerd6 to allow for changes to
 modules to be carried out in a simple manner.

## Combination rules

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
      - If `B` has the property with a `null` value, then the property is removed from `C`
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
