The raster-single-band data type of the data-types register, represented in JPEG.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/raster-single-band-jpeg` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://w3id.org/geolabs/ospd/data-types/data-type/raster-single-band/v1` of the data-types register and points (`df:format`) to the format [JPEG](../../format/jpeg/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.raster-single-band`.

## Requested by

Added on 2026-11-18 for inputs and outputs of deployed processes (tier 4) of `bblocks-process-profiles` whose data type is `raster-single-band` and whose description declares this format. Measured on 2026-11-18 in the process descriptions (`processDescription.inherited.json`) of `bblocks-process-profiles-tests-1` (branch `planes/w3id-identifiers`, `bfa5cef`), by `.claude/bblocks-audit/tier4-formats/inventory.py`.

- [`raster/band-math`](https://w3id.org/geolabs/ospd/process-profiles/process-type/raster/band-math): output `out`

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
