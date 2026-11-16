The feature-collection data type of the data-types register, represented in GeoJSON.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-geojson` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/v1` of the data-types register and points (`df:format`) to the format [GeoJSON](../../format/geojson/). In GeoJSON it is a `FeatureCollection` object (RFC 7946, section 3.3). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.feature-collection`. `hasFormat` names [`feature-collection-gml`](../feature-collection-gml/), which represents the same data type in another format.

## Schema

`df:jsonSchemaFragment` is a reference to `https://geojson.org/schema/FeatureCollection.json`, published by [geojson/schema](https://github.com/geojson/schema). The schemas of https://github.com/geojson/schema are published without a version (the URL serves the latest build), are written in JSON Schema draft-07, and cannot check that linear rings are closed or follow the right-hand rule (RFC 7946, section 3.1.6).

## Requested by

No role requests it yet. Added on 2026-11-17 to complete, in GeoJSON, the representations of a data type already represented in GML (decision of 2026-11-17; the register specification allows it since that date): the geometry, point, surface and feature-collection data types each have a GML and a GeoJSON representation.

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
