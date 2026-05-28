# SpaceItem

A single entry in the Space's ordered list. The Space renders
items in the order they appear in `space_items`; products and links
can interleave freely (e.g. link → product → link → course → link).
`kind` discriminates against ProductStorefront (`product`) vs a
StorefrontLink already stored in `storefront_links` (`link`).
`hidden` lets creators take an item off the Space without losing
the item itself — products restore via the picker, links by
flipping the flag.


## Fields

| Field                                                                                                                                 | Type                                                                                                                                  | Required                                                                                                                              | Description                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `kind`                                                                                                                                | [Models::Components::Kind](../../models/shared/kind.md)                                                                               | :heavy_check_mark:                                                                                                                    | What `id` refers to: a product, or a storefront_links entry.                                                                          |
| `id`                                                                                                                                  | *::String*                                                                                                                            | :heavy_check_mark:                                                                                                                    | Identifier of the referenced product or link.                                                                                         |
| `hidden`                                                                                                                              | *T.nilable(T::Boolean)*                                                                                                               | :heavy_minus_sign:                                                                                                                    | If true, the renderer skips this item. Lets creators hide an item without removing it from the Space's order or deleting it outright. |