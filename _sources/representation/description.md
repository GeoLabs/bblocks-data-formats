The representation item of the data-formats register, in JSON.

## Definition

A `df:Representation` is a `rim:RegisterItem` of the `df:representationItemClass` item class. It
realizes (`rim:realizes`) exactly one `dt:DataTypeVersion` of the data-types register and points
(`df:format`) to exactly one [format](../format/) of this register. `df:RepresentationShape` checks
both; the Registered Item Model already limits an item to one `rim:realizes`.

A representation is created when an existing role needs it: each one lists the Implementation
Profile roles that request it. In `bblock.json`, `isDescribedBy` names the data type block of the
data-types register; `hasFormat` will link the representations of a same data type once a data type
has more than one.

## Content of this block

- `schema.yaml`: a profile of `ogc.rim.schemas.register-item`.
- `context.jsonld`: the JSON-LD context of the items, inherited by every item block through its
  schema (the same context in the format and representation blocks).
