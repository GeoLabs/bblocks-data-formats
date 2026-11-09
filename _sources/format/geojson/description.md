A JSON encoding of geographic features and geometries.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/format/geojson` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [RFC 7946 The GeoJSON Format](https://www.rfc-editor.org/rfc/rfc7946) (`dct:conformsTo`)

RFC 7946 is the only GeoJSON specification cited; the testbed states no version.

## Observed media types

Measured on 2026-11-09 in the Implementation Profiles of `bblocks-generic-profiles` (branch `planes/phase-1-docs`, `b0da6aa`) and in the testbed process descriptions of `bblocks-process-profiles-tests-1` (`5e4116d`). No principal media type is set: none has been chosen.

| Media type | Observed in | Where |
|---|---|---|
| `application/geo+json` | testbed | 3 `aoi` inputs of the algae-bloom processes |

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
