A JSON object that links STAC Items, Collections and child Catalogs into a browsable structure through its links.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/format/stac-catalog` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type; none is created until a role needs it.

## Specification

- [STAC Catalog Specification 1.1.0](https://github.com/radiantearth/stac-spec/blob/v1.1.0/catalog-spec/catalog-spec.md) (`dct:conformsTo`)

The JSON Schema fragment `$ref`s the JSON Schema the specification publishes for a Catalog: https://schemas.stacspec.org/v1.1.0/catalog-spec/json-schema/catalog.json (checked on 2026-11-11, HTTP 200).

## Media type taken from the specification

`application/json` (`df:inferredMediaType`, and `df:primaryMediaType`), source [STAC Catalog Specification 1.1.0](https://github.com/radiantearth/stac-spec/blob/v1.1.0/catalog-spec/catalog-spec.md). Stated by the STAC Catalog Specification 1.1.0, section Media Type for STAC Catalogs: "A STAC Catalog is a JSON file (RFC 8259), and thus should use the application/json as the Media Type (previously known as the MIME Type)." Not observed in an Implementation Profile or on the testbed (measured on 2026-11-11, bblocks-process-profiles-tests-1 3d8c031): the six testbed outputs that return a STAC Catalog (kindgrove.mangrove result, kindgrove.mangrove-workflow stac, kindgrove-steps.mangrove-workflow-steps stac, kindgrove-steps.export-stac stac_catalog, water-bodies.stac stac_catalog, water-bodies.water-bodies stac) declare a JSON object schema with format stac-catalog and no media type.

## Replaces

The data type `stac-catalog` of the data-types register, a proposal withdrawn on 2026-11-11 (decision Q4, option b): this format carries `rim:supersedes` towards its item, `https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog/item`, which carries `dct:isReplacedBy` towards this format.

## Requested by

Added on 2026-11-11 by decision Q4, option b: the STAC types of data-types describe encodings and are withdrawn in favour of formats. No role uses it yet.

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
