
# Format: OGC API - Processes bounding box (Schema)

`data-formats.format.ogcapi-processes-bbox` *v0.1*

A bounding box as OGC API - Processes - Part 1: Core encodes it in JSON (ogc.api.processes.part1.v1.schemas.bbox).

[*Status*](http://www.opengis.net/def/status): Under development

## Description

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

## Examples

### OGC API - Processes bounding box
The register item of the OGC API - Processes bounding box format, of the register's format item class.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://docs.ogc.org/is/18-062r2/18-062r2.html",
      "title": "OGC 18-062r2 OGC API - Processes - Part 1: Core"
    }
  ],
  "jsonSchemaFragment": {
    "$ref": "https://geolabs.github.io/bblocks-ogcapi-processes/build/annotated/api/processes/v1/schemas/bbox/schema.json"
  },
  "inferredMediaTypes": [
    {
      "mediaType": "application/json",
      "source": "https://docs.ogc.org/is/18-062r2/18-062r2.html",
      "description": "Inferred from the bbox JSON schema of OGC API - Processes - Part 1 (an object with the bbox array and crs): a JSON value. OGC 18-062r2 states no media type for a bounding box: Requirement 23 (/req/core/process-execute-input-inline-bbox, 7.11.2.2) only requires the bbox.yaml schema for an inline value, and Recommendation 17 with Table 13 (8.2) marks it with the JSON Schema format key ogc-bbox. Not observed on the testbed."
    }
  ],
  "seeAlso": "https://geolabs.github.io/bblocks-ogcapi-processes/",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": [
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox",
      "startedAtTime": "2026-11-09T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox/actions/amendment-media-type",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "Media type application/json added as inferred (df:inferredMediaType), not observed: inferred from the bbox JSON schema; OGC 18-062r2 states none (Requirement 23, Recommendation 17). Decision of 2026-11-09.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox",
      "startedAtTime": "2026-11-09T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox/actions/amendment-identifier-2026-11-10",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "The description, the title of the source and the abstract of the block name the OGC API - Processes bbox building block by its identifier after its renaming by GeoLabs on 2026-11-10 (Part 1, edition 1.0: ogc.api.processes.part1.v1.schemas.bbox). The format, its specification and its media types are unchanged. Classified clarifying: a reworded description.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox",
      "startedAtTime": "2026-11-10T00:00:00Z"
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


<https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox> a df:Format, rim:RegisterItem ;
    dct:title "OGC API - Processes bounding box"@en ;
    dct:description "A bounding box as OGC API - Processes - Part 1: Core encodes it in JSON: an array of 4 or 6 numbers (bbox) and an optional CRS (crs), as the schema of ogc.api.processes.part1.v1.schemas.bbox gives it."@en ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox"^^xsd:anyURI ;
    rim:itemClass df:formatItemClass ;
    rim:inRegister df:register ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox/actions/addition> , <https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox/actions/amendment-media-type> ,
        <https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox/actions/amendment-identifier-2026-11-10> ;
    dct:conformsTo <https://docs.ogc.org/is/18-062r2/18-062r2.html> ;
    df:jsonSchemaFragment "{\"$ref\":\"https://geolabs.github.io/bblocks-ogcapi-processes/build/annotated/api/processes/v1/schemas/bbox/schema.json\"}"^^rdf:JSON ;
    df:inferredMediaType [ df:mediaType "application/json" ;
        dct:source <https://docs.ogc.org/is/18-062r2/18-062r2.html> ;
        dct:description "Inferred from the bbox JSON schema of OGC API - Processes - Part 1 (an object with the bbox array and crs): a JSON value. OGC 18-062r2 states no media type for a bounding box: Requirement 23 (/req/core/process-execute-input-inline-bbox, 7.11.2.2) only requires the bbox.yaml schema for an inline value, and Recommendation 17 with Table 13 (8.2) marks it with the JSON Schema format key ogc-bbox. Not observed on the testbed."@en ] ;
    dct:source <https://docs.ogc.org/is/17-069r4/17-069r4.html> ;
    rdfs:seeAlso <https://geolabs.github.io/bblocks-ogcapi-processes/> .

<https://docs.ogc.org/is/18-062r2/18-062r2.html> dct:title "OGC 18-062r2 OGC API - Processes - Part 1: Core" .
<https://docs.ogc.org/is/17-069r4/17-069r4.html> dct:title "OGC 17-069r4 OGC API - Features - Part 1: Core, 7.15.3 Parameter bbox" .

