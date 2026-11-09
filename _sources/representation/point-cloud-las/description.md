The point-cloud data type of the data-types register, represented in LAS.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/representation/point-cloud-las` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud/v1` of the data-types register and points (`df:format`) to the format [LAS](../../format/las/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.point-cloud`.

## Requested by

Created because existing roles need it: 4 roles of 3 Implementation Profiles of `bblocks-generic-profiles` (branch `planes/phase-1-docs`, `b0da6aa`) have the data type `point-cloud` and a schema with `contentMediaType` `application/vnd.las`, measured on 2026-11-09. They still carry that schema; they do not point to this representation yet.

- `implementation-profile/point-cloud-thinning/inputs/points`
- `implementation-profile/point-cloud-thinning/outputs/result`
- `implementation-profile/point-cloud-to-grid/inputs/points`
- `implementation-profile/point-cloud-to-shapes/inputs/points`

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
