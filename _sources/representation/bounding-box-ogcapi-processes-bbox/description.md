The bounding-box data type of the data-types register, represented as an OGC API - Processes bbox object.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/v1` of the data-types register and points (`df:format`) to the format [OGC API - Processes bounding box](../../format/ogcapi-processes-bbox/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.bounding-box`.

## Requested by

Created on 2026-11-09 because one existing role needs it: `implementation-profile/raster-crop/inputs/areaOfInterest` of `bblocks-generic-profiles`, data type `bounding-box`, whose `schema` was a `$ref` to `ogc.api.processes.part1.v1.schemas.bbox`. That role points to this representation from branch `planes/phase-3` of that register.

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
