The surface data type of the data-types register, represented in GeoJSON.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/surface-geojson` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/surface/v1` of the data-types register and points (`df:format`) to the format [GeoJSON](../../format/geojson/). GeoJSON has no Surface type: a surface is encoded as a `Polygon` or a `MultiPolygon` geometry object (RFC 7946, sections 3.1.6 and 3.1.7). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.surface`. `hasFormat` names [`surface-gml`](../surface-gml/), which represents the same data type in another format.

## Requested by

No role requests it yet. Added on 2026-11-17 to complete, in GeoJSON, the representations of a data type already represented in GML (decision of 2026-11-17; the register specification allows it since that date): the geometry, point, surface and feature-collection data types each have a GML and a GeoJSON representation.

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
