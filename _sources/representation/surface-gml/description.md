The surface data type of the data-types register, represented in GML.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/representation/surface-gml` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/surface/v1` of the data-types register and points (`df:format`) to the format [GML](../../format/gml/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.surface`.

## Requested by

Created because existing roles need it: 5 roles of 5 Implementation Profiles of `bblocks-generic-profiles` (branch `planes/phase-1-docs`, `b0da6aa`) have the data type `surface` and a schema with `contentMediaType` `text/xml`, measured on 2026-11-09. They still carry that schema; they do not point to this representation yet.

- `implementation-profile/area/inputs/geometry`
- `implementation-profile/buffer/outputs/result`
- `implementation-profile/centroid/inputs/geometry`
- `implementation-profile/geometry-extent/outputs/result`
- `implementation-profile/raster-extent/outputs/result`

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
