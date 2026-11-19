A wavelet-based image encoding, lossless or lossy, of one or more components, in the JP2 file format.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/format/jpeg2000` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [ITU-T Recommendation T.800, Information technology - JPEG 2000 image coding system: Core coding system](https://www.itu.int/rec/T-REC-T.800) (`dct:conformsTo`)

The page of the Recommendation was read on 2026-11-18 for its title and editions (in force: T.800 (07/24)); its text was not read, and the edition the observed files follow is not stated where they are served.

Decision C8 of 2026-11-10 declined a JPEG 2000 format because no media type was observed for it (only a SAFE Implementation Profile needed it). `image/jp2` is now observed on the testbed, so the rule that every format has a media type holds.

## Observed media types

Measured on 2026-11-18 in the process descriptions (`processDescription.inherited.json`) of `bblocks-process-profiles-tests-1` (branch `planes/w3id-identifiers`, `bfa5cef`), by `.claude/bblocks-audit/tier4-formats/inventory.py`. No principal media type is set: none has been chosen.

| Media type | Observed in |
|---|---|
| `image/jp2` | testbed |

Where it is declared:

- [`algae-bloom/calculate-band`](https://w3id.org/geolabs/ospd/process-profiles/process-type/algae-bloom/calculate-band): input `band_a`, input `band_b`, input `band_c`, input `band_d`, input `band_e`, input `band_f`, input `band_g`, input `band_h`, input `band_i`, input `band_j`, input `band_k`, input `band_l`, input `band_m`, input `band_n`, input `band_o`, input `band_p`, input `band_q`, input `band_r`, input `band_s`, input `band_t`, input `band_u`, input `band_v`, input `band_w`, input `band_x`, input `band_y`, input `band_z`
- [`algae-bloom/plot-image`](https://w3id.org/geolabs/ospd/process-profiles/process-type/algae-bloom/plot-image): input `input_image`
- [`algae-bloom/reproject-image`](https://w3id.org/geolabs/ospd/process-profiles/process-type/algae-bloom/reproject-image): input `input_image`

## Requested by

Added on 2026-11-18 for the representations [`raster-jpeg2000`](../../representation/raster-jpeg2000/), needed by the deployed processes above (tier 4).

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
