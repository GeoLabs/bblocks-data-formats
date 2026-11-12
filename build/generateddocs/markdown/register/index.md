
# Data Formats register (Schema)

`data-formats.register` *v0.1*

The data-formats register itself, in JSON: a profile of the Registered Item Model register, with its system and the roles that govern it.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

The data-formats register as a Registered Item Model **register**, in JSON.

## Definition

A profile of the RIM `register` schema: the governed collection of formats and representations,
distinct from the register system it runs on (`runsOn`) and from the roles that govern it. Its
title, description and item classes are declared in the `data.ttl` of the
[shared vocabulary](../vocabulary/), which the SHACL closure of this block includes.

## Register specification

`df:specification` is a `rim:RegisterSpecification`. It records:

- the register type: a content register, as the Registered Item Model uses the term;
- the roles: GeoLabs SARL is owner, manager and, for now, control body, with the written intention
  to delegate the control body role to the OGC or to an OSPD working group;
- the `rim:realizes` link with the data-types register: a representation realizes at most one
  `dt:DataTypeVersion`; this register depends on data-types, never the reverse;
- the definition of a substantive change (`rim:definesSubstantiveChange`), the table of substantive
  and clarifying changes for formats and representations, the version rule and the rule for
  proposals;
- `df:amendmentAction`, the action type of an in-place change to a proposal;
- that no eligibility criteria and no commitments have been set.

## Sources

- [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
- [Registered Item Model](https://ogcincubator.github.io/registered-item-model/)

## Examples

### The data-formats register (JSON)
The register, the system it runs on and the roles that govern it. Its title, description, item classes and specification are in the shared vocabulary's `data.ttl`.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-formats/register",
  "type": "Register",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/register",
  "functionalIdentifier": "https://geolabs.github.io/bblocks-data-formats/",
  "runsOn": "https://w3id.org/geolabs/ospd/data-formats/registerSystem",
  "registerOwner": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
  "registerManager": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
  "controlBody": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
  "hasSpecification": "https://w3id.org/geolabs/ospd/data-formats/specification"
}

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-formats/build/annotated/register/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-formats/register",
  "type": "Register",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/register",
  "functionalIdentifier": "https://geolabs.github.io/bblocks-data-formats/",
  "runsOn": "https://w3id.org/geolabs/ospd/data-formats/registerSystem",
  "registerOwner": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
  "registerManager": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
  "controlBody": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
  "hasSpecification": "https://w3id.org/geolabs/ospd/data-formats/specification"
}
```

#### ttl
```ttl
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://w3id.org/geolabs/ospd/data-formats/register> a rim:Register ;
    rim:controlBody <https://w3id.org/geolabs/ospd/data-formats/geolabs> ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-formats/"^^xsd:anyURI ;
    rim:hasSpecification <https://w3id.org/geolabs/ospd/data-formats/specification> ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/register"^^xsd:anyURI ;
    rim:registerManager <https://w3id.org/geolabs/ospd/data-formats/geolabs> ;
    rim:registerOwner <https://w3id.org/geolabs/ospd/data-formats/geolabs> ;
    rim:runsOn <https://w3id.org/geolabs/ospd/data-formats/registerSystem> .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Data Formats register
description: 'The data-formats register, in JSON: the governed collection itself,
  the system it runs on and the roles that govern it.'
allOf:
- $ref: https://ogcincubator.github.io/registered-item-model/build/annotated/rim/schemas/register/schema.yaml
required:
- objectIdentifier
- runsOn
- registerOwner
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-formats/register
x-bblocks-metadata:
  itemIdentifier: data-formats.register
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-09'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/register/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/register/schema.yaml)


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
    "definesSubstantiveChange": "rim:definesSubstantiveChange",
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
    "runsOn": {
      "@id": "rim:runsOn",
      "@type": "@id"
    },
    "hasSpecification": {
      "@id": "rim:hasSpecification",
      "@type": "@id"
    },
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
      "@context": {
        "commitmentCategory": {
          "@id": "rim:commitmentCategory",
          "@type": "@vocab"
        }
      },
      "@id": "rim:hasCommitment",
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
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/register/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/register`

