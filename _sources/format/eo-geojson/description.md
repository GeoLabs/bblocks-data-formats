A GeoJSON encoding of Earth observation dataset metadata: a Feature, or a FeatureCollection, that describes EO products.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type: [`eo-product-eo-geojson`](../../representation/eo-product-eo-geojson/).

## Specification

- [OGC 17-003r2 EO Dataset Metadata GeoJSON(-LD) Encoding Standard 1.0](https://docs.ogc.org/is/17-003r2/17-003r2.html) (`dct:conformsTo`)

The JSON Schema fragment `$ref`s the JSON Schema OGC publishes for the standard: https://schemas.opengis.net/eo-geojson/1.0/eo-geojson-schema.json (checked on 2026-11-17, HTTP 200, `application/json`). Its title is "GeoJSON encoding of OGC 17-003 Earth Observation Metadata"; it is written in JSON Schema draft-04 and its root is the `EarthObservation` definition. The same directory publishes a standalone copy (`eo-geojson-schema-standalone.json`), the normative JSON-LD context (`eo-geojson.jsonld`) and four examples.

## Media type taken from the specification

`application/geo+json` (`df:inferredMediaType`, and `df:primaryMediaType`), source [OGC 17-003r2 EO Dataset Metadata GeoJSON(-LD) Encoding Standard 1.0](https://docs.ogc.org/is/17-003r2/17-003r2.html). Stated by OGC 17-003r2, chapter 9, Media Types for any data encoding(s): "When EO Dataset Metadata is delivered using HTTP, the following MIME media types shall be used." The table gives application/geo+json for the "GeoJSON representation with implicit normative context or normative context linked via a http://www.w3.org/ns/json-ld#context HTTP Link Header"; its two other rows are the GeoJSON-LD representations (application/ld+json, with or without a profile parameter), which are not this format. Read on 2026-11-17. Not observed in an Implementation Profile or on the testbed: no role uses this format yet.

It is also the principal media type (`df:primaryMediaType`), set on 2026-11-17 by an amendment classified substantive (`amendment-primary-media-type-2026-11-17`): the standard lists three media types, one per encoding, and `application/geo+json` is the one of the GeoJSON encoding this format describes; the two `application/ld+json` rows are the GeoJSON-LD encodings. It is also the media type RFC 7946 registers for GeoJSON.

## Requested by

No role requests it yet. Added on 2026-11-17 by decision of Gérald, with the representation `eo-product-eo-geojson`: the eo-product data type then has two representations, as a STAC Item and as EO GeoJSON.

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
