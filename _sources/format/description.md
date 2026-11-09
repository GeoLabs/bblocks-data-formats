The format item of the data-formats register, in JSON.

## Definition

A `df:Format` is a `rim:RegisterItem` of the `df:formatItemClass` item class. It is an encoding:

- it realizes no concept version (`realizes` is forbidden, by the schema and by `df:FormatShape`);
- it names its specification (`specification`, `dct:conformsTo`);
- it carries the media types under which it was observed (`observedMediaTypes`), each with where it
  was observed: `implementation-profile` (tier 3) or `testbed` (tier 4), and/or a JSON Schema
  fragment (`jsonSchemaFragment`), with the `parameters` a profile must supply to complete it.

No principal media type (`primaryMediaType`) is set on any format: none has been chosen.

A format is bound to a data type by a [representation](../representation/).

## Content of this block

- `schema.yaml`: a profile of `ogc.rim.schemas.register-item`.
