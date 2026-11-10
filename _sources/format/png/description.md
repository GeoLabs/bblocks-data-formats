A lossless raster image encoding of greyscale, truecolour or indexed-colour pictures, with optional transparency.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/format/png` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [W3C Portable Network Graphics (PNG) Specification (Third Edition), W3C Recommendation 24 June 2025](https://www.w3.org/TR/png/) (`dct:conformsTo`)

The specification defines the media type `image/png` (its Appendix A.1).

## Observed media types

Measured on 2026-11-10 in the process descriptions of `bblocks-process-profiles-tests-1` (branch `planes/phase-4`, `ea01115`). No principal media type is set: none has been chosen.

| Media type | Observed in | Where |
|---|---|---|
| `image/png` | testbed | output `output_plot` of `algae-bloom.plot-image` (CWL `format: iana:image/png`); the 9 `*_plot.png` files of the two W1 runs of 2026-09-23 are identified as PNG by `file` (PNG signature) |

## Requested by

Added on 2026-11-10 for the representation [`rendered-image-png`](../../representation/rendered-image-png/), needed by the new process profiles of `bblocks-generic-profiles` (branch `planes/new-profiles`).

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
