A TIFF-based encoding of georeferenced raster data.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/format/geotiff` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [OGC GeoTIFF Standard](https://www.ogc.org/standards/geotiff/) (`dct:conformsTo`)

No version of the GeoTIFF standard is stated where the format is served.

## Observed media types

Measured on 2026-11-09 in the Implementation Profiles of `bblocks-generic-profiles` (branch `planes/phase-1-docs`, `b0da6aa`) and in the testbed process descriptions of `bblocks-process-profiles-tests-1` (`5e4116d`). No principal media type is set: none has been chosen.

| Media type | Observed in | Where |
|---|---|---|
| `image/tiff` | implementation-profile | 22 roles of 12 Implementation Profiles (elevation-model, raster and raster-single-band data types), 20 of them with the schema description `GeoTIFF` |
| `image/tiff` | testbed | 61 inputs and outputs of the testbed processes |
| `image/tiff; application=geotiff` | testbed | 56 inputs and outputs of the algae-bloom processes |

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
