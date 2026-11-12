A bounding box as OGC API - Processes - Part 1: Core encodes it in JSON: `{"bbox": [4 or 6 numbers], "crs": ...}`.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version. The representation [`bounding-box-ogcapi-processes-bbox`](../../representation/bounding-box-ogcapi-processes-bbox/) binds it to the bounding-box data type.

## Specification

- [OGC 18-062r2 OGC API - Processes - Part 1: Core](https://docs.ogc.org/is/18-062r2/18-062r2.html) (`dct:conformsTo`), whose `bbox` schema is published as the building block `ogc.api.processes.part1.v1.schemas.bbox`.
- [OGC 17-069r4 OGC API - Features - Part 1: Core](https://docs.ogc.org/is/17-069r4/17-069r4.html), 7.15.3, defines the `bbox` parameter that schema cites (`dct:source`).

## JSON Schema fragment

`{"$ref": "https://geolabs.github.io/bblocks-ogcapi-processes/build/annotated/api/processes/v1/schemas/bbox/schema.json"}`: the `$ref` that the Implementation Profile `raster-crop` of `bblocks-generic-profiles` carried as the `schema` of its `areaOfInterest` input until 2026-11-09, moved here unchanged (decision D6).

No media type is observed: the testbed process `OTB.ExtractROI` takes the area as four numbers, not as this object.

## Inferred media type

`application/json` (`df:inferredMediaType`), inferred from the bbox JSON schema: a bbox value is a JSON
object. OGC 18-062r2 states no media type for it: Requirement 23
(`/req/core/process-execute-input-inline-bbox`, §7.11.2.2) only requires the `bbox.yaml` schema for an
inline value, and Recommendation 17 with Table 13 (§8.2) marks it with the JSON Schema `format` key
`ogc-bbox`. It is not an observation: no tier-3 profile declared it and the testbed does not serve it.
Added on 2026-11-09 as a `df:amendmentAction` classified clarifying.

## Requested by

Created on 2026-11-09 because one existing role needs it: `implementation-profile/raster-crop/inputs/areaOfInterest` of `bblocks-generic-profiles`, data type `bounding-box`.

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
