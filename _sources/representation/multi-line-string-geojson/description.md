The multi-line-string data type of the data-types register, represented in GeoJSON.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/multi-line-string-geojson` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/multi-line-string/v1` of the data-types register and points (`df:format`) to the format [GeoJSON](../../format/geojson/): a GeoJSON `MultiLineString` object (RFC 7946). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.multi-line-string`.

## Schema

`df:jsonSchemaFragment` is a reference to `https://geojson.org/schema/MultiLineString.json`, published by [geojson/schema](https://github.com/geojson/schema). The schemas of https://github.com/geojson/schema are published without a version (the URL serves the latest build), are written in JSON Schema draft-07, and cannot check that linear rings are closed or follow the right-hand rule (RFC 7946, section 3.1.6).

## Requested by

No role requests it yet. Added on 2026-11-17 by decision of Gérald: every GeoJSON object type that geojson/schema publishes and that the data-types register defines has a GeoJSON representation (Point, LineString, Polygon, MultiPoint, MultiLineString, MultiPolygon, GeometryCollection, Geometry, Feature, FeatureCollection). The register specification allows a representation for each object type a format's specification defines since that date.

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
