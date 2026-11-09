A password, as the OpenAPI `password` format: a hint to obscure the value.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/format/string-password` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [OpenAPI Specification 3.0.3, Data Types](https://spec.openapis.org/oas/v3.0.3#data-types) (`dct:conformsTo`)

## JSON Schema fragment

```json
{
  "type": "string",
  "format": "password"
}
```

## EOAP

Record `Password` of the EOAP `string_format.yaml`: "Represents a valid password."

This format is carried in CWL by that record, documented by the building block [`eoap.cct.string-format`](https://geolabs.github.io/bblocks-eoap-cct/bblock/eoap.cct.string-format) (`seeAlso` in `bblock.json`, `rdfs:seeAlso` and `df:cwlCustomType` in `ontology.ttl`).

It was registered in the data-types register as the data type `string-password`, a proposal. Its withdrawal from that register is pending (see the data-formats README).

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