<https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox> ;
    prov:startedAtTime "2026-11-09T00:00:00Z"^^xsd:dateTime .

<https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox/actions/amendment-media-type> a rim:RegisterAction ;
    rim:actionType df:amendmentAction ;
    rim:changeClassification rim:clarifyingChange ;
    rim:affectedProperty df:inferredMediaType ;
    dct:description "Media type application/json added as inferred (df:inferredMediaType), not observed: inferred from the bbox JSON schema; OGC 18-062r2 states none (Requirement 23, Recommendation 17). Decision of 2026-11-09."@en ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox> ;
    prov:startedAtTime "2026-11-09T00:00:00Z"^^xsd:dateTime .

<https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox/actions/amendment-identifier-2026-11-10> a rim:RegisterAction ;
    rim:actionType df:amendmentAction ;
    rim:changeClassification rim:clarifyingChange ;
    rim:affectedProperty dct:description ;
    dct:description "The description, the title of the source and the abstract of the block name the OGC API - Processes bbox building block by its identifier after its renaming by GeoLabs on 2026-11-10 (Part 1, edition 1.0: ogc.api.processes.part1.v1.schemas.bbox). The format, its specification and its media types are unchanged. Classified clarifying: a reworded description."@en ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox> ;
    prov:startedAtTime "2026-11-10T00:00:00Z"^^xsd:dateTime .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-formats/build/annotated/format/ogcapi-processes-bbox/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://docs.ogc.org/is/18-062r2/18-062r2.html",
      "title": "OGC 18-062r2 OGC API - Processes - Part 1: Core"
    }
  ],
  "jsonSchemaFragment": {
    "$ref": "https://geolabs.github.io/bblocks-ogcapi-processes/build/annotated/api/processes/v1/schemas/bbox/schema.json"
  },
  "inferredMediaTypes": [
    {
      "mediaType": "application/json",
      "source": "https://docs.ogc.org/is/18-062r2/18-062r2.html",
      "description": "Inferred from the bbox JSON schema of OGC API - Processes - Part 1 (an object with the bbox array and crs): a JSON value. OGC 18-062r2 states no media type for a bounding box: Requirement 23 (/req/core/process-execute-input-inline-bbox, 7.11.2.2) only requires the bbox.yaml schema for an inline value, and Recommendation 17 with Table 13 (8.2) marks it with the JSON Schema format key ogc-bbox. Not observed on the testbed."
    }
  ],
  "seeAlso": "https://geolabs.github.io/bblocks-ogcapi-processes/",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": [
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox",
      "startedAtTime": "2026-11-09T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox/actions/amendment-media-type",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "Media type application/json added as inferred (df:inferredMediaType), not observed: inferred from the bbox JSON schema; OGC 18-062r2 states none (Requirement 23, Recommendation 17). Decision of 2026-11-09.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox",
      "startedAtTime": "2026-11-09T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox/actions/amendment-identifier-2026-11-10",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "The description, the title of the source and the abstract of the block name the OGC API - Processes bbox building block by its identifier after its renaming by GeoLabs on 2026-11-10 (Part 1, edition 1.0: ogc.api.processes.part1.v1.schemas.bbox). The format, its specification and its media types are unchanged. Classified clarifying: a reworded description.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox",
      "startedAtTime": "2026-11-10T00:00:00Z"
    }
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Format item - OGC API - Processes bounding box
description: The register item of the OGC API - Processes bounding box format, in
  JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-formats/build/annotated/format/schema.yaml
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox
x-bblocks-metadata:
  itemIdentifier: data-formats.format.ogcapi-processes-bbox
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-09'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/ogcapi-processes-bbox/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/ogcapi-processes-bbox/schema.yaml)


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
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/ogcapi-processes-bbox/context.jsonld)

## Sources

* [OGC 18-062r2 OGC API - Processes - Part 1: Core](https://docs.ogc.org/is/18-062r2/18-062r2.html)
* [OGC 17-069r4 OGC API - Features - Part 1: Core, 7.15.3 Parameter bbox](https://docs.ogc.org/is/17-069r4/17-069r4.html)
* [ogc.api.processes.part1.v1.schemas.bbox -- bbox schema (OGC API - Processes - Part 1: Core)](https://geolabs.github.io/bblocks-ogcapi-processes/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/format/ogcapi-processes-bbox`

