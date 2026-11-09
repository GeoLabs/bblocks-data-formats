The feature-collection data type of the data-types register, represented in GML.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/representation/feature-collection-gml` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/v1` of the data-types register and points (`df:format`) to the format [GML](../../format/gml/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.feature-collection`.

## Requested by

Created because existing roles need it: 1 roles of 1 Implementation Profiles of `bblocks-generic-profiles` (branch `planes/phase-1-docs`, `b0da6aa`) have the data type `feature-collection` and a schema with `contentMediaType` `text/xml`, measured on 2026-11-09. They still carry that schema; they do not point to this representation yet.

- `implementation-profile/point-cloud-to-shapes/outputs/result`

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
