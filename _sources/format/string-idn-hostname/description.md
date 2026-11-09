An internationalized Internet host name, as JSON Schema `idn-hostname`.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/format/string-idn-hostname` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [JSON Schema Validation: A Vocabulary for Structural Validation of JSON (draft 2020-12), 7.3.3 Hostnames](https://json-schema.org/draft/2020-12/json-schema-validation#section-7.3.3) (`dct:conformsTo`)

## JSON Schema fragment

```json
{
  "type": "string",
  "format": "idn-hostname"
}
```

## EOAP

Record `IDNHostname` of the EOAP `string_format.yaml`: "Represents a valid IDN hostname."

It was registered in the data-types register as the data type `string-idn-hostname`, a proposal. Its withdrawal from that register is pending (see the data-formats README).

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
