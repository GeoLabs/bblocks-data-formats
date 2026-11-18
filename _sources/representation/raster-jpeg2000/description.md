The raster data type of the data-types register, represented in JPEG 2000.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/raster-jpeg2000` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://w3id.org/geolabs/ospd/data-types/data-type/raster/v1` of the data-types register and points (`df:format`) to the format [JPEG 2000](../../format/jpeg2000/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.raster`.

## Requested by

Added on 2026-11-18 for inputs and outputs of deployed processes (tier 4) of `bblocks-process-profiles` whose data type is `raster` and whose description declares this format. Measured on 2026-11-18 in the process descriptions (`processDescription.inherited.json`) of `bblocks-process-profiles-tests-1` (branch `planes/w3id-identifiers`, `bfa5cef`), by `.claude/bblocks-audit/tier4-formats/inventory.py`.

- [`algae-bloom/calculate-band`](https://w3id.org/geolabs/ospd/process-profiles/process-type/algae-bloom/calculate-band): input `band_a`, input `band_b`, input `band_c`, input `band_d`, input `band_e`, input `band_f`, input `band_g`, input `band_h`, input `band_i`, input `band_j`, input `band_k`, input `band_l`, input `band_m`, input `band_n`, input `band_o`, input `band_p`, input `band_q`, input `band_r`, input `band_s`, input `band_t`, input `band_u`, input `band_v`, input `band_w`, input `band_x`, input `band_y`, input `band_z`
- [`algae-bloom/plot-image`](https://w3id.org/geolabs/ospd/process-profiles/process-type/algae-bloom/plot-image): input `input_image`
- [`algae-bloom/reproject-image`](https://w3id.org/geolabs/ospd/process-profiles/process-type/algae-bloom/reproject-image): input `input_image`

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
