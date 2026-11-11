A JSON object describing a set of related STAC Items, with its license, its spatial and temporal extents and its links.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/format/stac-collection` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type; none is created until a role needs it.

## Specification

- [STAC Collection Specification 1.1.0](https://github.com/radiantearth/stac-spec/blob/v1.1.0/collection-spec/collection-spec.md) (`dct:conformsTo`)

The JSON Schema fragment `$ref`s the JSON Schema the specification publishes for a Collection: https://schemas.stacspec.org/v1.1.0/collection-spec/json-schema/collection.json (checked on 2026-11-11, HTTP 200).

The ogcincubator building block `ogc.contrib.stac.collection-v1-1-0` (STAC Collection (v1.1.0), `under-development`) publishes a schema that combines this one (`allOf`) with the constraints of its own block `ogc.contrib.stac.collection`; on 2026-11-11 both accepted the Collection example of STAC 1.1.0 (`examples/collection.json`) and rejected it without `extent`. It is cited as `seeAlso` (https://ogcincubator.github.io/bblocks-stac/build/generateddocs/markdown/contrib/stac/collection-v1-1-0/index.md), not imported: the register item, its statuses and its actions are this register's.

## Media type taken from the specification

`application/json` (`df:inferredMediaType`, and `df:primaryMediaType`), source [STAC Collection Specification 1.1.0](https://github.com/radiantearth/stac-spec/blob/v1.1.0/collection-spec/collection-spec.md). Stated by the STAC Collection Specification 1.1.0, section Media Type for STAC Collections: "A STAC Collection is a JSON file (RFC 8259), and thus should use the application/json as the Media Type (previously known as the MIME Type)." Not observed in an Implementation Profile or on the testbed (measured on 2026-11-11, bblocks-process-profiles-tests-1 3d8c031): no process takes or returns a STAC Collection.

## Replaces

The data type `stac-collection` of the data-types register, a proposal withdrawn on 2026-11-11 (decision Q4, option b): this format carries `rim:supersedes` towards its item, `https://geolabs.github.io/bblocks-data-types/def/data-type/stac-collection/item`, which carries `dct:isReplacedBy` towards this format.

## Requested by

Added on 2026-11-11 by decision Q4, option b: the STAC types of data-types describe encodings and are withdrawn in favour of formats. No role uses it yet.

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
