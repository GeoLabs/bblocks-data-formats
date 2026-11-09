The data-formats register as a Registered Item Model **register**, in JSON.

## Definition

A profile of the RIM `register` schema: the governed collection of formats and representations,
distinct from the register system it runs on (`runsOn`) and from the roles that govern it. Its
title, description and item classes are declared in the `data.ttl` of the
[shared vocabulary](../vocabulary/), which the SHACL closure of this block includes.

## Register specification

`df:specification` is a `rim:RegisterSpecification`. It records:

- the register type: a content register, as the Registered Item Model uses the term;
- the roles: GeoLabs SARL is owner, manager and, for now, control body, with the written intention
  to delegate the control body role to the OGC or to an OSPD working group;
- the `rim:realizes` link with the data-types register: a representation realizes at most one
  `dt:DataTypeVersion`; this register depends on data-types, never the reverse;
- the definition of a substantive change (`rim:definesSubstantiveChange`), the table of substantive
  and clarifying changes for formats and representations, the version rule and the rule for
  proposals;
- `df:amendmentAction`, the action type of an in-place change to a proposal;
- that no eligibility criteria and no commitments have been set.

## Sources

- [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
- [Registered Item Model](https://ogcincubator.github.io/registered-item-model/)
