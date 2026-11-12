The elevation-model data type of the data-types register, represented in GeoTIFF.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/elevation-model-geotiff` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/v1` of the data-types register and points (`df:format`) to the format [GeoTIFF](../../format/geotiff/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.elevation-model`.

## Requested by

Created because existing roles need it: 4 roles of 4 Implementation Profiles of `bblocks-generic-profiles` (branch `planes/phase-1-docs`, `b0da6aa`) have the data type `elevation-model` and a schema with `contentMediaType` `image/tiff`, measured on 2026-11-09. They still carry that schema; they do not point to this representation yet.

- `implementation-profile/analytical-hillshading/inputs/elevation`
- `implementation-profile/slope/inputs/elevation`
- `implementation-profile/terrain-ruggedness-index/inputs/elevation`
- `implementation-profile/topographic-position-index/inputs/elevation`

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
