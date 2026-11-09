An XML encoding of geographic features and geometries.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/format/gml` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [OGC Geography Markup Language (GML) Encoding Standard](https://www.ogc.org/standards/gml/) (`dct:conformsTo`)

No GML version is established: the Implementation Profiles say `GML` only, and the testbed's `contentSchema` values (`http://fooa/gml/3.1.0/polygon.xsd`, `http://fooa/gml/3.1.0/point.xsd`) are on a placeholder host.

## Observed media types

Measured on 2026-11-09 in the Implementation Profiles of `bblocks-generic-profiles` (branch `planes/phase-1-docs`, `b0da6aa`) and in the testbed process descriptions of `bblocks-process-profiles-tests-1` (`5e4116d`). No principal media type is set: none has been chosen.

| Media type | Observed in | Where |
|---|---|---|
| `text/xml` | implementation-profile | 38 roles of 19 Implementation Profiles (geometry, surface, point and feature-collection data types), each with a schema description that starts with `GML` |
| `text/xml` | testbed | 34 inputs and outputs of the sqlmm processes whose description or contentSchema names GML |

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
