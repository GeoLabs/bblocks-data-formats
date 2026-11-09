An email address, as JSON Schema `email`.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/format/string-email` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [JSON Schema Validation: A Vocabulary for Structural Validation of JSON (draft 2020-12), 7.3.2 Email Addresses](https://json-schema.org/draft/2020-12/json-schema-validation#section-7.3.2) (`dct:conformsTo`)

## JSON Schema fragment

```json
{
  "type": "string",
  "format": "email"
}
```

## EOAP

Record `Email` of the EOAP `string_format.yaml`: "Represents a valid e-mail address format."

It was registered in the data-types register as the data type `string-email`, a proposal. Its withdrawal from that register is pending (see the data-formats README).

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
