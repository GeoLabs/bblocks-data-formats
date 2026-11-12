
# Representation item (Schema)

`data-formats.representation` *v0.1*

A representation of this register, in JSON: a profile of the Registered Item Model register item that realizes one data type version of the data-types register and points to one format.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

The representation item of the data-formats register, in JSON.

## Definition

A `df:Representation` is a `rim:RegisterItem` of the `df:representationItemClass` item class. It
realizes (`rim:realizes`) exactly one `dt:DataTypeVersion` of the data-types register and points
(`df:format`) to exactly one [format](../format/) of this register. `df:RepresentationShape` checks
both; the Registered Item Model already limits an item to one `rim:realizes`.

A representation is created when an existing role needs it: each one lists the Implementation
Profile roles that request it. In `bblock.json`, `isDescribedBy` names the data type block of the
data-types register; `hasFormat` will link the representations of a same data type once a data type
has more than one.

## Content of this block

- `schema.yaml`: a profile of `ogc.rim.schemas.register-item`.
- `context.jsonld`: the JSON-LD context of the items, inherited by every item block through its
  schema (the same context in the format and representation blocks).

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Representation item
description: 'A representation of the data-formats register, in JSON: a profile of
  the Registered Item Model register item (`type` pinned to `Representation`). It
  realizes exactly one data type version of the data-types register (`realizes`) and
  points to one format of this register (`format`).'
allOf:
- $ref: https://ogcincubator.github.io/registered-item-model/build/annotated/rim/schemas/register-item/schema.yaml
type: object
required:
- realizes
- format
- hasAction
properties:
  type:
    const: Representation
    x-jsonld-id: '@type'
  itemClass:
    const: https://w3id.org/geolabs/ospd/data-formats/representationItemClass
    x-jsonld-id: https://w3id.org/ogc/rim/itemClass
    x-jsonld-type: '@id'
  inRegister:
    const: https://w3id.org/geolabs/ospd/data-formats/register
    x-jsonld-id: https://w3id.org/ogc/rim/inRegister
    x-jsonld-type: '@id'
  realizes:
    type: string
    format: uri
    pattern: ^https://geolabs\.github\.io/bblocks-data-types/def/data-type/[a-z0-9-]+/v[0-9]+$
    x-jsonld-id: https://w3id.org/ogc/rim/realizes
    x-jsonld-type: '@id'
  format:
    type: string
    format: uri
    pattern: ^https://w3id\.org/geolabs/ospd/data-formats/format/[a-z0-9-]+$
    x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/format
    x-jsonld-type: '@id'
  hasAction:
    description: 'The proposed addition, alone or followed by later actions on the
      item, as for a format. The schema requires the addition; it does not constrain
      the action type or the classification of the other actions (decision Q5, option
      b, of 2026-11-11: pending a decision common to all registers).'
    oneOf:
    - $ref: '#/$defs/addition'
    - type: array
      contains:
        $ref: '#/$defs/addition'
      items:
        $ref: '#/$defs/action'
    x-jsonld-id: https://w3id.org/ogc/rim/hasAction
    x-jsonld-type: '@id'
$defs:
  addition:
    type: object
    required:
    - id
    - actionType
    - proposer
    properties:
      id:
        type: string
        format: uri
        x-jsonld-id: '@id'
      type:
        const: RegisterAction
        x-jsonld-id: '@type'
      actionType:
        const: addition
        x-jsonld-id: https://w3id.org/ogc/rim/actionType
        x-jsonld-type: '@vocab'
      proposer:
        type: string
        format: uri
        x-jsonld-id: https://w3id.org/ogc/rim/proposer
        x-jsonld-type: '@id'
      startedAtTime:
        type: string
        format: date-time
        x-jsonld-id: http://www.w3.org/ns/prov#startedAtTime
        x-jsonld-type: http://www.w3.org/2001/XMLSchema#dateTime
  action:
    type: object
    required:
    - id
    - actionType
    - proposer
    properties:
      id:
        type: string
        format: uri
        x-jsonld-id: '@id'
      type:
        const: RegisterAction
        x-jsonld-id: '@type'
      actionType:
        type: string
        x-jsonld-id: https://w3id.org/ogc/rim/actionType
        x-jsonld-type: '@vocab'
      proposer:
        type: string
        format: uri
        x-jsonld-id: https://w3id.org/ogc/rim/proposer
        x-jsonld-type: '@id'
      startedAtTime:
        type: string
        format: date-time
        x-jsonld-id: http://www.w3.org/ns/prov#startedAtTime
        x-jsonld-type: http://www.w3.org/2001/XMLSchema#dateTime
      description:
        type: string
        x-jsonld-id: http://purl.org/dc/terms/description
