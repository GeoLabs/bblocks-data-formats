A GeoJSON FeatureCollection whose features are STAC Items, with optional links and counts, such as the response of a STAC API Item Search.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/format/stac-item-collection` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type; none is created until a role needs it.

## Specification

- [STAC API - ItemCollection Fragment 1.0.0](https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/fragments/itemcollection/README.md) (`dct:conformsTo`)
- [STAC API - Item Search 1.0.0](https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/item-search/README.md) and [STAC API - Features 1.0.0](https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/ogcapi-features/README.md), the sources of the media type (`dct:source`)

The JSON Schema fragment `$ref`s the schema STAC API 1.0.0 publishes for an ItemCollection: the OpenAPI 3.0 schema object itemCollection of the Item Search OpenAPI document. STAC publishes no JSON Schema document for it on schemas.stacspec.org: https://api.stacspec.org/v1.0.0/item-search/openapi.yaml#/components/schemas/itemCollection (checked on 2026-11-11, HTTP 200).

## Media type taken from the specification

`application/geo+json` (`df:inferredMediaType`, and `df:primaryMediaType`), two sources.

- [STAC API - Item Search 1.0.0](https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/item-search/README.md). Given by the STAC API - Item Search 1.0.0, section Endpoints, whose table gives "/search | Item Collection | application/geo+json | STAC API - Item Search | Search endpoint". Derived, not stated: neither the ItemCollection fragment nor the STAC specification 1.1.0 gives a media type for an Item Collection, unlike the Catalog, Collection and Item specifications (section Media Type for STAC ...). The fragment states that an ItemCollection must be a valid GeoJSON FeatureCollection, the media type of GeoJSON is application/geo+json (RFC 7946, section 12), and the STAC best practices 1.1.0 (section Working with Media Types) ask for as specific a media type as possible: if a file is a GeoJSON, not a JSON media type. Not observed in an Implementation Profile or on the testbed (measured on 2026-11-11, bblocks-process-profiles-tests-1 3d8c031): no process takes or returns a STAC Item Collection. Observed on 2026-11-11 where Item Collections are served, the Earth Search STAC API read by the KindGrove processes (https://earth-search.aws.element84.com/v1/search?collections=sentinel-2-l2a&limit=2): Content-Type application/geo+json; charset=utf-8.
- [STAC API - Features 1.0.0](https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/ogcapi-features/README.md). Given by the STAC API - Features 1.0.0, section Endpoints, whose table gives "/collections/{collectionId}/items | application/geo+json | ItemCollection | GeoJSON FeatureCollection-conformant entity of Item objects in collection". Derived, not stated, as for the Item Search source.

## Replaces

The data type `stac-item-collection` of the data-types register, a proposal withdrawn on 2026-11-11 (decision Q4, option b): this format carries `rim:supersedes` towards its item, `https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection/item`, which carries `dct:isReplacedBy` towards this format.

## Requested by

Added on 2026-11-11 by decision Q4, option b: the STAC types of data-types describe encodings and are withdrawn in favour of formats. No role uses it yet.

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
