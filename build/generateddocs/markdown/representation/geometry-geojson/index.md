
# Representation: Geometry as GeoJSON (Schema)

`data-formats.representation.geometry-geojson` *v0.1*

The geometry data type of the data-types register, represented in GeoJSON.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

The geometry data type of the data-types register, represented in GeoJSON.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://w3id.org/geolabs/ospd/data-types/data-type/geometry/v1` of the data-types register and points (`df:format`) to the format [GeoJSON](../../format/geojson/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.geometry`. `hasFormat` names [`geometry-gml`](../geometry-gml/), which represents the same data type in another format.

## Schema

`df:jsonSchemaFragment` is a reference to `https://geojson.org/schema/Geometry.json`, published by [geojson/schema](https://github.com/geojson/schema). The schemas of https://github.com/geojson/schema are published without a version (the URL serves the latest build), are written in JSON Schema draft-07, and cannot check that linear rings are closed or follow the right-hand rule (RFC 7946, section 3.1.6).

## Requested by

Added on 2026-11-10 for roles of the new Implementation Profiles of `bblocks-generic-profiles` (branch `planes/new-profiles`):

- [`implementation-profile/product-selection/inputs/areaOfInterest`](https://w3id.org/geolabs/ospd/generic-profiles/implementation-profile/product-selection/inputs/areaOfInterest)

The other GeoJSON object types were added the same day: every object type that geojson/schema publishes and that the data-types register defines now has a GeoJSON representation.

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.

## Examples

### Geometry as GeoJSON
The register item of the representation Geometry as GeoJSON: it realizes version 1 of the geometry data type of the data-types register and points to the geojson format.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson",
  "type": "Representation",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/representationItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "realizes": "https://w3id.org/geolabs/ospd/data-types/data-type/geometry/v1",
  "format": "https://w3id.org/geolabs/ospd/data-formats/format/geojson",
  "jsonSchemaFragment": {
    "$ref": "https://geojson.org/schema/Geometry.json"
  },
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": [
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/org/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson",
      "startedAtTime": "2026-11-10T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson/actions/amendment-schema-fragment-2026-11-17",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "substantive",
      "description": "JSON Schema fragment added (df:jsonSchemaFragment): a reference to https://geojson.org/schema/Geometry.json, the schema of a GeoJSON geometry object published by https://github.com/geojson/schema. The schemas of https://github.com/geojson/schema are published without a version (the URL serves the latest build), are written in JSON Schema draft-07, and cannot check that linear rings are closed or follow the right-hand rule (RFC 7946, section 3.1.6). Decision of Gérald, 2026-11-17: each GeoJSON representation carries the schema of its data type. The realized data type version and the format are unchanged. Classified substantive: the register specification lists the schema fragment among the substantive changes.",
      "proposer": "https://w3id.org/geolabs/ospd/org/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson",
      "startedAtTime": "2026-11-17T00:00:00Z"
    }
  ]
}

```

#### turtle
```turtle
@prefix df:   <https://w3id.org/geolabs/ospd/data-formats/> .
@prefix dt:   <https://w3id.org/geolabs/ospd/data-types/> .
@prefix rim:  <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct:  <http://purl.org/dc/terms/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix rdf:  <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix xsd:  <http://www.w3.org/2001/XMLSchema#> .
@prefix prov: <http://www.w3.org/ns/prov#> .

<https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson> a df:Representation, rim:RegisterItem ;
    dct:title "Geometry as GeoJSON"@en ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson"^^xsd:anyURI ;
    rim:itemClass df:representationItemClass ;
    rim:inRegister df:register ;
    rim:realizes <https://w3id.org/geolabs/ospd/data-types/data-type/geometry/v1> ;
    df:format <https://w3id.org/geolabs/ospd/data-formats/format/geojson> ;
    df:jsonSchemaFragment "{\"$ref\":\"https://geojson.org/schema/Geometry.json\"}"^^rdf:JSON ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson/actions/addition> ,
        <https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson/actions/amendment-schema-fragment-2026-11-17> .

