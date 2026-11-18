The surface data type of the data-types register, represented in KML.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/surface-kml` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://w3id.org/geolabs/ospd/data-types/data-type/surface/v1` of the data-types register and points (`df:format`) to the format [KML](../../format/kml/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.surface`.

## Requested by

Added on 2026-11-18 for inputs and outputs of deployed processes (tier 4) of `bblocks-process-profiles` whose data type is `surface` and whose description declares this format. Measured on 2026-11-18 in the process descriptions (`processDescription.inherited.json`) of `bblocks-process-profiles-tests-1` (branch `planes/w3id-identifiers`, `bfa5cef`), by `.claude/bblocks-audit/tier4-formats/inventory.py`.

- [`raster/extent`](https://w3id.org/geolabs/ospd/process-profiles/process-type/raster/extent): output `out`
- [`vector/geometry-extent`](https://w3id.org/geolabs/ospd/process-profiles/process-type/vector/geometry-extent): output `EXTENTS`

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
