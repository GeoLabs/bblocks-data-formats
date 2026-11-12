The geometry data type of the data-types register, represented in GML.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/geometry-gml` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/geometry/v1` of the data-types register and points (`df:format`) to the format [GML](../../format/gml/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.geometry`.

## Requested by

Created because existing roles need it: 31 roles of 15 Implementation Profiles of `bblocks-generic-profiles` (branch `planes/phase-1-docs`, `b0da6aa`) have the data type `geometry` and a schema with `contentMediaType` `text/xml`, measured on 2026-11-09. They still carry that schema; they do not point to this representation yet.

- `implementation-profile/buffer/inputs/geometry`
- `implementation-profile/contains/inputs/geometry1`
- `implementation-profile/contains/inputs/geometry2`
- `implementation-profile/convex-hull/inputs/geometry`
- `implementation-profile/convex-hull/outputs/result`
- `implementation-profile/crosses/inputs/geometry1`
- `implementation-profile/crosses/inputs/geometry2`
- `implementation-profile/difference/inputs/geometry1`
- `implementation-profile/difference/inputs/geometry2`
- `implementation-profile/difference/outputs/result`
- `implementation-profile/disjoint/inputs/geometry1`
- `implementation-profile/disjoint/inputs/geometry2`
- `implementation-profile/equals/inputs/geometry1`
- `implementation-profile/equals/inputs/geometry2`
- `implementation-profile/geometry-extent/inputs/geometry`
- `implementation-profile/intersection/inputs/geometry1`
- `implementation-profile/intersection/inputs/geometry2`
- `implementation-profile/intersection/outputs/result`
- `implementation-profile/intersects/inputs/geometry1`
- `implementation-profile/intersects/inputs/geometry2`
- `implementation-profile/is-simple/inputs/geometry`
- `implementation-profile/symdifference/inputs/geometry1`
- `implementation-profile/symdifference/inputs/geometry2`
- `implementation-profile/symdifference/outputs/result`
- `implementation-profile/touches/inputs/geometry1`
- `implementation-profile/touches/inputs/geometry2`
- `implementation-profile/union/inputs/geometry1`
- `implementation-profile/union/inputs/geometry2`
- `implementation-profile/union/outputs/result`
- `implementation-profile/within/inputs/geometry1`
- `implementation-profile/within/inputs/geometry2`

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
