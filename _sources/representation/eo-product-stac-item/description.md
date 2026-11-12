The eo-product data type of the data-types register, represented in STAC Item.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/eo-product-stac-item` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/eo-product/v1` of the data-types register and points (`df:format`) to the format [STAC Item](../../format/stac-item/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.eo-product`.

## Requested by

Added on 2026-11-10 for roles of the new Implementation Profiles of `bblocks-generic-profiles` (branch `planes/new-profiles`):

- [`implementation-profile/product-selection/outputs/products`](https://geolabs.github.io/bblocks-generic-profiles/def/implementation-profile/product-selection/outputs/products)
- [`implementation-profile/band-retrieval/inputs/product`](https://geolabs.github.io/bblocks-generic-profiles/def/implementation-profile/band-retrieval/inputs/product)

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
