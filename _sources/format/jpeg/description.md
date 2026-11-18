A lossy image encoding of continuous-tone greyscale or colour pictures.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/format/jpeg` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [ITU-T Recommendation T.81, Information technology - Digital compression and coding of continuous-tone still images - Requirements and guidelines](https://www.itu.int/rec/T-REC-T.81) (`dct:conformsTo`)

The page of the Recommendation was read on 2026-11-18 for its title and editions (T.81 (09/92), Corrigendum 1 (01/04)); its text was not read.

## Observed media types

Measured on 2026-11-18 in the process descriptions (`processDescription.inherited.json`) of `bblocks-process-profiles-tests-1` (branch `planes/w3id-identifiers`, `bfa5cef`), by `.claude/bblocks-audit/tier4-formats/inventory.py`. No principal media type is set: none has been chosen.

| Media type | Observed in |
|---|---|
| `image/jpeg` | testbed |

Where it is declared:

- [`raster/band-math`](https://w3id.org/geolabs/ospd/process-profiles/process-type/raster/band-math): input `il`, output `out`
- [`raster/band-math-multiband`](https://w3id.org/geolabs/ospd/process-profiles/process-type/raster/band-math-multiband): input `il`, input `incontext`, output `out`
- [`raster/extent`](https://w3id.org/geolabs/ospd/process-profiles/process-type/raster/extent): input `in`
- [`raster/extract-roi`](https://w3id.org/geolabs/ospd/process-profiles/process-type/raster/extract-roi): input `in`, input `mode.fit.im`, output `out`
- [`raster/radiometric-index`](https://w3id.org/geolabs/ospd/process-profiles/process-type/raster/radiometric-index): input `in`, output `out`

## Requested by

Added on 2026-11-18 for the representations [`raster-jpeg`](../../representation/raster-jpeg/), [`raster-single-band-jpeg`](../../representation/raster-single-band-jpeg/), needed by the deployed processes above (tier 4).

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
