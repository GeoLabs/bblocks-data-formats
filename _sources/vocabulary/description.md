The shared model of the data-formats register: the content plane of the OSPD data axis, as a
profile of the [Registered Item Model](https://ogcincubator.github.io/registered-item-model/).

## Model

| Class | Item class | Realizes | Carries |
|---|---|---|---|
| `df:Format` | `df:formatItemClass` | nothing | specification (`dct:conformsTo`), observed media types (`df:observedMediaType`), inferred media types (`df:inferredMediaType`, with source and justification) and/or a JSON Schema fragment (`df:jsonSchemaFragment`), parameters (`df:parameter`) |
| `df:Representation` | `df:representationItemClass` | one `dt:DataTypeVersion` of the data-types register | one format (`df:format`) |

Both are sub-classes of `rim:RegisterItem`, so `rim:RegisterItemShape` applies to every item. Every
item records its addition, proposed by GeoLabs, and is `rim:invalid` and `rim:published`: a proposal
awaiting a decision.

The meaning of data is not here: it is the concept plane of the
[data-types register](https://geolabs.github.io/bblocks-data-types/). This register depends on it
(`dependsOn: data-types.vocabulary`), so the data type versions a representation realizes are in the
SHACL closure; data-types never depends on this register.

## Content of this block

- `ontology.ttl`: classes and properties.
- `data.ttl`: the register, its owner and system, the two item classes, the register specification
  (`df:specification`) and the amendment action type (`df:amendmentAction`).
- `shapes.shacl`: `df:FormatShape`, `df:RepresentationShape`, `df:AdditionProposalShape`.
- `tests/`: Turtle items that must fail, one per rule.

## Sources

- [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
- [Registered Item Model](https://ogcincubator.github.io/registered-item-model/)
