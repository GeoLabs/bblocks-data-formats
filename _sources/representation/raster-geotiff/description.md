The raster data type of the data-types register, represented in GeoTIFF.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/raster-geotiff` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/raster/v1` of the data-types register and points (`df:format`) to the format [GeoTIFF](../../format/geotiff/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.raster`.

## Requested by

Created because existing roles need it: 12 roles of 7 Implementation Profiles of `bblocks-generic-profiles` (branch `planes/phase-1-docs`, `b0da6aa`) have the data type `raster` and a schema with `contentMediaType` `image/tiff`, measured on 2026-11-09. They still carry that schema; they do not point to this representation yet.

- `implementation-profile/radiometric-index/inputs/rasters`
- `implementation-profile/radiometric-index/outputs/raster`
- `implementation-profile/raster-band-math-multiband/inputs/rasters`
- `implementation-profile/raster-band-math-multiband/outputs/raster`
- `implementation-profile/raster-band-math/inputs/rasters`
- `implementation-profile/raster-crop/inputs/raster`
- `implementation-profile/raster-crop/outputs/raster`
- `implementation-profile/raster-extent/inputs/raster`
- `implementation-profile/raster-format-conversion/inputs/raster`
- `implementation-profile/raster-format-conversion/outputs/raster`
- `implementation-profile/raster-reprojection/inputs/raster`
- `implementation-profile/raster-reprojection/outputs/raster`

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
