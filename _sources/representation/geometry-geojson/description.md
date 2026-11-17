The geometry data type of the data-types register, represented in GeoJSON.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://w3id.org/geolabs/ospd/data-types/data-type/geometry/v1` of the data-types register and points (`df:format`) to the format [GeoJSON](../../format/geojson/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.geometry`. `hasFormat` names [`geometry-gml`](../geometry-gml/), which represents the same data type in another format.

## Schema

`df:jsonSchemaFragment` is a reference to `https://geojson.org/schema/Geometry.json`, published by [geojson/schema](https://github.com/geojson/schema). The schemas of https://github.com/geojson/schema are published without a version (the URL serves the latest build), are written in JSON Schema draft-07, and cannot check that linear rings are closed or follow the right-hand rule (RFC 7946, section 3.1.6).

## Requested by

Added on 2026-11-10 for roles of the new Implementation Profiles of `bblocks-generic-profiles` (branch `planes/new-profiles`):

- [`implementation-profile/product-selection/inputs/areaOfInterest`](https://w3id.org/geolabs/ospd/generic-profiles/implementation-profile/product-selection/inputs/areaOfInterest)

The other GeoJSON object types were added the same day: every object type that geojson/schema publishes and that the data-types register defines now has a GeoJSON representation.

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
