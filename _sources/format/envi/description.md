Raw raster cells, band interleaved by line, by pixel or band sequential, described by an ENVI-style .hdr text header.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/format/envi` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [GDAL raster driver documentation: ENVI -- ENVI .hdr Labelled Raster](https://gdal.org/en/stable/drivers/raster/envi.html) (`dct:conformsTo`)

No formal specification of this format is published: the GDAL driver documentation, read on 2026-11-18, is the reference cited, and it cites no specification. The media type `application/x-ogc-envi` is not registered with IANA (`x-` prefix); it is the one the deployed processes declare.

## Observed media types

Measured on 2026-11-18 in the process descriptions (`processDescription.inherited.json`) of `bblocks-process-profiles-tests-1` (branch `planes/w3id-identifiers`, `bfa5cef`), by `.claude/bblocks-audit/tier4-formats/inventory.py`. No principal media type is set: none has been chosen.

| Media type | Observed in |
|---|---|
| `application/x-ogc-envi` | testbed |

Where it is declared:

- [`pointcloud/point-cloud-to-grid`](https://w3id.org/geolabs/ospd/process-profiles/process-type/pointcloud/point-cloud-to-grid): output `COUNT`, output `GRIDS`, output `GRID`
- [`terrain/hillshading`](https://w3id.org/geolabs/ospd/process-profiles/process-type/terrain/hillshading): input `ELEVATION`, output `SHADE`
- [`terrain/slope`](https://w3id.org/geolabs/ospd/process-profiles/process-type/terrain/slope): input `ELEVATION`, output `ASPECT`, output `C_CROS`, output `C_GENE`, output `C_LONG`, output `C_MAXI`, output `C_MINI`, output `C_PLAN`, output `C_PROF`, output `C_ROTO`, output `C_TANG`, output `C_TOTA`, output `SLOPE`
- [`terrain/terrain-ruggedness-index`](https://w3id.org/geolabs/ospd/process-profiles/process-type/terrain/terrain-ruggedness-index): input `DEM`, output `TRI`
- [`terrain/topographic-position-index`](https://w3id.org/geolabs/ospd/process-profiles/process-type/terrain/topographic-position-index): input `DEM`, output `TPI`

## Requested by

Added on 2026-11-18 for the representations [`raster-single-band-envi`](../../representation/raster-single-band-envi/), [`elevation-model-envi`](../../representation/elevation-model-envi/), needed by the deployed processes above (tier 4).

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
