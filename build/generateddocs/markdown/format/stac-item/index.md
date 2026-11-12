
# Format: STAC Item (Schema)

`data-formats.format.stac-item` *v0.1*

A GeoJSON Feature describing one spatiotemporal item, such as an Earth observation product, with its links and its assets.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A GeoJSON Feature describing one spatiotemporal item, such as an Earth observation product, with its links and its assets.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/format/stac-item` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [STAC Item Specification 1.1.0](https://github.com/radiantearth/stac-spec/blob/v1.1.0/item-spec/item-spec.md) (`dct:conformsTo`)

The JSON Schema fragment `$ref`s the JSON Schema the specification publishes for an Item, https://schemas.stacspec.org/v1.1.0/item-spec/json-schema/item.json (read on 2026-11-10). Version 1.1.0 is the version of the STAC Items observed in the KindGrove run (`scene_item.json`, `stac_version` 1.1.0).

## Observed media types

No media type observed in an Implementation Profile or on the testbed (measured on 2026-11-10, `bblocks-process-profiles-tests-1` `ea01115`). The media type is taken from the specification, with its source and justification (`df:inferredMediaType`).

## Principal media type

`application/geo+json` (`df:primaryMediaType`), the media type the specification states, set on 2026-11-10 by an amendment of the proposal classified substantive: this register's table lists the principal media type among the substantive changes.

## Media type taken from the specification

`application/geo+json`, source [STAC Item Specification 1.1.0](https://github.com/radiantearth/stac-spec/blob/v1.1.0/item-spec/item-spec.md). Stated by the STAC Item Specification 1.1.0, section Media Type for STAC Item: a STAC Item is a GeoJSON file and should use application/geo+json. Not observed in an Implementation Profile or on the testbed. Of the processes of bblocks-process-profiles that exchange STAC Items, kindgrove-steps.select-scene and kindgrove-steps.download-band serve application/geo+json since their CWL declares it (GeoLabs/KindGrove 89e3d36, 2026-11-10, released in v0.0.2-rc3 on 2026-11-11; until then their CWL declared no format and they served application/octet-stream), and the others pass the Item by URL. Observed on 2026-11-10 where the Items are served, the Earth Search STAC API read by those processes (https://earth-search.aws.element84.com/v1, items S2C_46PGC_20260913_0_L2A and S2A_29SPC_20190701_0_L2A of sentinel-2-l2a): Content-Type application/geo+json; charset=utf-8.

## Replaces

The data type `stac-item` of the data-types register, a proposal withdrawn on 2026-11-11 (decision Q4, option b): this format carries `rim:supersedes` towards its item, `https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item/item`, which carries `dct:isReplacedBy` towards this format. Recorded by an amendment of the proposal classified clarifying (`https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-supersedes-2026-11-11`).

## Related building block

The ogcincubator building block `ogc.contrib.stac.item-v1-1-0` (STAC Item (v1.1.0), `under-development`) publishes a schema that combines the same STAC Item 1.1.0 JSON Schema (`allOf`) with the constraints of the building blocks ogc.geo.features.feature and ogc.api.records.v1.schemas.recordGeoJSON and its own block `ogc.contrib.stac.item`; on 2026-11-11 both accepted the three Item examples of STAC 1.1.0 (`simple-item`, `core-item`, `extended-item`) and rejected one without `assets`. It is cited as `seeAlso` (https://ogcincubator.github.io/bblocks-stac/build/generateddocs/markdown/contrib/stac/item-v1-1-0/index.md), not imported, and the fragment keeps the specification's own schema: the register item, its statuses and its actions are this register's.

## Requested by

Added on 2026-11-10 for the representation [`eo-product-stac-item`](../../representation/eo-product-stac-item/), needed by the new process profiles of `bblocks-generic-profiles` (branch `planes/new-profiles`).

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.

## Examples

### STAC Item
The register item of the STAC Item format, of the register's format item class.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://github.com/radiantearth/stac-spec/blob/v1.1.0/item-spec/item-spec.md",
      "title": "STAC Item Specification 1.1.0"
    }
  ],
  "primaryMediaType": "application/geo+json",
  "supersedes": "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item/item",
  "seeAlso": "https://ogcincubator.github.io/bblocks-stac/build/generateddocs/markdown/contrib/stac/item-v1-1-0/index.md",
  "jsonSchemaFragment": {
    "$ref": "https://schemas.stacspec.org/v1.1.0/item-spec/json-schema/item.json"
  },
  "inferredMediaTypes": [
    {
      "mediaType": "application/geo+json",
      "source": "https://github.com/radiantearth/stac-spec/blob/v1.1.0/item-spec/item-spec.md",
      "description": "Stated by the STAC Item Specification 1.1.0, section Media Type for STAC Item: a STAC Item is a GeoJSON file and should use application/geo+json. Not observed in an Implementation Profile or on the testbed. Of the processes of bblocks-process-profiles that exchange STAC Items, kindgrove-steps.select-scene and kindgrove-steps.download-band serve application/geo+json since their CWL declares it (GeoLabs/KindGrove 89e3d36, 2026-11-10, released in v0.0.2-rc3 on 2026-11-11; until then their CWL declared no format and they served application/octet-stream), and the others pass the Item by URL. Observed on 2026-11-10 where the Items are served, the Earth Search STAC API read by those processes (https://earth-search.aws.element84.com/v1, items S2C_46PGC_20260913_0_L2A and S2A_29SPC_20190701_0_L2A of sentinel-2-l2a): Content-Type application/geo+json; charset=utf-8."
    }
  ],
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": [
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
      "startedAtTime": "2026-11-10T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-primary-media-type",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "substantive",
      "description": "Principal media type set to application/geo+json, the media type the STAC Item Specification 1.1.0 states (section Media Type for STAC Item), already recorded with that source as df:inferredMediaType. Decision of 2026-11-10. Classified substantive: the validated table of this register lists the principal media type among the substantive changes; the item is a proposal, amended in place.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
      "startedAtTime": "2026-11-10T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-observation-2026-11-11",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "The justification of the media type taken from the specification (df:inferredMediaType) is brought up to date: kindgrove-steps.select-scene and kindgrove-steps.download-band now serve application/geo+json, their CWL declaring it (GeoLabs/KindGrove 10887a4), where it said they served application/octet-stream. The media types and the principal media type are unchanged. Classified clarifying: a reworded justification.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
      "startedAtTime": "2026-11-11T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-supersedes-2026-11-11",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "The format records that it replaces the data type stac-item of the data-types register, withdrawn on 2026-11-11 (decision Q4, option b): rim:supersedes towards https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item/item, which carries dct:isReplacedBy towards this format. It also cites the ogcincubator building block ogc.contrib.stac.item-v1-1-0 (rdfs:seeAlso), whose schema combines the STAC Item 1.1.0 JSON Schema with the constraints of the building blocks ogc.geo.features.feature and ogc.api.records.v1.schemas.recordGeoJSON. The media types, the principal media type, the specification and the JSON Schema fragment are unchanged. Classified clarifying: a relation and a link are added, and what the format is does not change.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
      "startedAtTime": "2026-11-11T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-kindgrove-release-2026-11-12",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "The justification of the media type taken from the specification (df:inferredMediaType) cites the commit of GeoLabs/KindGrove that makes kindgrove-steps.select-scene and kindgrove-steps.download-band declare application/geo+json as it was published: 89e3d36, released in v0.0.2-rc3 on 2026-11-11, instead of 10887a4, said not released, a commit that is not public (checked on 2026-11-12: https://github.com/GeoLabs/KindGrove/commit/10887a4 HTTP 404, https://github.com/GeoLabs/KindGrove/commit/89e3d36 HTTP 200, 89e3d36 an ancestor of the tag v0.0.2-rc3). The action amendment-observation-2026-11-11, which cites 10887a4, stays as recorded. Decision of Gérald, 2026-11-12. The media types and the principal media type are unchanged. Classified clarifying: a reference in a justification is corrected.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
      "startedAtTime": "2026-11-12T00:00:00Z"
    }
  ]
}

```