<https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer <https://w3id.org/geolabs/ospd/org/geolabs> ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson> ;
    prov:startedAtTime "2026-11-10T00:00:00Z"^^xsd:dateTime .

<https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson/actions/amendment-schema-fragment-2026-11-17> a rim:RegisterAction ;
    rim:actionType df:amendmentAction ;
    rim:changeClassification rim:substantiveChange ;
    rim:affectedProperty df:jsonSchemaFragment ;
    dct:description "JSON Schema fragment added (df:jsonSchemaFragment): a reference to https://geojson.org/schema/Geometry.json, the schema of a GeoJSON geometry object published by https://github.com/geojson/schema. The schemas of https://github.com/geojson/schema are published without a version (the URL serves the latest build), are written in JSON Schema draft-07, and cannot check that linear rings are closed or follow the right-hand rule (RFC 7946, section 3.1.6). Decision of Gérald, 2026-11-17: each GeoJSON representation carries the schema of its data type. The realized data type version and the format are unchanged. Classified substantive: the register specification lists the schema fragment among the substantive changes."@en ;
    rim:proposer <https://w3id.org/geolabs/ospd/org/geolabs> ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson> ;
    prov:startedAtTime "2026-11-17T00:00:00Z"^^xsd:dateTime .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/geometry-geojson/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson",
  "type": "Representation",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/representationItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "realizes": "https://w3id.org/geolabs/ospd/data-types/data-type/geometry/v1",
  "format": "https://w3id.org/geolabs/ospd/data-formats/format/geojson",
  "jsonSchemaFragment": {
    "$ref": "https://geojson.org/schema/Geometry.json"
  },
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": [
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/org/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson",
      "startedAtTime": "2026-11-10T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson/actions/amendment-schema-fragment-2026-11-17",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "substantive",
      "description": "JSON Schema fragment added (df:jsonSchemaFragment): a reference to https://geojson.org/schema/Geometry.json, the schema of a GeoJSON geometry object published by https://github.com/geojson/schema. The schemas of https://github.com/geojson/schema are published without a version (the URL serves the latest build), are written in JSON Schema draft-07, and cannot check that linear rings are closed or follow the right-hand rule (RFC 7946, section 3.1.6). Decision of G\u00e9rald, 2026-11-17: each GeoJSON representation carries the schema of its data type. The realized data type version and the format are unchanged. Classified substantive: the register specification lists the schema fragment among the substantive changes.",
      "proposer": "https://w3id.org/geolabs/ospd/org/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson",
      "startedAtTime": "2026-11-17T00:00:00Z"
    }
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Representation item - Geometry as GeoJSON
description: The register item of the representation Geometry as GeoJSON, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/schema.yaml
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-formats/representation/geometry-geojson
x-bblocks-metadata:
  itemIdentifier: data-formats.representation.geometry-geojson
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-10'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/geometry-geojson/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/geometry-geojson/schema.yaml)


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
    "jsonSchemaFragment": {
      "@id": "df:jsonSchemaFragment",
      "@type": "@json"
    },
    "xmlSchemaElement": {
      "@context": {
        "namespace": {
          "@id": "df:xmlNamespace",
          "@type": "@id"
        },
        "localName": "df:xmlLocalName",
        "schema": {
          "@id": "dct:source",
          "@type": "@id"
        }
      },
      "@id": "df:xmlSchemaElement"
    },
    "rim": "https://w3id.org/ogc/rim/",
    "prov": "http://www.w3.org/ns/prov#",
    "dct": "http://purl.org/dc/terms/",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "skos": "http://www.w3.org/2004/02/skos/core#",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "df": "https://w3id.org/geolabs/ospd/data-formats/",
    "dt": "https://w3id.org/geolabs/ospd/data-types/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/geometry-geojson/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/representation/geometry-geojson`

