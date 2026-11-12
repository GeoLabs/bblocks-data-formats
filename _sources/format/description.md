The format item of the data-formats register, in JSON.

## Definition

A `df:Format` is a `rim:RegisterItem` of the `df:formatItemClass` item class. It is an encoding:

- it realizes no concept version (`realizes` is forbidden, by the schema and by `df:FormatShape`);
- it names its specification (`specification`, `dct:conformsTo`);
- it carries the media types under which it was observed (`observedMediaTypes`), each with where it
  was observed: `implementation-profile` (tier 3) or `testbed` (tier 4), and/or a JSON Schema
  fragment (`jsonSchemaFragment`), with the `parameters` a profile must supply to complete it;
- it may carry media types that were not observed but inferred (`inferredMediaTypes`,
  `df:inferredMediaType`), each with its source (`dct:source`) and justification
  (`dct:description`), checked by `df:MediaTypeInferenceShape`.

A principal media type (`primaryMediaType`, `df:primaryMediaType`) is set only where a specification states the media type: the four STAC formats (`stac-item`, `stac-item-collection`, `stac-collection`, `stac-catalog`). It is one of the format's recorded media types, checked by `df:PrimaryMediaTypeShape`. None is set on the other formats: none has been chosen.

A format is bound to a data type by a [representation](../representation/).

## Content of this block

- `schema.yaml`: a profile of `ogc.rim.schemas.register-item`.
- `context.jsonld`: the JSON-LD context of the items, inherited by every item block through its
  schema (the same context in the format and representation blocks).
