
# Format item (Schema)

`data-formats.format` *v0.1*

A format of this register, in JSON: a profile of the Registered Item Model register item that realizes no concept version and names its specification, its observed media types and/or a JSON Schema fragment.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

The format item of the data-formats register, in JSON.

## Definition

A `df:Format` is a `rim:RegisterItem` of the `df:formatItemClass` item class. It is an encoding:

- it realizes no concept version (`realizes` is forbidden, by the schema and by `df:FormatShape`);
- it names its specification (`specification`, `dct:conformsTo`);
- it carries the media types under which it was observed (`observedMediaTypes`), each with where it
  was observed: `implementation-profile` (tier 3) or `testbed` (tier 4), and/or a JSON Schema
  fragment (`jsonSchemaFragment`), with the `parameters` a profile must supply to complete it;
- it may carry media types that were not observed but inferred (`inferredMediaTypes`,
  `df:inferredMediaType`), each with its source (`dct:source`) and justification
  (`dct:description`), checked by `df:MediaTypeInferenceShape`.

A principal media type (`primaryMediaType`, `df:primaryMediaType`) is set only where a specification states the media type: the four STAC formats (`stac-item`, `stac-item-collection`, `stac-collection`, `stac-catalog`). It is one of the format's recorded media types, checked by `df:PrimaryMediaTypeShape`. None is set on the other formats: none has been chosen.

A format is bound to a data type by a [representation](../representation/).

## Content of this block

- `schema.yaml`: a profile of `ogc.rim.schemas.register-item`.
- `context.jsonld`: the JSON-LD context of the items, inherited by every item block through its
  schema (the same context in the format and representation blocks).

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Format item
description: 'A format of the data-formats register, in JSON: a profile of the Registered
  Item Model register item (`type` pinned to `Format`). A format realizes no concept
  version (`realizes` is forbidden); it names its specification and carries the media
  types observed where it is served and/or a JSON Schema fragment, with its parameters
  when the fragment is completed by the profile.'
allOf:
- $ref: https://ogcincubator.github.io/registered-item-model/build/annotated/rim/schemas/register-item/schema.yaml
type: object
required:
- specification
- hasAction
anyOf:
- required:
  - observedMediaTypes
- required:
  - jsonSchemaFragment
not:
  required:
  - realizes
properties:
  type:
    const: Format
    x-jsonld-id: '@type'
  itemClass:
    const: https://w3id.org/geolabs/ospd/data-formats/formatItemClass
    x-jsonld-id: https://w3id.org/ogc/rim/itemClass
    x-jsonld-type: '@id'
  inRegister:
    const: https://w3id.org/geolabs/ospd/data-formats/register
    x-jsonld-id: https://w3id.org/ogc/rim/inRegister
    x-jsonld-type: '@id'
  specification:
    type: array
    minItems: 1
    items:
      type: object
      required:
      - id
      - title
      properties:
        id:
          type: string
          format: uri
          x-jsonld-id: '@id'
        title:
          type: string
          x-jsonld-id: http://purl.org/dc/terms/title
    x-jsonld-id: http://purl.org/dc/terms/conformsTo
    x-jsonld-type: '@id'
  observedMediaTypes:
    type: array
    minItems: 1
    items:
      type: object
      required:
      - mediaType
      - observedIn
      properties:
        mediaType:
          type: string
          x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/mediaType
        observedIn:
          enum:
          - implementation-profile
          - testbed
          x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/observedIn
    x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/observedMediaType
  inferredMediaTypes:
    description: 'Media types not observed but taken from a source: stated by the
      format''s specification, or inferred (e.g. from its JSON Schema) when the specification
      states none; each with its source and justification.'
    type: array
    minItems: 1
    items:
      type: object
      required:
      - mediaType
      - source
      - description
      properties:
        mediaType:
          type: string
          x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/mediaType
        source:
          type: string
          format: uri
          x-jsonld-id: http://purl.org/dc/terms/source
          x-jsonld-type: '@id'
        description:
          type: string
          x-jsonld-id: http://purl.org/dc/terms/description
    x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/inferredMediaType
  primaryMediaType:
    type: string
    x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/primaryMediaType
  jsonSchemaFragment:
    type: object
    x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/jsonSchemaFragment
    x-jsonld-type: '@json'
  parameters:
    type: array
    items:
      type: object
      required:
      - name
      - jsonSchemaKeyword
      properties:
        name:
          type: string
          x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/parameterName
        jsonSchemaKeyword:
          type: string
          x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/jsonSchemaKeyword
        description:
          type: string
          x-jsonld-id: http://purl.org/dc/terms/description
    x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/parameter
  cwlCustomType:
    description: The record of the EOAP string_format.yaml that carries this format
      in CWL.
    type: string
    x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/cwlCustomType
  seeAlso:
    type: string
    format: uri
    x-jsonld-id: http://www.w3.org/2000/01/rdf-schema#seeAlso
    x-jsonld-type: '@id'
  hasAction:
    description: 'The proposed addition, alone or followed by later actions on the
      item. The schema requires the addition; it does not constrain the action type
      or the classification of the other actions (decision Q5, option b, of 2026-11-11:
      pending a decision common to all registers).'
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
  objectIdentifier:
    x-jsonld-id: https://w3id.org/ogc/rim/objectIdentifier
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#anyURI
  functionalIdentifier:
    x-jsonld-id: https://w3id.org/ogc/rim/functionalIdentifier
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#anyURI
  realizes:
    x-jsonld-id: https://w3id.org/ogc/rim/realizes
    x-jsonld-type: '@id'
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
  format:
    x-jsonld-id: https://w3id.org/geolabs/ospd/data-formats/format
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
  itemIdentifier: data-formats.format
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-09'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/schema.yaml)


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
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/context.jsonld)

## Sources

* [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
* [Registered Item Model (OGC Building Block)](https://ogcincubator.github.io/registered-item-model/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/format`

