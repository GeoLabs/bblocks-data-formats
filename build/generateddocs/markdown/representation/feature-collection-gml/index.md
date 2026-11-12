
# Representation: Feature collection as GML (Schema)

`data-formats.representation.feature-collection-gml` *v0.1*

The feature-collection data type of the data-types register, represented in GML.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

The feature-collection data type of the data-types register, represented in GML.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/v1` of the data-types register and points (`df:format`) to the format [GML](../../format/gml/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.feature-collection`.

## Requested by

Created because existing roles need it: 1 roles of 1 Implementation Profiles of `bblocks-generic-profiles` (branch `planes/phase-1-docs`, `b0da6aa`) have the data type `feature-collection` and a schema with `contentMediaType` `text/xml`, measured on 2026-11-09. They still carry that schema; they do not point to this representation yet.

- `implementation-profile/point-cloud-to-shapes/outputs/result`

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.

## Examples

### Feature collection as GML
The register item of the representation Feature collection as GML: it realizes version 1 of the feature-collection data type of the data-types register and points to the gml format.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml",
  "type": "Representation",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/representationItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "realizes": "https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/v1",
  "format": "https://w3id.org/geolabs/ospd/data-formats/format/gml",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": {
    "id": "https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml/actions/addition",
    "type": "RegisterAction",
    "actionType": "addition",
    "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
    "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml",
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


<https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml> a df:Representation, rim:RegisterItem ;
    dct:title "Feature collection as GML"@en ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml"^^xsd:anyURI ;
    rim:itemClass df:representationItemClass ;
    rim:inRegister df:register ;
    rim:realizes <https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/v1> ;
    df:format <https://w3id.org/geolabs/ospd/data-formats/format/gml> ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml/actions/addition> .

<https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml> ;
    prov:startedAtTime "2026-11-09T00:00:00Z"^^xsd:dateTime .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/feature-collection-gml/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml",
  "type": "Representation",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/representationItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "realizes": "https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/v1",
  "format": "https://w3id.org/geolabs/ospd/data-formats/format/gml",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": {
    "id": "https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml/actions/addition",
    "type": "RegisterAction",
    "actionType": "addition",
    "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
    "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml",
    "startedAtTime": "2026-11-09T00:00:00Z"
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Representation item - Feature collection as GML
description: The register item of the representation Feature collection as GML, in
  JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/schema.yaml
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-formats/representation/feature-collection-gml
x-bblocks-metadata:
  itemIdentifier: data-formats.representation.feature-collection-gml
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-09'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/feature-collection-gml/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/feature-collection-gml/schema.yaml)


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
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/feature-collection-gml/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/representation/feature-collection-gml`