x-jsonld-extra-terms:
  Register: https://w3id.org/ogc/rim/Register
  RegisterItem: https://w3id.org/ogc/rim/RegisterItem
  RegisterItemClass: https://w3id.org/ogc/rim/RegisterItemClass
  RegisterAction: https://w3id.org/ogc/rim/RegisterAction
  Format: https://w3id.org/geolabs/ospd/data-formats/Format
  Representation: https://w3id.org/geolabs/ospd/data-formats/Representation
  title: http://purl.org/dc/terms/title
  objectIdentifier:
    x-jsonld-id: https://w3id.org/ogc/rim/objectIdentifier
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#anyURI
  functionalIdentifier:
    x-jsonld-id: https://w3id.org/ogc/rim/functionalIdentifier
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#anyURI
  supersededBy:
    x-jsonld-id: https://w3id.org/ogc/rim/supersededBy
    x-jsonld-type: '@id'
  supersedes:
    x-jsonld-id: https://w3id.org/ogc/rim/supersedes
    x-jsonld-type: '@id'
  validityStatus:
    x-jsonld-id: https://w3id.org/ogc/rim/validityStatus
    x-jsonld-type: '@vocab'
  publicationStatus:
    x-jsonld-id: https://w3id.org/ogc/rim/publicationStatus
    x-jsonld-type: '@vocab'
  valid: https://w3id.org/ogc/rim/valid
  invalid: https://w3id.org/ogc/rim/invalid
  published: https://w3id.org/ogc/rim/published
  unpublished: https://w3id.org/ogc/rim/unpublished
  appliesTo:
    x-jsonld-id: https://w3id.org/ogc/rim/appliesTo
    x-jsonld-type: '@id'
  changeClassification:
    x-jsonld-id: https://w3id.org/ogc/rim/changeClassification
    x-jsonld-type: '@vocab'
  addition: https://w3id.org/ogc/rim/additionAction
  substantive: https://w3id.org/ogc/rim/substantiveChange
  clarifying: https://w3id.org/ogc/rim/clarifyingChange
  specification:
    x-jsonld-id: http://purl.org/dc/terms/conformsTo
    x-jsonld-type: '@id'
  observedMediaTypes: https://w3id.org/geolabs/ospd/data-formats/observedMediaType
  mediaType: https://w3id.org/geolabs/ospd/data-formats/mediaType
  observedIn: https://w3id.org/geolabs/ospd/data-formats/observedIn
  primaryMediaType: https://w3id.org/geolabs/ospd/data-formats/primaryMediaType
  jsonSchemaFragment:
    x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/jsonSchemaFragment
    x-jsonld-type: '@json'
  parameters: https://w3id.org/geolabs/ospd/data-formats/parameter
  name: https://w3id.org/geolabs/ospd/data-formats/parameterName
  jsonSchemaKeyword: https://w3id.org/geolabs/ospd/data-formats/jsonSchemaKeyword
  cwlCustomType: https://w3id.org/geolabs/ospd/data-formats/cwlCustomType
  seeAlso:
    x-jsonld-id: http://www.w3.org/2000/01/rdf-schema#seeAlso
    x-jsonld-type: '@id'
x-jsonld-prefixes:
  rim: https://w3id.org/ogc/rim/
  df: https://w3id.org/geolabs/ospd/data-formats/
  dct: http://purl.org/dc/terms/
  xsd: http://www.w3.org/2001/XMLSchema#
  prov: http://www.w3.org/ns/prov#
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  dt: https://geolabs.github.io/bblocks-data-types/def/
  skos: http://www.w3.org/2004/02/skos/core#
x-bblocks-metadata:
  itemIdentifier: data-formats.representation
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-09'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/schema.yaml)


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
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/representation/context.jsonld)

## Sources

* [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
* [Registered Item Model (OGC Building Block)](https://ogcincubator.github.io/registered-item-model/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/representation`

