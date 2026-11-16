The eo-product data type of the data-types register, represented in EO GeoJSON.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/eo-product-eo-geojson` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/eo-product/v1` of the data-types register and points (`df:format`) to the format [EO GeoJSON](../../format/eo-geojson/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.eo-product`. `hasFormat` names [`eo-product-stac-item`](../eo-product-stac-item/), which represents the same data type in another format.

## Schema

`df:jsonSchemaFragment` is a reference to the `EarthObservation` definition of `https://schemas.opengis.net/eo-geojson/1.0/eo-geojson-schema.json`, the JSON Schema OGC publishes for OGC 17-003r2 (JSON Schema draft-04): one EO product, a GeoJSON Feature.

## Requested by

No role requests it yet. Added on 2026-11-17 by decision of Gérald, to complete, in another format, the representations of a data type that already has one (the register specification allows it since that date).

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
