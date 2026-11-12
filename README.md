# bblocks-data-formats

OGC Building Blocks register holding the **content plane** of the OSPD data axis: the formats in
which process inputs and outputs are encoded, and the representations that bind a data type to a
format. It is a profile of the
[Registered Item Model](https://ogcincubator.github.io/registered-item-model/) (RIM, ISO 19135:2026).
Identifier prefix: `data-formats.`; namespace `https://w3id.org/geolabs/ospd/data-formats/`, prefix
`df:`. The namespace is not resolved yet.

The meaning of data is not here: it is the concept plane held by
[`GeoLabs/bblocks-data-types`](https://github.com/GeoLabs/bblocks-data-types). This register depends
on it (`dependsOn: data-types.vocabulary`); data-types never depends on this register.

## Model

| Class | Item class | Realizes | Carries |
|---|---|---|---|
| `df:Format` | `df:formatItemClass` | nothing | its specification (`dct:conformsTo`), the media types observed where it is served, each with where (`implementation-profile` or `testbed`), and/or a JSON Schema fragment, with its parameters; media types inferred rather than observed (`df:inferredMediaType`), each with its source and justification |
| `df:Representation` | `df:representationItemClass` | exactly one `dt:DataTypeVersion` of data-types | one format (`df:format`) |

Both are sub-classes of `rim:RegisterItem`. Every item is a proposal: an addition by GeoLabs,
`rim:invalid` and `rim:published`. A principal media type is set only on the four STAC formats, where
the STAC specification states it; none has been chosen for the other formats. A representation is created when an existing role needs it, and lists the roles that do.

## Register specification

`df:specification` (in [`_sources/vocabulary/data.ttl`](_sources/vocabulary/data.ttl)) is the
`rim:RegisterSpecification` of the register: a content register, GeoLabs SARL as owner, manager and,
for now, control body, with the intention to delegate that role to the OGC or to an OSPD working
group. It holds the definition of a substantive change, the table of substantive and clarifying
changes for formats and representations, the version rule, the rule for proposals and
`df:amendmentAction`, the action type of an in-place change to a proposal, and the rule for an item
that replaces a data type (`rim:supersedes`). No eligibility criteria and no commitments are set.

## Building blocks

| Identifier | Content |
|---|---|
| `data-formats.vocabulary` | Ontology, register metadata and specification, shapes, tests (support block) |
| `data-formats.register` | The register, in JSON; profile of the RIM `register` schema |
| `data-formats.item-class` | The two item classes, in JSON; profile of the RIM `register-item-class` schema |
| `data-formats.format` | The format item schema and JSON-LD context; profile of the RIM `register-item` schema |
| `data-formats.format.<name>` | One format: `geotiff`, `gml`, `las`, `geojson`, `ogcapi-processes-bbox`, `png`, `stac-item`, `stac-item-collection`, `stac-collection`, `stac-catalog`, and the 20 EOAP string formats `string-*` |
| `data-formats.representation` | The representation item schema and JSON-LD context; profile of the RIM `register-item` schema |
| `data-formats.representation.<name>` | One representation: `geometry-gml`, `surface-gml`, `point-gml`, `feature-collection-gml`, `raster-geotiff`, `raster-single-band-geotiff`, `elevation-model-geotiff`, `point-cloud-las`, `bounding-box-ogcapi-processes-bbox`, `geometry-geojson`, `eo-product-stac-item`, `rendered-image-png` |

### Formats

| Format | Specification | Observed media types |
|---|---|---|
| `geotiff` | OGC GeoTIFF Standard (version not stated where served) | `image/tiff` (tier 3, testbed), `image/tiff; application=geotiff` (testbed) |
| `gml` | OGC GML Encoding Standard (version not established) | `text/xml` (tier 3, testbed) |
| `las` | OGC 17-030r1 LAS 1.4 | `application/vnd.las` (tier 3), `application/x-ogc-lasf` (testbed) |
| `geojson` | RFC 7946 | `application/geo+json` (testbed) |
| `ogcapi-processes-bbox` | OGC 18-062r2 OGC API - Processes - Part 1: Core (`bbox` schema) | none observed; `application/json` inferred from the bbox JSON schema (OGC 18-062r2 states none); a JSON Schema fragment, the `$ref` to `ogc.api.processes.part1.v1.schemas.bbox` that tier 3 carried (added 2026-11-09) |
| `png` | W3C PNG Specification (Third Edition) | `image/png` (testbed: `algae-bloom.plot-image`, added 2026-11-10) |
| `stac-item` | STAC Item Specification 1.1.0 | none observed in a profile or on the testbed; `application/geo+json` inferred from the specification, which states it, and seen where the Earth Search STAC API serves the Items (added 2026-11-10); principal media type |
| `stac-item-collection` | STAC API - ItemCollection Fragment 1.0.0 | none observed in a profile or on the testbed; `application/geo+json`, stated by STAC API - Item Search 1.0.0 (Endpoints) and seen on the Earth Search `/search` endpoint; principal media type (added 2026-11-11) |
| `stac-collection` | STAC Collection Specification 1.1.0 | none observed; `application/json`, stated by the specification; principal media type (added 2026-11-11) |
| `stac-catalog` | STAC Catalog Specification 1.1.0 | none observed (six testbed outputs return a Catalog as a JSON object schema with no media type); `application/json`, stated by the specification; principal media type (added 2026-11-11) |
| `string-*` (19) | JSON Schema Validation 2020-12, 7.3 (`password`: OpenAPI 3.0.3 data types) | none: a JSON Schema fragment `{"type": "string", "format": ...}` |
| `string-pattern` | JSON Schema Validation 2020-12, 6.3.3 `pattern` | none: fragment `{"type": "string"}`, parameter `pattern` |

The media types were measured on 2026-11-09 in the Implementation Profiles of
`bblocks-generic-profiles` (tier 3) and in the testbed process descriptions of
`bblocks-process-profiles` (tier 4). The 20 `string-*` formats are the records of the EOAP
[`string_format.yaml`](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml), kept
whether or not a process uses them; each declares its relation to the
[`eoap.cct.string-format`](https://geolabs.github.io/bblocks-eoap-cct/bblock/eoap.cct.string-format)
building block (`seeAlso`, `rdfs:seeAlso`) and the name of its CWL record (`df:cwlCustomType`).

19 of them were registered in data-types as the data types `string-*`, as proposals, and were
withdrawn on 2026-11-09. Each of these 19 formats carries `rim:supersedes` towards the withdrawn item
(`https://geolabs.github.io/bblocks-data-types/def/data-type/string-<name>/item`), which this register
types through its dependency on data-types; the withdrawn item is unpublished, by an action
classified substantive, and carries `dct:isReplacedBy` towards the format. The link is carried here
because `rim:RegisterItemShape` rejects a `rim:supersededBy` towards an item data-types does not type,
and data-types never depends on this register. Which way `rim:supersedes` points is read from its
label; the question is asked to the model maintainers.

The four STAC formats replace, in the same way, the four STAC data types of data-types (`stac-item`,
`stac-item-collection`, `stac-collection`, `stac-catalog`), proposals withdrawn on 2026-11-11
(decision Q4, option b): each format carries `rim:supersedes` towards
`https://geolabs.github.io/bblocks-data-types/def/data-type/stac-<name>/item` (for `stac-item`, by an
amendment classified clarifying). Their JSON Schema fragments `$ref` the schemas the STAC
specifications publish (`schemas.stacspec.org` v1.1.0 for Item, Collection and Catalog; for the Item
Collection, which has no JSON Schema there, the `itemCollection` schema object of the STAC API 1.0.0
Item Search OpenAPI document). The ogcincubator `bblocks-stac` blocks `ogc.contrib.stac.item-v1-1-0`
and `ogc.contrib.stac.collection-v1-1-0` are cited as `seeAlso` by URL, not imported: they combine
those schemas with their own constraints, and the register items, statuses and actions stay here.
bblocks-stac has no Catalog and no Item Collection block.

## Building locally

The register imports the published data-types register. Until it is published with the same
content, map it to a local build in `bblocks-config-local.yml` (ignored by git):

```yaml
url-mappings:
  https://geolabs.github.io/bblocks-data-types/build/: /ext/dt/build-local/
  https://geolabs.github.io/bblocks-data-types/: /ext/dt/
```

and mount that build into the container (`-v <data-types copy>:/ext/dt`). Build data-types first.

```bash
./build.sh   # process and validate (Docker); output in build-local/
./view.sh    # preview at http://localhost:9090
```

`bblocks-config.yaml` keeps the published URLs.

## License

Apache-2.0.
