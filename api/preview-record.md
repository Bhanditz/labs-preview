---
layout: "api-page2"
title: Record
published: true
excerpt: Retrieving a single record from the dataset
---

* TOC
{:toc}

Retrieve a single record from the Europeana dataset. On the relation between EDM and records read [this](http://labs.europeana.eu/api/preview-data-hierarchy/#edm-and-records).

    http://beta.europeana.eu/v2/record/[recordID].json
    
## Request

| Parameter | Datatype | Description |
|:-------------|:-------------|:-----|
| recordID | String | [Europeana ID](http://labs.europeana.eu/api/preview-data-hierarchy/#identifying-records) of the record to retrieve. |
| callback | String | Name of a [client side callback function](http://labs.europeana.eu/api/preview-search/#callback-function). |


## Response

| Field | Datatype | Description |
|:-------------|:-------------|:-----|
| object | [Object](#object) | The object representing the EDM metadata record. (see the note above) |
| similarItems | Array([item](http://labs.europeana.eu/api/preview-search/#item)) | The collection of metadata records similar to the current one. Available when profile parameter value is set to **similar**. The structure of each record is the same as the structure of the items collection returned by the [search](http://labs.europeana.eu/api/preview-search) method. |


### object

| Field | Datatype | Description |
|:-------------|:-------------|:-----|
| about | String | [Europeana ID](http://labs.europeana.eu/api/preview-data-hierarchy/#identifying-records) of the returned object.|
| agents | Array([Agent](#edm-agent)) | A collection of EDM Agent objects contextually related to the object. Find more in the EDM Definition. |
| aggregations | Array([Aggregation](#edm-aggregation)) | A collection of EDM Aggregation objects related to the object. Find more in the EDM Definition. |
| concepts | Array([Concept](#edm-concept)) | A collection of EDM Concept objects contextually related to the object. Find more in the EDM Definition. |
| country | Array(String) | TBD |
| europeanaAggregation | Array([EuropeanaAggregation](#edm-EuropeanaAggregation)) | A collection of EDM Europeana Aggregation objects related to the object. Find more in the EDM Definition.|
| europeanaCollectionName | Array(String) | A collection of names of the datasets the object belongs to. |
| europeanaCompleteness | Number | A number between 0 and 10 representing the metadata quality of the object. |
| language | Array(String) | A singleton collection with the language of the object. |
| optOut | Boolean | Flag indicating whether the provider allowed retrieval of thumbnail of the record |
| places | Array([Place](edm_#Place)) | A collection of EDM Place objects contextually related to the object. Find more in the EDM Definition. |
| provider | Array(String) | A singleton collection with the name of the organization that delivered this object to Europeana. |
| providedCHOs | Array([ProvidedCHO](#edm-ProvidedCHO)) | A collection of Provided Cultural Heritage Objects related to the record. Find more in the EDM Definition. |
| proxies | Array([Proxy](#Proxy)) | A collection of proxy objects for Provided Cultural Heritage Objects. Find more in the EDM Definition. |
| timespans | Array([TimeSpan](#TimeSpan)) | A collection of EDM TimeSpan objects contextually related to the object. Find more in the EDM Definition. |
| timestamp_created_epoch | Number | Unix time of the date when the object was created. |
| timestamp_update_epoch | Number | Unix time of the date when the object was last updated. |
| timestamp_created | String | ISO 8601 format of the date when the object was created. |
| timestamp_update | String | ISO 8601 format of the date when the object was last updated.|
| title | Array(String) | A collection with the main and alternative titles of the object. |
| type | String | The type of the object (see the TYPE facet) TBD: add link |
| year | Array(String) |  |

### EDM Aggregation

An EDM Aggregation object. The set of resources related to a single cultural heritage object that collectively represent that object in Europeana. Such set consists of: all descriptions about the object that Europeana collects from (possibly different) content providers, including thumbnails and other forms of abstractions, as well as of the description of the object Europeana builds. Find more in the EDM Definition.

| Field | Qualified Name | Datatype | Description |
|:-------------|:-------------|:-----|:-----|
| about | rdf:about | String | URI of the aggregation |
| edmDataProvider | edm:dataProvider | LangMap | The name or identifier of the data provider of the object (i.e. the organisation providing data to an aggregator). |
| edmIsShownBy | edm:isShownBy | String | The URL of a web view of the object. |
| edmIsShownAt | edm:isShownAt | String | The URL of a web view of the object in full information context. |
| edmObject | edm:object | String | The URL of a representation of the CHO which will be used for generating previews for use in the Europeana portal. This may be the same URL as edm:isShownBy. |
| edmProvider | edm:provider | LangMap | The name or identifier of the provider of the object (i.e. the organisation providing data directly to Europeana). |
| edmRights | edm:rights | LangMap | The rights statement that applies to the digital representation as given (for example) in edm:object or edm:isShownAt/By, when these resources are not provided with their own edm:rights. |
| edmUgc | edm:ugc | String | This is a mandatory property for objects that are user generated or user created that have been collected by crowdsourcing or project activity.  The property is used to identify such content and can only take the value “true” (lower case). |
| dcRights | dc:rights | LangMap | Information about rights held in and over the resource. |
| hasView | edm:hasView | Array(String) | The URL of a web resource which is a digital representation of the CHO.  This may be the source object itself in the case of a born digital cultural heritage object. |
| aggregatedCHO | edm:aggregatedcHO | String | The identifier of the source object e.g. the Mona Lisa itself.  This could be a full linked open data URI or an internal identifier. |
| aggregates | ore:aggregates | Array(String) | This is a container element which includes all relevant information that otherwise cannot be mapped to another element in the ESE. |
| edmUnstored | edm:unstored | Array(String) | This property should not be used and is only included here for backward compatibility with ESE. |
| webResources | edm:WebResource | Array([WebResource](#WebResource)) | Information Resources that have at least one Web Representation and at least a URI. |

### EDM EuropeanaAggregation 

An EDM Europeana Aggregation object. The set of resources related to a single cultural heritage object that collectively represent that object in Europeana. Such set consists of: all descriptions about the object that Europeana collects from (possibly different) content providers, including thumbnails and other forms of abstractions, as well as of the description of the object Europeana builds.

| Field | Qualified Name | Datatype | Description |
|:-------------|:-------------|:-----|:-----|
|about|     rdf:about|     String|     URI of the europeanaAggregation|
|webResources|     edm:WebResources|     Array ([WebResource](#WebResource))|     A collection of webResource objects|
|aggregatedcHO|     edm:aggregatedcHO|     String|     The ID of the record corresponding to the CHO of this aggregation|
|aggregates|     ore:aggregates|     Array (String)|     Aggregations, by definition, aggregate resources. The ore:aggregates relationship expresses that the object resource is a member of the set of aggregated resources of the subject (the Aggregation). This relationship between the Aggregation and its Aggregated Resources is thus more specific than a simple part/whole relationship, as expressed by dcterms:hasPart for example.|
|dcCreator|     dc:creator|     LangMap|     A creator definitions. This field has always the value Europeana |
|edmLandingPage|     edm:landingPage|     String|     This property captures the relation between an aggregation representing a cultural heritage object and the Web resource representing that object on the provider’s web site. |
|edmIsShownBy|     edm:isShownBy|     String|     An unambiguous URL reference to the digital object on the provider’s web site in the best available resolution/quality. |
|edmHasView|     edm:hasView|     Array (string)|     This property relates a ORE aggregation about a CHO with a web resource providing a view of that CHO. Examples of view are: a thumbnail, a textual abstract and a table of contents. |
|edmCountry|     edm:country|     LangMap|     This is the name of the country in which the Provider is based or “Europe” in the case of Europe-wide projects.|
|edmLanguage|     edm:language|     LangMap|     A language assigned to the resource with reference to the Provider.|
|edmRights|     edm:rights|     LangMap|     Information about copyright of the digital object as specified by isShownBy and isShownAt.|
|edmPreview|     edm:preview|     String|     |


### EDM ProvidedCHO

An EDM Provided CHO (Cultural Heritage Object) object. This class comprises the Cultural Heritage objects that Europeana collects descriptions about.

| Field | Qualified Name | Datatype | Description |
|:-------------|:-------------|:-----|:-----|
|about|     rdf:about|     String|     Defines the resource being described |
|owlSameAs|     owl:sameAs|     Array (String)|     owl:sameAs links an individual to an individual. Such an owl:sameAs statement indicates that two URI references actually refer to the same thing: the individuals have the same "identity". |


### EDM Proxy 

ORE* Proxy. Europeana uses proxies as place-holders for cultural heritage objects within aggregations (whether Europeana aggregations or not) to the end of making assertions about the corresponding cultural heritage objects while distinguishing the provenance of these assertions. This class is used to create aliases of cultural heritage objects to which descriptions are attached. This allows Europeana to keep track of provenance of descriptions. See chapter 6.1 Introducing proxies in the EDM primer

* ORE stands for Open Archives Initiative Object Reuse and Exchange

| Field | Qualified Name | Datatype | Description |
|:-------------|:-------------|:-----|:-----|
| about | rdf:about | String | Defines the resource being described |
| dcContributor | dc:contributor | LangMap | An entity responsible for making contributions to the resource. |
| dcCoverage | dc:coverage | LangMap | The spatial or temporal topic of the resource, the spatial applicability of the resource, or the jurisdiction under which the resource is relevant. |
| dcCreator | dc:creator | LangMap | An entity primarily responsible for making the resource. This may be a person, organisation or a service. |
| dcDate | dc:date | LangMap | A point or period of time associated with an event in the lifecycle of the resource. |
| dcDescription | dc:description | LangMap | A description of the resource. |
| dcFormat | dc:format | LangMap | The file format, physical medium or dimensions of the resource. |
| dcIdentifier | dc:identifier | LangMap | An unambiguous reference to the resource within a given context. |
| dcLanguage | dc:language | LangMap | A language of the resource |
| dcPublisher | dc:publisher | LangMap | An entity responsible for making the resource available. Examples of a publisher include a person, an organisation and a service. |
| dcRelation | dc:relation | LangMap | The name or identifier of a related resource, generally used for other related CHOs. The recommended best practice is to identify the resource using a formal identification scheme. |
| dcRights | dc:rights | LangMap | Name of the rights holder of the CHO or more general rights information.  (Note that the controlled edm:rights property relates to the digital objects and applies to the edm:WebResource and/or edm:Aggregation). |
| dcSource | dc:source | LangMap | A related resource from which the described resource is derived in whole or in part, i.e. the source of the original CHO. |
| dcSubject | dc:subject | LangMap | The topic of the resource. |
| dcTitle | dc:title | LangMap | A name given to the resource. Typically, a Title will be a name by which the resource is formally known. |
| dcType | dc:type | LangMap | The nature or genre of the resource. Type includes terms describing general categories, functions, genres, or aggregation levels for content. |
| dctermsAlternative | dcterms:alternative | LangMap | An alternative name for the resource. This can be any form of the title that is used as a substitute or an alternative to the formal title of the resource including abbreviations or translations of the title. |
| dctermsConformsTo | dcterms:conformsTo | LangMap | An established standard to which the described resource conforms. |
| dctermsCreated | dcterms:created | LangMap | Date of creation of the resource. |
| dctermsExtent | dcterms:extent | LangMap | The size or duration of the resource. |
|dctermsHasFormat|     dcterms:hasFormat|     LangMap|     A related resource that is substantially the same as the pre-existing described resource, but in another format.|
|dctermsHasPart|     dcterms:hasPart|     LangMap|     A related resource that is included either physically or logically in the described resource.|
|dctermsHasVersion|     dcterms:hasVersion|     LangMap|     A related resource that is a version, edition, or adaptation of the described resource. Changes in version imply substantive changes in content rather than differences in format.|
|dctermsIsFormatOf|     dcterms:isFormatOf|     LangMap|     A related resource that is substantially the same as the described resource, but in another format.|
|dctermsIsPartOf|     dcterms:isPartOf|     LangMap|     A related resource in which the described resource is physically or logically included.|
|dctermsIsReferencedBy|     dcterms:isReferencedBy|     LangMap|     A related resource that references, cites, or otherwise points to the described resource.|
|dctermsIsReplacedBy|     dcterms:isReplacedBy|     LangMap|     A related resource that supplants, displaces, or supersedes the described resource.|
|dctermsIsRequiredBy|     dcterms:isRequiredBy|     LangMap|     A related resource that requires the described resource to support its function, delivery or coherence.|
|dctermsIssued|     dcterms:issued|     LangMap|     Date of formal issuance (e.g., publication) of the resource.|
|dctermsIsVersionOf|     dcterms:isVersionOf|     LangMap|     A related resource of which the described resource is a version, edition, or adaptation. Changes in version imply substantive changes in content rather than differences in format.|
|dctermsMedium|     dcterms:medium|     LangMap|     The material or physical carrier of the resource.|
|dctermsProvenance|     dcterms:provenance|     LangMap|     A statement of any changes in ownership and custody of the resource since its creation that are significant for its authenticity, integrity and interpretation. This may include a description of any changes successive custodians made to the resource.|
|dctermsReferences|     dcterms:references|     LangMap|     A related resource that is referenced, cited, or otherwise pointed to by the described resource.|
|dctermsReplaces|     dcterms:replaces|     LangMap|     A related resource that is supplanted, displaced, or superseded by the described resource.|
|dctermsRequires|     dcterms:requires|     LangMap|     A related resource that is required by the described resource to support its function, delivery or coherence.|
|dctermsSpatial|     dcterms:spatial|     LangMap|     Spatial characteristics of the resource.|
|dctermsTOC|     dcterms:tableOfContents|     LangMap|     Table Of Contents. A list of subunits of the resource.|
|dctermsTemporal|     dcterms:temporal|     LangMap|     Temporal characteristics of the resource.|
|edmCurrentLocation|     edm:currentLocation|     String|     The geographic location and/or name of the repository, building, site, or other entity whose boundaries presently include the resource.
|edmHasMet|     edm:hasMet|     LangMap|     edm:hasMet relates a resource with the objects or phenomena that have happened to or have happened together with the resource under consideration. We can abstractly think of history and the present as a series of “meetings” between people and other things in space-time. Therefore we name this relationship as the things the object “has met” in the course of its existence. These meetings are events in the proper sense, in which other people and things participate in any role.|
|edmHasType|     edm:hasType|     LangMap|     This property relates a resource with the concepts it belongs to in a suitable type system such as MIME or any thesaurus that captures categories of objects in a given field (e.g., the “Objects” facet in Getty’s Art and Architecture Thesaurus). It does not capture aboutness.|
|edmIncorporates|     edm:incorporates|     Array (String)|     This property captures the use of some resource to add value to another resource. Such resources may be nested, such as performing a theater play text, and then recording the performance, or creating an artful edition of a collection of poems or just aggregating various poems in an anthology.|
|edmIsDerivativeOf|     edm:isDerivativeOf|     Array (String)|     This property captures a narrower notion of derivation than edm:isSimilarTo, in the sense that it relates a resource to another one, obtained by reworking, reducing, expanding, parts or the whole contents of the former, and possibly adding some minor parts.|
|edmIsNextInSequence|     edm:isNextInSequence|     String|     edm:isNextInSequence relates two resources S and R that are ordered parts of the same resource A, and such that S comes immediately after R in the order created by their being parts of A. |
|edmIsRelatedTo|     edm:isRelatedTo|     LangMap|     edm:isRelatedTo is the most general contextual property in EDM. Contextual properties have typically to do either with the things that have happened to or together with the object under consideration, or what the object refers to by its shape, form or features in a figural or encoded form.|
|edmIsRepresentationOf|     edm:isRepresentationOf|     String|     This property associates a resource to another resource that it represents.|
|edmIsSimilarTo|     edm:isSimilarTo|     Array (String)|     The most generic derivation property, covering also the case of questionable derivation. Is Similar To asserts that parts of the contents of one resource exhibit common features with respect to ideas, shapes, structures, colors, words, plots, topics with the contents of the related resource.|
|edmIsSuccessorOf|     edm:isSuccessorOf|     Array (String)|     This property captures the relation between the continuation of a resource and that resource. This applies to a story, a serial, a journal etc. No content of the successor resource is identical or has a similar form with that of the precursor. The similarity is only in the context, subjects and figures of a plot. Successors typically form part of a common whole – such as a trilogy, a journal, etc. |
|edmRealizes|     edm:realizes|     Array (String)|     This property describes a relation between a physical thing and the information resource that is contained in it, visible at it or otherwise carried by it, if applicable. |
|edmType|     edm:type|     String|     The Europeana material type of the resource. All digital objects in Europeana have to be classified as one of the five Europeana material types using upper case letters: TEXT, IMAGE, SOUND, VIDEO or 3D. |
|edmRights|     edm:rights|     LangMap|     Information about copyright of the digital object as specified by isShownBy and isShownAt.|
|edmWasPresentAt|     edm:wasPresentAt|     Array (String)|     This property associates the people, things or information resources with an event at which they were present.|
|europeanaProxy|     |     Boolean|     Flag whether the proxy is an Europeana proxy. See chapter 6.2 Europeana proxies and data enrichment in the EDM primer|
|proxyFor|     ore:proxyFor|     String|     Proxy objects are used to represent a resource as it is aggregated in a particular aggregation. The ore:proxyFor relationship is used to link the proxy to the aggregated resource it is a proxy for. The subject of the relationship is a proxy object, and the object of the relationship is the aggregated resource.|
|proxyIn|     ore:proxyIn|     Array (String)|     Proxy objects must also link to the aggregation in which the resource being proxied is aggregated. The ore:proxyIn relationship is used for this purpose. The subject of the relationship is a proxy object, and the object of the relationship is the aggregation.|


### EDM WebResource

An EDM WebResource object.

| Field | Qualified Name | Datatype | Description |
|:-------------|:-------------|:-----|:-----|
| about | rdf:about | String | URI of the webResource |
| webResourceDcRights | dc:rights | LangMap | Free text information about the rights in this object. |
| webResourceEdmRights | edm:rights | LangMap | The value in this element will indicate the usage and access rights that apply to this digital representation. The rights statement specified at the level of the web resource will ‘override’ the statement specified at the level of the aggregation. The value in this element is a URI taken from the set of those defined for use in Europeana.  A list of these can be found at [http://pro.europeana.eu/web/available-rights-statements](http://pro.europeana.eu/web/available-rights-statements). |
| dcDescription | dc:description | LangMap | An account or description of this digital representation. |
| dcFormat | dc:format | LangMap | The file format, physical medium or dimensions of the resource. |
| dcSource | dc:source | LangMap | A related resource from which the web resource is derived in whole or in part. |
| dctermsExtent | dcterms:extent | LangMap | The size or duration of the digital resource. |
| dctermsIssued | dcterms:issued | LangMap | Date of formal issuance (e.g., publication) of the resource. |
| dctermsConformsTo | dcterms:conformsTo | LangMap | An established standard to which the web resource conforms. |
| dctermsCreated | dcterms:created | LangMap | Date of creation of the web resource. |
| dctermsIsFormatOf | dcterms:isFormatOf | LangMap | A related resource that is substantially the same as the described resource, but in another format. |
| dctermsHasPart | dcterms:hasPart | LangMap | A related resource that is included either physically or logically in the web resource. |
| isNextInSequence | edm:isNextInSequence | String | Where one CHO has several web resources, shown by multiple instances of the edm:hasView property on the ore:Aggregation this property can be used to show the sequence of the objects.  Each web resource (apart from the first in the sequence) should use this property to give the URI of the preceding resource in the sequence. |
| edmCodecName | edm:codecName | String | The name of a device or computer program capable of encoding or decoding a digital data stream or signal, e.g. h264 | 
| ebucoreHasMimeType | ebucore:hasMimeType | String | The main MIME type as defined by IANA: e.g. image/jpeg |
| ebucoreFileByteSize | ebucore:fileByteSize | Integer | The size of a media file in bytes |
| duration | ebucore:duration | String | The duration of a media file in ms |
| ebucoreWidth | ebucore:width | Integer | The width of a media file in pixels | 
| ebucoreHeight | ebucore:height | Integer | The height of a media file in pixels |
| edmSpatialResolution | edm:spatialResolution | String | The spatial resolution of a media resource |
| ebucoreSampleSize | ebucore:sampleSize | String | The size of an audio sample in bits. Also called bit depth |
| ebucoreSampleRate | ebucore:sampleRate | String | The frequency at which audio is sampled per second. Also called sampling rate |
| ebucoreBitRate | ebucore:bitRate | String | To provide the bitrate at which the MediaResource can be played in kilobits/second |
| ebucoreFrameRate | ebucore:frameRate | String | The frame rate of the video signal in frame per second | 
| edmHasColorSpace | edm:hasColorSpace | String | Whether an image is a coloured image | 
| ebucoreOrientation | ebucore:orientation | String | The orientation of a Document or an Image i.e. landscape or portrait | 
| ebucoreAudioChannelNumber | ebucore:audioChannelNumber | String | The total number of audio channels contained in the MediaResource | 

### Contextual resources

#### EDM Agent

An EDM Agent object. This EDM Agent class comprises people, either individually or in groups, who have the potential to perform intentional actions for which they can be held responsible. Find more in the EDM Definition.


| Field | Qualified Name | Datatype | Description |
|:-------------|:-------------|:-----|:-----|
| about | rdf:about | String | The URI of the object, usually a DBpedia URL. |
| prefLabel | skos:prefLabel | LangMap | The preferred form of the name of the agent.|
| altLabel | skos:altLabel | LangMap | Alternative forms of the name of the agent.|
| hiddenLabel |  skos:hiddenLabel | LangMap | SKOS hidden lexical label. (Accessible to text-based indexing and search applications, but not visible otherwise) |
| note | skos:note | LangMap | A note about the agent e.g. biographical notes. |
| begin | edm:begin | LangMap | The date the agent was born/established. |
| end | edm:end | LangMap | The date the agent died/terminated. |
| edmWasPresentAt | edm:wasPresentAt | Array(String) | Consult the EDM Definition. |
| edmHasMet | edm:hasMet | LangMap | Reference to another entity which the agent has “met” in a broad sense. For example a reference to a Place class. |
| edmIsRelatedTo | edm:isRelatedTo | LangMap | Reference to other entities, particularly other agents, with whom the agent is related in a generic sense. |
| owlSameAs | owl:sameAs | Array(String) | Another URI of the same agent. |
| foafName | foaf:name | LangMap | The name of the agent as a simple textual string. |
| dcDate | dc:date | LangMap | A significant date associated with the agent. |
| dcIdentifier | dc:identifier | LangMap | An identifier of the agent. |
| rdaGr2DateOfBirth | rdaGr2:dateOfBirth | LangMap | The date the agent (person) was born. |
| rdaGr2DateOfDeath | rdaGr2:dateOfDeath | LangMap | The date the agent (person) died. |
| rdaGr2DateOfEstablishment | rdaGr2:dateOfEstablishment | LangMap | The date on which the agent (corporate body) was established or founded. |
| rdaGr2DateOfTermination | rdaGr2:dateOfTermination | LangMap | The date on which the agent (corporate body) was terminated or dissolved. |
| rdaGr2Gender | rdaGr2:gender | LangMap | The gender with which the agent identifies. |
| rdaGr2ProfessionOrOccupation | rdaGr2:professionOrOccupation | LangMap | The profession or occupation in which the agent works or has worked. |
| rdaGr2BiographicalInformation | rdaGr2:biographicalInformation | LangMap | Information pertaining to the life or history of the agent. |


#### EDM Concept

A [SKOS](http://www.w3.org/2004/02/skos/) Concept. A SKOS concept can be viewed as an idea or notion; a unit of thought. All elements of this class belong to the skos namespace.

| Field | Qualified Name | Datatype | Description |
|:-------------|:-------------|:-----|:-----|
| about | rdf:about | String | Defines the resource being described |
| prefLabel | skos:prefLabel | LangMap | The preferred form of the name of the concept. |
| altLabel | skos:altLabel | LangMap | Alternative forms of the name of the concept. |
| hiddenLabel | skos:hiddenLabel | LangMap | A hidden lexical label, represented by means of the skos:hiddenLabel property, is a lexical label for a resource, where a KOS designer would like that character string to be accessible to applications performing text-based indexing and search operations, but would not like that label to be visible otherwise. |
| note | skos:note | LangMap | Information relating to the concept. |
| broader | skos:broader | Array(String) | The identifier of a broader concept in the same thesaurus or controlled vocabulary. |
| narrower | skos:narrower | Array(String) | The identifier of a narrower concept. |
| related | skos:related | Array(String) | The identifier of a related concept. |
| broadMatch | skos:broadMatch | Array(String) | The identifier of a broader matching concepts from other concept schemes. |
| narrowMatch | skos:narrowMatch | Array(String) | The identifier of a narrower matching concepts from other concept schemes. |
| exactMatch | skos:exactMatch | Array(String) | The identifier of exactly matching concepts from other concept schemes. |
| relatedMatch | skos:relatedMatch | Array(String) | The identifier of a related matching concepts from other concept schemes. |
| closeMatch | skos:closeMatch | Array(String) | The identifier of close matching concepts from other concept schemes. |
| notation | skos:skosnotation | LangMap | The notation in which the concept is represented.  This may not be words in natural language for some knowledge organisation systems e.g. algebra. |
| inScheme | skos:inScheme | Array(String) | The URI of a concept scheme. |


#### EDM Place

An EDM Place object - "extent in space, in particular on the surface of the earth, in the pure sense of physics: independent from temporal phenomena and matter" (CIDOC CRM).

| Field | Qualified Name | Datatype | Description |
|:-------------|:-------------|:-----|:-----|
| about | rdf:about | String | Defines the resource being described |
| prefLabel | skos:prefLabel | LangMap | The preferred form of the name of the place. |
| altLabel | skos:altLabel | LangMap | Alternative forms of the name of the place. |
| hiddenLabel | skos:hiddenLabel | LangMap | A hidden lexical label, represented by means of the skos:hiddenLabel property, is a lexical label for a resource, where a KOS designer would like that character string to be accessible to applications performing text-based indexing and search operations, but would not like that label to be visible otherwise. |
| note | skos:note | LangMap | Information relating to the place. |
| isPartOf | dcterms:isPartOf | LangMap | Reference to a place that the described place is part of. |
| latitude | wgs84:lat | Number | The latitude of a spatial thing (decimal degrees). |
| longitude | wgs84:long | Number | The longitude of a spatial thing (decimal degrees). |
| altitude | wgs84:alt | Number | The altitude of a spatial thing (decimal metres above the reference). |
| position | wgs84:lat_long | Object | A comma-separated representation of a latitude, longitude coordinate. |
| dcTermsHasPart | dcterms:hasPart | LangMap | Reference to a place that is part of the place being described. |
| owlSameAs | owl:sameAs | Array(String) | URI of a Place. |

#### EDM Timespan

An EDM Timespan object.

| Field | Qualified Name | Datatype | Description |
|:-------------|:-------------|:-----|:-----|
| about | rdf:about | String | Defines the resource being described. |
| prefLabel | skos:prefLabel | LangMap | The preferred form of the name of the timespan or period. |
| altLabel | skos:altLabel | LangMap | Alternative forms of the name of the timespan or period. |
| hiddenLabel | skos:hiddenLabel | LangMap | A hidden lexical label, represented by means of the skos:hiddenLabel property, is a lexical label for a resource, where a KOS designer would like that character string to be accessible to applications performing text-based indexing and search operations, but would not like that label to be visible otherwise. |
| note | skos:note | LangMap | Information relating to the timespan or period. |
| begin | edm:begin | LangMap | The date the timespan started. |
| end | edm:end | LangMap | The date the timespan finished. |
| isPartOf | dcterms:isPartOf | LangMap | Reference to a timespan of which the described timespan is a part. |
| dctermsHasPart | dcterms:hasPart | LangMap | Reference to a timespan which is part of the described timespan. |
| owlSameAs | owl:sameAs | Array(String) | The URI of a timespan. |
