
# Representation: Bounding box as OGC API - Processes bbox (Schema)

`data-formats.representation.bounding-box-ogcapi-processes-bbox` *v0.1*

The bounding-box data type of the data-types register, represented as an OGC API - Processes bbox object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

The bounding-box data type of the data-types register, represented as an OGC API - Processes bbox object.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/v1` of the data-types register and points (`df:format`) to the format [OGC API - Processes bounding box](../../format/ogcapi-processes-bbox/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.bounding-box`.

## Requested by

Created on 2026-11-09 because one existing role needs it: `implementation-profile/raster-crop/inputs/areaOfInterest` of `bblocks-generic-profiles`, data type `bounding-box`, whose `schema` was a `$ref` to `ogc.api.processes.part1.v1.schemas.bbox`. That role points to this representation from branch `planes/phase-3` of that register.

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.

## Examples

### Bounding box as OGC API - Processes bbox
The register item of the representation Bounding box as OGC API - Processes bbox: it realizes version 1 of the bounding-box data type of the data-types register and points to the ogcapi-processes-bbox format.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox",
  "type": "Representation",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/representationItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "realizes": "https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/v1",
  "format": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": {
    "id": "https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox/actions/addition",
    "type": "RegisterAction",
    "actionType": "addition",
    "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
    "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox",
    "startedAtTime": "2026-11-09T00:00:00Z"
  }
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


<https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox> a df:Representation, rim:RegisterItem ;
    dct:title "Bounding box as OGC API - Processes bbox"@en ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox"^^xsd:anyURI ;
    rim:itemClass df:representationItemClass ;
    rim:inRegister df:register ;
    rim:realizes <https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/v1> ;
    df:format <https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox> ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox/actions/addition> .

<https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox> ;
    prov:startedAtTime "2026-11-09T00:00:00Z"^^xsd:dateTime .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/bounding-box-ogcapi-processes-bbox/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox",
  "type": "Representation",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/representationItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "realizes": "https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/v1",
  "format": "https://w3id.org/geolabs/ospd/data-formats/format/ogcapi-processes-bbox",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": {
    "id": "https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox/actions/addition",
    "type": "RegisterAction",
    "actionType": "addition",
    "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
    "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox",
    "startedAtTime": "2026-11-09T00:00:00Z"
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Representation item - Bounding box as OGC API - Processes bbox
description: The register item of the representation Bounding box as OGC API - Processes
  bbox, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/schema.yaml
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-formats/representation/bounding-box-ogcapi-processes-bbox
x-bblocks-metadata:
  itemIdentifier: data-formats.representation.bounding-box-ogcapi-processes-bbox
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-09'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/bounding-box-ogcapi-processes-bbox/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/bounding-box-ogcapi-processes-bbox/schema.yaml)


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
    "specification": {
      "@id": "dct:conformsTo",
      "@type": "@id"
    },
    "observedMediaTypes": "df:observedMediaType",
    "mediaType": "df:mediaType",
    "observedIn": "df:observedIn",
    "primaryMediaType": "df:primaryMediaType",
    "jsonSchemaFragment": {
      "@id": "df:jsonSchemaFragment",
      "@type": "@json"
    },
    "parameters": "df:parameter",
    "name": "df:parameterName",
    "jsonSchemaKeyword": "df:jsonSchemaKeyword",
    "cwlCustomType": "df:cwlCustomType",
    "seeAlso": {
      "@id": "rdfs:seeAlso",
      "@type": "@id"
    },
    "format": {
      "@id": "df:format",
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
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/bounding-box-ogcapi-processes-bbox/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/representation/bounding-box-ogcapi-processes-bbox`

