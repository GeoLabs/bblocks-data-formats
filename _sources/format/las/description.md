A binary encoding of point cloud records.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/format/las` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [OGC 17-030r1 LAS Specification 1.4 OGC Community Standard](https://www.ogc.org/standards/las/) (`dct:conformsTo`)

The Implementation Profiles cite OGC 17-030r1 (LAS 1.4); the testbed states no version.

## Observed media types

Measured on 2026-11-09 in the Implementation Profiles of `bblocks-generic-profiles` (branch `planes/phase-1-docs`, `b0da6aa`) and in the testbed process descriptions of `bblocks-process-profiles-tests-1` (`5e4116d`). No principal media type is set: none has been chosen.

| Media type | Observed in | Where |
|---|---|---|
| `application/vnd.las` | implementation-profile | 4 roles of 3 Implementation Profiles (point-cloud data type), with the schema description `LAS (OGC 17-030r1)` |
| `application/x-ogc-lasf` | testbed | 4 inputs and outputs of the pointcloud processes |

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