#### turtle
```turtle
@prefix df:   <https://w3id.org/geolabs/ospd/data-formats/> .
@prefix dt:   <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim:  <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct:  <http://purl.org/dc/terms/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix rdf:  <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix xsd:  <http://www.w3.org/2001/XMLSchema#> .
@prefix prov: <http://www.w3.org/ns/prov#> .

<https://w3id.org/geolabs/ospd/data-formats/format/stac-item> a df:Format, rim:RegisterItem ;
    dct:title "STAC Item"@en ;
    dct:description "A GeoJSON Feature describing one spatiotemporal item, such as an Earth observation product, with its links and its assets."@en ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/format/stac-item"^^xsd:anyURI ;
    rim:itemClass df:formatItemClass ;
    rim:inRegister df:register ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/addition> ,
        <https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-primary-media-type> ,
        <https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-observation-2026-11-11> ,
        <https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-supersedes-2026-11-11> ,
        <https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-kindgrove-release-2026-11-12> ;
    dct:conformsTo <https://github.com/radiantearth/stac-spec/blob/v1.1.0/item-spec/item-spec.md> ;
    df:primaryMediaType "application/geo+json" ;
    rim:supersedes <https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item/item> ;
    rdfs:seeAlso <https://ogcincubator.github.io/bblocks-stac/build/generateddocs/markdown/contrib/stac/item-v1-1-0/index.md> ;
    df:jsonSchemaFragment "{\"$ref\":\"https://schemas.stacspec.org/v1.1.0/item-spec/json-schema/item.json\"}"^^rdf:JSON ;
    df:inferredMediaType [ df:mediaType "application/geo+json" ;
        dct:source <https://github.com/radiantearth/stac-spec/blob/v1.1.0/item-spec/item-spec.md> ;
        dct:description "Stated by the STAC Item Specification 1.1.0, section Media Type for STAC Item: a STAC Item is a GeoJSON file and should use application/geo+json. Not observed in an Implementation Profile or on the testbed. Of the processes of bblocks-process-profiles that exchange STAC Items, kindgrove-steps.select-scene and kindgrove-steps.download-band serve application/geo+json since their CWL declares it (GeoLabs/KindGrove 89e3d36, 2026-11-10, released in v0.0.2-rc3 on 2026-11-11; until then their CWL declared no format and they served application/octet-stream), and the others pass the Item by URL. Observed on 2026-11-10 where the Items are served, the Earth Search STAC API read by those processes (https://earth-search.aws.element84.com/v1, items S2C_46PGC_20260913_0_L2A and S2A_29SPC_20190701_0_L2A of sentinel-2-l2a): Content-Type application/geo+json; charset=utf-8."@en ] .

<https://github.com/radiantearth/stac-spec/blob/v1.1.0/item-spec/item-spec.md> dct:title "STAC Item Specification 1.1.0" .

<https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/stac-item> ;
    prov:startedAtTime "2026-11-10T00:00:00Z"^^xsd:dateTime .

<https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-primary-media-type> a rim:RegisterAction ;
    rim:actionType df:amendmentAction ;
    rim:changeClassification rim:substantiveChange ;
    rim:affectedProperty df:primaryMediaType ;
    dct:description "Principal media type set to application/geo+json, the media type the STAC Item Specification 1.1.0 states (section Media Type for STAC Item), already recorded with that source as df:inferredMediaType. Decision of 2026-11-10. Classified substantive: the validated table of this register lists the principal media type among the substantive changes; the item is a proposal, amended in place."@en ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/stac-item> ;
    prov:startedAtTime "2026-11-10T00:00:00Z"^^xsd:dateTime .

<https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-observation-2026-11-11> a rim:RegisterAction ;
    rim:actionType df:amendmentAction ;
    rim:changeClassification rim:clarifyingChange ;
    rim:affectedProperty df:inferredMediaType ;
    dct:description "The justification of the media type taken from the specification (df:inferredMediaType) is brought up to date: kindgrove-steps.select-scene and kindgrove-steps.download-band now serve application/geo+json, their CWL declaring it (GeoLabs/KindGrove 10887a4), where it said they served application/octet-stream. The media types and the principal media type are unchanged. Classified clarifying: a reworded justification."@en ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/stac-item> ;
    prov:startedAtTime "2026-11-11T00:00:00Z"^^xsd:dateTime .

<https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-supersedes-2026-11-11> a rim:RegisterAction ;
    rim:actionType df:amendmentAction ;
    rim:changeClassification rim:clarifyingChange ;
    rim:affectedProperty rim:supersedes , rdfs:seeAlso ;
    dct:description "The format records that it replaces the data type stac-item of the data-types register, withdrawn on 2026-11-11 (decision Q4, option b): rim:supersedes towards https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item/item, which carries dct:isReplacedBy towards this format. It also cites the ogcincubator building block ogc.contrib.stac.item-v1-1-0 (rdfs:seeAlso), whose schema combines the STAC Item 1.1.0 JSON Schema with the constraints of the building blocks ogc.geo.features.feature and ogc.api.records.v1.schemas.recordGeoJSON. The media types, the principal media type, the specification and the JSON Schema fragment are unchanged. Classified clarifying: a relation and a link are added, and what the format is does not change."@en ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/stac-item> ;
    prov:startedAtTime "2026-11-11T00:00:00Z"^^xsd:dateTime .

<https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-kindgrove-release-2026-11-12> a rim:RegisterAction ;
    rim:actionType df:amendmentAction ;
    rim:changeClassification rim:clarifyingChange ;
    rim:affectedProperty df:inferredMediaType ;
    dct:description "The justification of the media type taken from the specification (df:inferredMediaType) cites the commit of GeoLabs/KindGrove that makes kindgrove-steps.select-scene and kindgrove-steps.download-band declare application/geo+json as it was published: 89e3d36, released in v0.0.2-rc3 on 2026-11-11, instead of 10887a4, said not released, a commit that is not public (checked on 2026-11-12: https://github.com/GeoLabs/KindGrove/commit/10887a4 HTTP 404, https://github.com/GeoLabs/KindGrove/commit/89e3d36 HTTP 200, 89e3d36 an ancestor of the tag v0.0.2-rc3). The action amendment-observation-2026-11-11, which cites 10887a4, stays as recorded. Decision of Gérald, 2026-11-12. The media types and the principal media type are unchanged. Classified clarifying: a reference in a justification is corrected."@en ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/stac-item> ;
    prov:startedAtTime "2026-11-12T00:00:00Z"^^xsd:dateTime .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-formats/build/annotated/format/stac-item/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://github.com/radiantearth/stac-spec/blob/v1.1.0/item-spec/item-spec.md",
      "title": "STAC Item Specification 1.1.0"
    }
  ],
  "primaryMediaType": "application/geo+json",
  "supersedes": "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item/item",
  "seeAlso": "https://ogcincubator.github.io/bblocks-stac/build/generateddocs/markdown/contrib/stac/item-v1-1-0/index.md",
  "jsonSchemaFragment": {
    "$ref": "https://schemas.stacspec.org/v1.1.0/item-spec/json-schema/item.json"
  },
  "inferredMediaTypes": [
    {
      "mediaType": "application/geo+json",
      "source": "https://github.com/radiantearth/stac-spec/blob/v1.1.0/item-spec/item-spec.md",
      "description": "Stated by the STAC Item Specification 1.1.0, section Media Type for STAC Item: a STAC Item is a GeoJSON file and should use application/geo+json. Not observed in an Implementation Profile or on the testbed. Of the processes of bblocks-process-profiles that exchange STAC Items, kindgrove-steps.select-scene and kindgrove-steps.download-band serve application/geo+json since their CWL declares it (GeoLabs/KindGrove 89e3d36, 2026-11-10, released in v0.0.2-rc3 on 2026-11-11; until then their CWL declared no format and they served application/octet-stream), and the others pass the Item by URL. Observed on 2026-11-10 where the Items are served, the Earth Search STAC API read by those processes (https://earth-search.aws.element84.com/v1, items S2C_46PGC_20260913_0_L2A and S2A_29SPC_20190701_0_L2A of sentinel-2-l2a): Content-Type application/geo+json; charset=utf-8."
    }
  ],
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": [
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
      "startedAtTime": "2026-11-10T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-primary-media-type",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "substantive",
      "description": "Principal media type set to application/geo+json, the media type the STAC Item Specification 1.1.0 states (section Media Type for STAC Item), already recorded with that source as df:inferredMediaType. Decision of 2026-11-10. Classified substantive: the validated table of this register lists the principal media type among the substantive changes; the item is a proposal, amended in place.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
      "startedAtTime": "2026-11-10T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-observation-2026-11-11",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "The justification of the media type taken from the specification (df:inferredMediaType) is brought up to date: kindgrove-steps.select-scene and kindgrove-steps.download-band now serve application/geo+json, their CWL declaring it (GeoLabs/KindGrove 10887a4), where it said they served application/octet-stream. The media types and the principal media type are unchanged. Classified clarifying: a reworded justification.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
      "startedAtTime": "2026-11-11T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-supersedes-2026-11-11",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "The format records that it replaces the data type stac-item of the data-types register, withdrawn on 2026-11-11 (decision Q4, option b): rim:supersedes towards https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item/item, which carries dct:isReplacedBy towards this format. It also cites the ogcincubator building block ogc.contrib.stac.item-v1-1-0 (rdfs:seeAlso), whose schema combines the STAC Item 1.1.0 JSON Schema with the constraints of the building blocks ogc.geo.features.feature and ogc.api.records.v1.schemas.recordGeoJSON. The media types, the principal media type, the specification and the JSON Schema fragment are unchanged. Classified clarifying: a relation and a link are added, and what the format is does not change.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
      "startedAtTime": "2026-11-11T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item/actions/amendment-kindgrove-release-2026-11-12",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "The justification of the media type taken from the specification (df:inferredMediaType) cites the commit of GeoLabs/KindGrove that makes kindgrove-steps.select-scene and kindgrove-steps.download-band declare application/geo+json as it was published: 89e3d36, released in v0.0.2-rc3 on 2026-11-11, instead of 10887a4, said not released, a commit that is not public (checked on 2026-11-12: https://github.com/GeoLabs/KindGrove/commit/10887a4 HTTP 404, https://github.com/GeoLabs/KindGrove/commit/89e3d36 HTTP 200, 89e3d36 an ancestor of the tag v0.0.2-rc3). The action amendment-observation-2026-11-11, which cites 10887a4, stays as recorded. Decision of G\u00e9rald, 2026-11-12. The media types and the principal media type are unchanged. Classified clarifying: a reference in a justification is corrected.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item",
      "startedAtTime": "2026-11-12T00:00:00Z"
    }
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Format item - STAC Item
description: The register item of the STAC Item format, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-formats/build/annotated/format/schema.yaml
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-formats/format/stac-item
x-bblocks-metadata:
  itemIdentifier: data-formats.format.stac-item
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-10'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/stac-item/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/stac-item/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "Register": "rim:Register",
    "RegisterSystem": "rim:RegisterSystem",
    "RegisterSpecification": "rim:RegisterSpecification",
    "RegisterItemClass": "rim:RegisterItemClass",
    "RegisterItem": "rim:RegisterItem",
    "RegisterAction": "rim:RegisterAction",
    "Concept": "rim:Concept",
    "ConceptVersion": "rim:ConceptVersion",
    "ConceptSystem": "rim:ConceptSystem",
    "Commitment": "rim:Commitment",
    "Agent": "prov:Agent",
    "Organization": "prov:Organization",
    "Person": "prov:Person",
    "label": "rdfs:label",
    "prefLabel": "skos:prefLabel",
    "definition": "skos:definition",
    "inScheme": {
      "@id": "skos:inScheme",
      "@type": "@id"
    },
    "runsOn": {
      "@id": "rim:runsOn",
      "@type": "@id"
    },
    "hasSpecification": {
      "@id": "rim:hasSpecification",
      "@type": "@id"
    },
    "definesSubstantiveChange": "rim:definesSubstantiveChange",
    "registerOwner": {
      "@id": "rim:registerOwner",
      "@type": "@id"
    },
    "registerManager": {
      "@id": "rim:registerManager",
      "@type": "@id"
    },
    "controlBody": {
      "@id": "rim:controlBody",
      "@type": "@id"
    },
    "registerSystemManager": {
      "@id": "rim:registerSystemManager",
      "@type": "@id"
    },
    "registerUser": {
      "@id": "rim:registerUser",
      "@type": "@id"
    },
    "hasCommitment": {
      "@id": "rim:hasCommitment",
      "@type": "@id"
    },
    "commitmentCategory": {
      "@id": "rim:commitmentCategory",
      "@type": "@vocab"
    },
    "access": "rim:accessCommitment",
    "persistence": "rim:persistenceCommitment",
    "transparency": "rim:transparencyCommitment",
    "definedIn": {
      "@id": "rim:definedIn",
      "@type": "@id"
    },
    "validatedBy": {
      "@id": "rim:validatedBy",
      "@type": "@id"
    },
    "versionOf": {
      "@id": "rim:versionOf",
      "@type": "@id"
    },
    "version": "rim:version",
    "valid": "rim:valid",
    "invalid": "rim:invalid",
    "published": "rim:published",
    "unpublished": "rim:unpublished",
    "appliesTo": {
      "@id": "rim:appliesTo",
      "@type": "@id"
    },
    "proposer": {
      "@id": "rim:proposer",
      "@type": "@id"
    },
    "actionType": {
      "@id": "rim:actionType",
      "@type": "@vocab"
    },
    "addition": "rim:additionAction",
    "publish": "rim:publishAction",
    "unpublish": "rim:unpublishAction",
    "invalidation": "rim:invalidationAction",
    "supersession": "rim:supersessionAction",
    "redaction": "rim:redactionAction",
    "deletion": "rim:deletionAction",
    "changeClassification": {
      "@id": "rim:changeClassification",
      "@type": "@vocab"
    },
    "substantive": "rim:substantiveChange",
    "clarifying": "rim:clarifyingChange",
    "correctional": "rim:correctionalChange",
    "startedAtTime": {
      "@id": "prov:startedAtTime",
      "@type": "xsd:dateTime"
    },
    "endedAtTime": {
      "@id": "prov:endedAtTime",
      "@type": "xsd:dateTime"
    },
    "wasAssociatedWith": {
      "@id": "prov:wasAssociatedWith",
      "@type": "@id"
    },
    "id": "@id",
    "type": "@type",
    "objectIdentifier": {
      "@id": "rim:objectIdentifier",
      "@type": "xsd:anyURI"
    },
    "functionalIdentifier": {
      "@id": "rim:functionalIdentifier",
      "@type": "xsd:anyURI"
    },
    "itemClass": {
      "@id": "rim:itemClass",
      "@type": "@id"
    },
    "inRegister": {
      "@id": "rim:inRegister",
      "@type": "@id"
    },
    "realizes": {
      "@id": "rim:realizes",
      "@type": "@id"
    },
    "validityStatus": {
      "@id": "rim:validityStatus",
      "@type": "@vocab"
    },
    "publicationStatus": {
      "@id": "rim:publicationStatus",
      "@type": "@vocab"
    },
    "isRedacted": {
      "@id": "rim:isRedacted",
      "@type": "xsd:boolean"
    },
    "isDeleted": {
      "@id": "rim:isDeleted",
      "@type": "xsd:boolean"
    },
    "title": "dct:title",
    "description": "dct:description",
    "relatedItem": {
      "@id": "rim:relatedItem",
      "@type": "@id"
    },
    "supersededBy": {
      "@id": "rim:supersededBy",
      "@type": "@id"
    },
    "supersedes": {
      "@id": "rim:supersedes",
      "@type": "@id"
    },
    "hasAction": {
      "@id": "rim:hasAction",
      "@type": "@id"
    },
    "Format": "df:Format",
    "Representation": "df:Representation",
    "format": {
      "@id": "df:format",
      "@type": "@id"
    },
    "specification": {
      "@id": "dct:conformsTo",
      "@type": "@id"
    },
    "observedMediaTypes": {
      "@context": {
        "mediaType": "df:mediaType",
        "observedIn": "df:observedIn"
      },
      "@id": "df:observedMediaType"
    },
    "inferredMediaTypes": {
      "@context": {
        "mediaType": "df:mediaType",
        "source": {
          "@id": "dct:source",
          "@type": "@id"
        }
      },
      "@id": "df:inferredMediaType"
    },
    "primaryMediaType": "df:primaryMediaType",
    "jsonSchemaFragment": {
      "@id": "df:jsonSchemaFragment",
      "@type": "@json"
    },
    "parameters": {
      "@context": {
        "name": "df:parameterName",
        "jsonSchemaKeyword": "df:jsonSchemaKeyword"
      },
      "@id": "df:parameter"
    },
    "cwlCustomType": "df:cwlCustomType",
    "seeAlso": {
      "@id": "rdfs:seeAlso",
      "@type": "@id"
    },
    "rim": "https://w3id.org/ogc/rim/",
    "prov": "http://www.w3.org/ns/prov#",
    "dct": "http://purl.org/dc/terms/",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "skos": "http://www.w3.org/2004/02/skos/core#",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "df": "https://w3id.org/geolabs/ospd/data-formats/",
    "dt": "https://geolabs.github.io/bblocks-data-types/def/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/stac-item/context.jsonld)

## Sources

* [STAC Item Specification 1.1.0](https://github.com/radiantearth/stac-spec/blob/v1.1.0/item-spec/item-spec.md)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/format/stac-item`

