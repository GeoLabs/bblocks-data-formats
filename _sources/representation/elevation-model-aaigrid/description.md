The elevation-model data type of the data-types register, represented in Arc/Info ASCII Grid.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/elevation-model-aaigrid` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://w3id.org/geolabs/ospd/data-types/data-type/elevation-model/v1` of the data-types register and points (`df:format`) to the format [Arc/Info ASCII Grid](../../format/aaigrid/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.elevation-model`.

## Requested by

Added on 2026-11-18 for inputs and outputs of deployed processes (tier 4) of `bblocks-process-profiles` whose data type is `elevation-model` and whose description declares this format. Measured on 2026-11-18 in the process descriptions (`processDescription.inherited.json`) of `bblocks-process-profiles-tests-1` (branch `planes/w3id-identifiers`, `bfa5cef`), by `.claude/bblocks-audit/tier4-formats/inventory.py`.

- [`terrain/hillshading`](https://w3id.org/geolabs/ospd/process-profiles/process-type/terrain/hillshading): input `ELEVATION`
- [`terrain/slope`](https://w3id.org/geolabs/ospd/process-profiles/process-type/terrain/slope): input `ELEVATION`
- [`terrain/terrain-ruggedness-index`](https://w3id.org/geolabs/ospd/process-profiles/process-type/terrain/terrain-ruggedness-index): input `DEM`
- [`terrain/topographic-position-index`](https://w3id.org/geolabs/ospd/process-profiles/process-type/terrain/topographic-position-index): input `DEM`

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
