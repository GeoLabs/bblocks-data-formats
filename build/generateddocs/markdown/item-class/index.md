
# Data Formats item classes (Schema)

`data-formats.item-class` *v0.1*

The two item classes of this register, format and representation, in JSON: a profile of the Registered Item Model register item class.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

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

## Examples

### The format item class (JSON)
The abstraction every format shares, validated by df:FormatShape.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "type": "RegisterItemClass",
  "title": "Format",
  "definedIn": "https://w3id.org/geolabs/ospd/data-formats/register",
  "validatedBy": "https://w3id.org/geolabs/ospd/data-formats/FormatShape"
}

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-formats/build/annotated/item-class/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "type": "RegisterItemClass",
  "title": "Format",
  "definedIn": "https://w3id.org/geolabs/ospd/data-formats/register",
  "validatedBy": "https://w3id.org/geolabs/ospd/data-formats/FormatShape"
}
```

#### ttl
```ttl
@prefix dct: <http://purl.org/dc/terms/> .
@prefix rim: <https://w3id.org/ogc/rim/> .

<https://w3id.org/geolabs/ospd/data-formats/formatItemClass> a rim:RegisterItemClass ;
    dct:title "Format" ;
    rim:definedIn <https://w3id.org/geolabs/ospd/data-formats/register> ;
    rim:validatedBy <https://w3id.org/geolabs/ospd/data-formats/FormatShape> .


```


### The representation item class (JSON)
The abstraction every representation shares, validated by df:RepresentationShape.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-formats/representationItemClass",
  "type": "RegisterItemClass",
  "title": "Representation",
  "definedIn": "https://w3id.org/geolabs/ospd/data-formats/register",
  "validatedBy": "https://w3id.org/geolabs/ospd/data-formats/RepresentationShape"
}

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-formats/build/annotated/item-class/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-formats/representationItemClass",
  "type": "RegisterItemClass",
  "title": "Representation",
  "definedIn": "https://w3id.org/geolabs/ospd/data-formats/register",
  "validatedBy": "https://w3id.org/geolabs/ospd/data-formats/RepresentationShape"
}
```

#### ttl
```ttl
@prefix dct: <http://purl.org/dc/terms/> .
@prefix rim: <https://w3id.org/ogc/rim/> .

<https://w3id.org/geolabs/ospd/data-formats/representationItemClass> a rim:RegisterItemClass ;
    dct:title "Representation" ;
    rim:definedIn <https://w3id.org/geolabs/ospd/data-formats/register> ;
    rim:validatedBy <https://w3id.org/geolabs/ospd/data-formats/RepresentationShape> .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Data Formats item class
description: 'One of the two item classes of the data-formats register, in JSON: format
  or representation. Each is defined in the register and validated by a shape of the
  shared vocabulary.'
allOf:
- $ref: https://ogcincubator.github.io/registered-item-model/build/annotated/rim/schemas/register-item-class/schema.yaml
required:
- definedIn
- validatedBy
properties:
  id:
    enum:
    - https://w3id.org/geolabs/ospd/data-formats/formatItemClass
    - https://w3id.org/geolabs/ospd/data-formats/representationItemClass
x-bblocks-metadata:
  itemIdentifier: data-formats.item-class
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-09'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/item-class/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/item-class/schema.yaml)


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
    "versionOf": {
      "@id": "rim:versionOf",
      "@type": "@id"
    },
    "version": "rim:version",
    "validityStatus": {
      "@id": "rim:validityStatus",
      "@type": "@vocab"
    },
    "publicationStatus": {
      "@id": "rim:publicationStatus",
      "@type": "@vocab"
    },
    "valid": "rim:valid",
    "invalid": "rim:invalid",
    "published": "rim:published",
    "unpublished": "rim:unpublished",
    "isRedacted": {
      "@id": "rim:isRedacted",
      "@type": "xsd:boolean"
    },
    "isDeleted": {
      "@id": "rim:isDeleted",
      "@type": "xsd:boolean"
    },
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
    "title": "dct:title",
    "description": "dct:description",
    "definedIn": {
      "@id": "rim:definedIn",
      "@type": "@id"
    },
    "validatedBy": {
      "@id": "rim:validatedBy",
      "@type": "@id"
    },
    "rim": "https://w3id.org/ogc/rim/",
    "prov": "http://www.w3.org/ns/prov#",
    "dct": "http://purl.org/dc/terms/",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "skos": "http://www.w3.org/2004/02/skos/core#",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/item-class/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/item-class`

