# Publishing a module

Publishing a module means making it available to the public.

When doing so, it is important to add information to the module that explains where
it was sourced from. This is done by providing information in the `module` section.

It is important to note that the module should only contain one `module.references`
property named after the unique module id, where the value are one or more
[URI references](https://datatracker.ietf.org/doc/html/rfc3986) to where to source the module from.

## Ensuring unique module identifiers

There is not a universal way to fetch a unique module identifier.

However, some strategies can greatly improve the chance of an identifier being
unique:

- Use descriptive names
  - `30-fire-spells-for-pyromaniacs` instead of `fire-spells`
- Use your company name in the identifier
  - `corp-tales-from-the-dungeons` instead of `tales-from-the-dungeons`
- Use the initial publishing date in the identifier
  - `2023-10-23-funny-items` instead of `funny-items`
- Combine all the previous strategies

## Handling purchases/payments

To sell a module, a creator should use a file-sharing service that processes payments.

For example, a creator may choose to share a module only to their subscribers, while others may simply host it on their website for free.