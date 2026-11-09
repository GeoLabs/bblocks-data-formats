The item classes of the data-formats register, as Registered Item Model **register item classes**, in JSON.

## Definition

Two item classes, both defined in the register (`definedIn`) and validated (`validatedBy`) by a shape
of the [shared vocabulary](../vocabulary/):

- `df:formatItemClass`, validated by `df:FormatShape`: an encoding, which realizes no concept version;
- `df:representationItemClass`, validated by `df:RepresentationShape`: one data type version of the
  data-types register, realized in one format.

Their titles and descriptions are in the vocabulary's `data.ttl`, which the SHACL closure of this
block includes.

## Sources

- [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
- [Registered Item Model](https://ogcincubator.github.io/registered-item-model/)
