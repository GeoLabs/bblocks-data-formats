An XML encoding of geographic features, their geometries and their presentation.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/format/kml` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [OGC 12-007r2 OGC KML 2.3](https://docs.ogc.org/is/12-007r2/12-007r2.html) (`dct:conformsTo`)

The standard was read on 2026-11-18 for its title, number and version only; the KML version the deployed processes produce or accept is not stated where they are served.

## Observed media types

Measured on 2026-11-18 in the process descriptions (`processDescription.inherited.json`) of `bblocks-process-profiles-tests-1` (branch `planes/w3id-identifiers`, `bfa5cef`), by `.claude/bblocks-audit/tier4-formats/inventory.py`. No principal media type is set: none has been chosen.

| Media type | Observed in |
|---|---|
| `application/vnd.google-earth.kml+xml` | testbed |

Where it is declared:

- [`pointcloud/point-cloud-to-shapes`](https://w3id.org/geolabs/ospd/process-profiles/process-type/pointcloud/point-cloud-to-shapes): output `SHAPES`
- [`raster/extent`](https://w3id.org/geolabs/ospd/process-profiles/process-type/raster/extent): output `out`
- [`raster/extract-roi`](https://w3id.org/geolabs/ospd/process-profiles/process-type/raster/extract-roi): input `mode.fit.vect`
- [`vector/geometry-extent`](https://w3id.org/geolabs/ospd/process-profiles/process-type/vector/geometry-extent): input `SHAPES`, output `EXTENTS`

## Requested by

Added on 2026-11-18 for the representations [`geometry-kml`](../../representation/geometry-kml/), [`surface-kml`](../../representation/surface-kml/), [`feature-collection-kml`](../../representation/feature-collection-kml/), needed by the deployed processes above (tier 4).

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
