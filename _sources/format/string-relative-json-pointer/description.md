A relative JSON Pointer, as JSON Schema `relative-json-pointer`.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/format/string-relative-json-pointer` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [JSON Schema Validation: A Vocabulary for Structural Validation of JSON (draft 2020-12), 7.3.7 JSON Pointers](https://json-schema.org/draft/2020-12/json-schema-validation#section-7.3.7) (`dct:conformsTo`)

## JSON Schema fragment

```json
{
  "type": "string",
  "format": "relative-json-pointer"
}
```

## EOAP

Record `RelativeJsonPointer` of the EOAP `string_format.yaml`: "Represents a valid relative JSON pointer."

This format is carried in CWL by that record, documented by the building block [`eoap.cct.string-format`](https://geolabs.github.io/bblocks-eoap-cct/bblock/eoap.cct.string-format) (`seeAlso` in `bblock.json`, `rdfs:seeAlso` and `df:cwlCustomType` in `ontology.ttl`).

It was registered in the data-types register as the data type `string-relative-json-pointer`, a proposal, withdrawn on 2026-11-09. This format supersedes its item: `rim:supersedes <https://geolabs.github.io/bblocks-data-types/def/data-type/string-relative-json-pointer/item>`. The withdrawn item carries `dct:isReplacedBy` towards this format, unpublished by an action classified substantive. The link is carried here because data-formats depends on data-types, never the reverse.

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
