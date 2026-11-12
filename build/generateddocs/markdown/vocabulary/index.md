
# Data Formats shared model (Model)

`data-formats.vocabulary` *v0.1*

Shared RIM content-plane model, register metadata and SHACL rules for the format and representation Building Blocks of this register.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

The shared model of the data-formats register: the content plane of the OSPD data axis, as a
profile of the [Registered Item Model](https://ogcincubator.github.io/registered-item-model/).

## Model

| Class | Item class | Realizes | Carries |
|---|---|---|---|
| `df:Format` | `df:formatItemClass` | nothing | specification (`dct:conformsTo`), observed media types (`df:observedMediaType`), media types taken from a source (`df:inferredMediaType`: stated by the specification, or inferred when it states none; with source and justification), at most one principal media type (`df:primaryMediaType`, one of those recorded) and/or a JSON Schema fragment (`df:jsonSchemaFragment`), parameters (`df:parameter`) |
| `df:Representation` | `df:representationItemClass` | one `dt:DataTypeVersion` of the data-types register | one format (`df:format`) |

Both are sub-classes of `rim:RegisterItem`, so `rim:RegisterItemShape` applies to every item. Every
item records its addition, proposed by GeoLabs, and is `rim:invalid` and `rim:published`: a proposal
awaiting a decision.

The meaning of data is not here: it is the concept plane of the
[data-types register](https://geolabs.github.io/bblocks-data-types/). This register depends on it
(`dependsOn: data-types.vocabulary`), so the data type versions a representation realizes are in the
SHACL closure; data-types never depends on this register.

## Content of this block

- `ontology.ttl`: classes and properties.
- `data.ttl`: the register, its owner and system, the two item classes, the register specification
  (`df:specification`) and the amendment action type (`df:amendmentAction`).
- `shapes.shacl`: `df:FormatShape`, `df:RepresentationShape`, `df:AdditionProposalShape`.
- `tests/`: Turtle items that must fail, one per rule.

## Sources

- [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
- [Registered Item Model](https://ogcincubator.github.io/registered-item-model/)

## Examples

### Shared register metadata
The register, its owner and system and the two item classes, format and representation. Each
format and representation Building Block publishes its own item and addition in its
`ontology.ttl`.

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

# Register-level metadata only. Each format and representation, with its addition action, is
# canonical in the ontology.ttl of its own Building Block.

df:register a rim:Register ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/register"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-formats/"^^xsd:anyURI ;
    dct:title "Data Formats"@en ;
    dct:description "A content register of the formats in which process inputs and outputs are encoded, and of the representations that bind a data type to a format."@en ;
    rim:registerOwner df:geolabs ;
    rim:registerManager df:geolabs ;
    rim:controlBody df:geolabs ;
    rim:hasSpecification df:specification ;
    rim:runsOn df:registerSystem .

# The register specification. rim:definesSubstantiveChange, the rule for proposals and the table of
# substantive and clarifying changes are the texts validated by GeoLabs on 2026-11-05, word for word;
# the table was validated in French and is given verbatim, followed by an English rendering.
# vocabulary/tests/specification-without-title-fail.ttl proves that rim:RegisterSpecificationShape
# runs on this register.
df:specification a rim:RegisterSpecification ;
    dct:title "Data Formats register specification"@en ;
    dct:description
        "Scope. This register holds the content plane of the data axis: formats (df:Format) and representations (df:Representation). The meaning of data, the data types, is held by the data-types register (https://geolabs.github.io/bblocks-data-types/), not here."@en ,
        "Register type. A content register, as the Registered Item Model uses the term: this register has no concept plane of its own. A format realizes no concept version. A representation realizes (rim:realizes) at most one dt:DataTypeVersion of the data-types register, which is the concept plane it represents, and points to one format. A representation is created when an existing role needs it."@en ,
        "Relation with the data-types register. This register depends on the data-types register; the data-types register never depends on this register. The Registered Item Model allows a dt:DataTypeVersion to be realized by items of both registers, its own dt:DataTypeItem and representations of this register: it limits rim:realizes to one version per item (rim:RegisterItemShape), not to one item per version."@en ,
        "Replacement of a data type. When a format or a representation replaces an item of the data-types register, it carries rim:supersedes towards that item, which is typed in the closure this register validates; the replaced item carries dct:isReplacedBy towards it. The 19 string-* formats supersede the withdrawn string-* data types."@en ,
        "Roles. GeoLabs SARL is the register owner, the register manager and, for now, the control body. GeoLabs intends to delegate the control body role to the OGC or to an OSPD working group."@en ,
        "Identifiers. The object identifier of an item is its IRI, https://w3id.org/geolabs/ospd/data-formats/<class>/<name>, with <class> one of format or representation. This namespace is not resolved yet. An object identifier never redirects; only a functional identifier may. The identifier of a published item changes only by an explicit decision."@en ,
        "Versions. An addition is an action of type addition, with no classification. A substantive change creates a new item or a new version, linked by rim:supersededBy, with an action classified substantive. A clarifying change keeps the item and its version, with an action classified clarifying. This version rule is specific to the registers of this project and does not come from ISO 19135. The classification correctional is not available. An item is retired by unpublishing it, not by deleting it."@en ,
        "Ce qui est substantiel ici (tableau validé le 2026-11-05, repris tel quel). Substantiel : Media type principal, version de la spécification, fragment de schéma, version de concept réalisée. Clarification : Media type observé ajouté, description reformulée."@fr ,
        "What is substantive here (English rendering of the validated table above). Substantive: the principal media type, the version of the specification, the schema fragment, the realized concept version. Clarifying: an observed media type added, a reworded description."@en ,
        "Proposals. While an item is a proposal, with no control-body decision recorded, it is amended in place, with a classified `rim:RegisterAction`. The substantive rule applies once it has been accepted."@en ,
        "Amendment. df:amendmentAction is the action type of an in-place change to a proposal, an item with no control-body decision recorded. Such an action is always classified, clarifying or substantive: it is the classified rim:RegisterAction of the rule for proposals. This type is specific to this register and will be replaced if the Registered Item Model defines one."@en ,
        "Eligibility. No eligibility criteria for proposers have been set. GeoLabs is the only proposer recorded so far."@en ,
        "Commitments. No commitment to register users has been set."@en ;
    rim:definesSubstantiveChange "A change is substantive when a register user may have to change their data, profiles or processes because of it, or when it changes what an item means. Any other change to an existing item is clarifying." .

# rim:actionType is required and the Registered Item Model has no type for an in-place change of a
# proposal; it lets a register specification define further action types. Defined by
# df:specification, specific to this register.
df:amendmentAction a rim:RegisterActionType , skos:Concept ;
    rdfs:isDefinedBy df: ;
    skos:prefLabel "amendment"@en ;
    skos:definition "An in-place change to a proposal, an item with no control-body decision recorded. Always classified, clarifying or substantive."@en .

df:formatItemClass a rim:RegisterItemClass ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/formatItemClass"^^xsd:anyURI ;
    dct:title "Format" ;
    dct:description "The abstraction every format item of this register shares: an encoding, with its specification, its observed media types, its inferred media types (each with source and justification) and/or a JSON Schema fragment; it realizes no concept version."@en ;
    rim:definedIn df:register ;
    rim:validatedBy df:FormatShape .

df:representationItemClass a rim:RegisterItemClass ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/representationItemClass"^^xsd:anyURI ;
    dct:title "Representation" ;
    dct:description "The abstraction every representation item of this register shares: one data type version of the data-types register, realized in one format."@en ;
    rim:definedIn df:register ;
    rim:validatedBy df:RepresentationShape .

df:geolabs a prov:Organization ;
    dct:title "GeoLabs SARL"@en .

df:registerSystem a rim:RegisterSystem ;
    dct:title "OGC Building Blocks register (bblocks-postprocess, GitHub Pages)"@en .

```


### Ontology of the content plane
The classes df:Format and df:Representation, sub-classes of rim:RegisterItem, and their
properties.

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

#################################################################
# Ontology metadata
#
# The content plane of the OSPD data axis, as a profile of the Registered
# Item Model (ISO 19135:2026). Two classes of register item: df:Format,
# an encoding, which realizes no concept version; df:Representation, which
# realizes one dt:DataTypeVersion of the data-types register and points to
# a df:Format. This register depends on the data-types register, never the
# reverse.
#################################################################

df: a owl:Ontology ;
    owl:imports rim: ;
    dct:title "Data Formats vocabulary" ;
    dct:description "Registered Item Model profile of the content plane: formats, and representations that bind a data type version of the data-types register to a format." ;
    dct:creator "GeoLabs SARL" ;
    dct:license <https://www.apache.org/licenses/LICENSE-2.0> .

df:Format a owl:Class ;
    rdfs:subClassOf rim:RegisterItem ;
    rdfs:isDefinedBy df: ;
    rdfs:label "Format" ;
    rdfs:comment "An encoding of data, with its specification, the media types observed where it is served, and/or a JSON Schema fragment. A format realizes no concept version: it says nothing about what the data means." .

df:Representation a owl:Class ;
    rdfs:subClassOf rim:RegisterItem ;
    rdfs:isDefinedBy df: ;
    rdfs:label "Representation" ;
    rdfs:comment "A data type in a format: realizes (rim:realizes) exactly one dt:DataTypeVersion of the data-types register and points (df:format) to one df:Format. Created when an existing role needs it." .

df:MediaTypeObservation a owl:Class ;
    rdfs:isDefinedBy df: ;
    rdfs:label "Media type observation" ;
    rdfs:comment "A media type under which a format was observed, and where: in an Implementation Profile (tier 3) or in a testbed process description (tier 4)." .

df:format a owl:ObjectProperty ;
    rdfs:subPropertyOf rim:relatedItem ;
    rdfs:isDefinedBy df: ;
    rdfs:label "format" ;
    rdfs:comment "Relates a representation to the format it uses." ;
    rdfs:domain df:Representation ;
    rdfs:range df:Format .

df:observedMediaType a owl:ObjectProperty ;
    rdfs:isDefinedBy df: ;
    rdfs:label "observed media type" ;
    rdfs:comment "A media type under which this format was observed. Adding one is a clarifying change." ;
    rdfs:domain df:Format ;
    rdfs:range df:MediaTypeObservation .

df:mediaType a owl:DatatypeProperty ;
    rdfs:isDefinedBy df: ;
    rdfs:label "media type" ;
    rdfs:domain df:MediaTypeObservation ;
    rdfs:range xsd:string .

df:observedIn a owl:DatatypeProperty ;
    rdfs:isDefinedBy df: ;
    rdfs:label "observed in" ;
    rdfs:comment "Where the media type was observed: implementation-profile (tier 3) or testbed (tier 4)." ;
    rdfs:domain df:MediaTypeObservation ;
    rdfs:range xsd:string .

df:inferredMediaType a owl:ObjectProperty ;
    rdfs:isDefinedBy df: ;
    rdfs:label "inferred media type" ;
    rdfs:comment "A media type of this format that was not observed in an Implementation Profile or on the testbed, but taken from a source: stated by the format's specification, or, when the specification states none, inferred, for instance from its JSON Schema. The record names its source (dct:source) and its justification (dct:description). Adding one is a clarifying change. Widened on 2026-11-10 to the media type a specification states (STAC Item); before, it covered only an inference when the specification states none." ;
    rdfs:domain df:Format ;
    rdfs:range df:MediaTypeInference .

df:MediaTypeInference a owl:Class ;
    rdfs:isDefinedBy df: ;
    rdfs:label "Media type inference" ;
    rdfs:comment "A media type of a format taken from a source rather than observed (df:mediaType): stated by its specification, or inferred; with that source (dct:source) and why (dct:description)." .

df:primaryMediaType a owl:DatatypeProperty ;
    rdfs:isDefinedBy df: ;
    rdfs:label "principal media type" ;
    rdfs:comment "The principal media type of a format; changing it is a substantive change. It is one of the format's recorded media types, observed (df:observedMediaType) or taken from a source (df:inferredMediaType), and that record gives its source (df:PrimaryMediaTypeShape). Set on the STAC Item format only (2026-11-10): application/geo+json, as its specification states." ;
    rdfs:domain df:Format ;
    rdfs:range xsd:string .

df:jsonSchemaFragment a owl:DatatypeProperty ;
    rdfs:isDefinedBy df: ;
    rdfs:label "JSON Schema fragment" ;
    rdfs:comment "The JSON Schema that expresses this format, as a JSON literal; changing it is a substantive change." ;
    rdfs:domain df:Format ;
    rdfs:range rdf:JSON .

df:parameter a owl:ObjectProperty ;
    rdfs:isDefinedBy df: ;
    rdfs:label "parameter" ;
    rdfs:comment "A value the profile that uses this format must supply to complete its JSON Schema fragment (e.g. the regular expression of a pattern-constrained string)." ;
    rdfs:domain df:Format .

df:parameterName a owl:DatatypeProperty ;
    rdfs:isDefinedBy df: ;
    rdfs:label "parameter name" ;
    rdfs:range xsd:string .

df:jsonSchemaKeyword a owl:DatatypeProperty ;
    rdfs:isDefinedBy df: ;
    rdfs:label "JSON Schema keyword" ;
    rdfs:comment "The JSON Schema keyword whose value the parameter supplies." ;
    rdfs:range xsd:string .

df:cwlCustomType a owl:DatatypeProperty ;
    rdfs:isDefinedBy df: ;
    rdfs:label "CWL custom type" ;
    rdfs:comment "The name of the record of the EOAP schemas (string_format.yaml) that carries this format in CWL, documented by the eoap.cct.string-format building block (rdfs:seeAlso)." ;
    rdfs:domain df:Format ;
    rdfs:range xsd:string .

```

## Sources

* [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
* [Registered Item Model (OGC Building Block)](https://ogcincubator.github.io/registered-item-model/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/vocabulary`

