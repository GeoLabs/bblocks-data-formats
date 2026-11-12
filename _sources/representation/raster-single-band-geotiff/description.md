The raster-single-band data type of the data-types register, represented in GeoTIFF.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/raster-single-band-geotiff` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/v1` of the data-types register and points (`df:format`) to the format [GeoTIFF](../../format/geotiff/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.raster-single-band`.

## Requested by

Created because existing roles need it: 6 roles of 6 Implementation Profiles of `bblocks-generic-profiles` (branch `planes/phase-1-docs`, `b0da6aa`) have the data type `raster-single-band` and a schema with `contentMediaType` `image/tiff`, measured on 2026-11-09. They still carry that schema; they do not point to this representation yet.

- `implementation-profile/analytical-hillshading/outputs/result`
- `implementation-profile/point-cloud-to-grid/outputs/result`
- `implementation-profile/raster-band-math/outputs/raster`
- `implementation-profile/slope/outputs/result`
- `implementation-profile/terrain-ruggedness-index/outputs/result`
- `implementation-profile/topographic-position-index/outputs/result`

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
