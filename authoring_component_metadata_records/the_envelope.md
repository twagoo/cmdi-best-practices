---
editor: 'Menzo (Header), Oddrun (Resource relations)'
---

## The envelope {#the-envelope}

### Header {#header}

###### E1: Include a MdSelfLink

Include a MdSelfLink that resolves to the CMD record hosted at the CLARIN Centre. Including the MdSelfLink is a requirement for CLARIN B Centres \(see [CE-2013-0095](http://hdl.handle.net/1839/00-DOCS.CLARIN.EU-78) section 6 sub-requirement 7\) as is the support of content negotiation for the MdSelfLink \(see [CE-2013-0095](http://hdl.handle.net/1839/00-DOCS.CLARIN.EU-78) section 7\), this allows both human and machines to see/retrieve the record in its context. The MdSelfLink is also important in the reconstruction of a CMD record \(collection\) hierarchy \(see below\).

###### E2: The MdSelfLink should be a Persistent Identifier \(PID\)

By giving a CMD record a PID and including it in the MdSelfLink it becomes possible for tools that present the records to the user to provide them with a persistent link suitable as a bookmark that will stand the test of time. This is another requirement for CLARIN B Centres \(see [CE-2013-0095](http://hdl.handle.net/1839/00-DOCS.CLARIN.EU-78) section 6 sub-requirement 7\).

###### E3: Include a MdCollectionDisplayName

The MdCollectionDisplayName allows grouping of records, e.g. for display or search, without the need to access or even the existence of an explicit CMD collection record. Including the CLARIN Centre name and a collection name enables users to quickly assess the provenance, scope and context of an individual record. Generic tools, like the VLO, use this information to put a record in context. Use a consistent collection name across records that belong to the same collection and should be presented as such.

###### E4: Include a matching MdProfile

The MdProfile contains the unique identifier of the used profile in the Component Registry. This element is mandatory in CMDI 1.2 but optional in CMDI 1.1. However, it should always be included and it should match with the XSD \(see [X1](/authoring_component_metadata_records/general_xml.md#x1)\). While the reference to the XSD is an absolute URI the MdProfile just needs to contain the identifier, e.g. `clarin.eu:cr1:p_1361876010680`.

### Resource Proxies {#resource-proxies}

###### E5: There should be at least one resource proxy

A CMD record describes one or more \(collections of\) resources. These \(collections of\) resources, where the minimum is one resource or collection, should be linked to the CMD record via a resource proxy. This allows central tools, like the VLO, to show the user the resources related to the metadata. It is also technically possible, but not preferred \(see [CS2](/authoring_component_metadata_records/the_component_section.md#cs2)\), to include the resource URLs/PIDs in the component section, however they should always be available as resource proxies.

###### E6: The URI of a resource proxy should be absolute and resolvable

An absolute URI should be used as the value of ResourceRef. This is certainly true for published CMD records. Internally a centre can use relative URLs, but care should be taken to make them absolute when publishing them to the infrastructure.

Also the URI of a resource proxy should be resolvable, i.e. the resource should be available at that location. However, it might be a protected and thus \(shibboleth-based\) authentication might be required.

#### Metadata {#metadata}

###### E7: “Metadata” type resource proxies should refer to a CMD record

The only metadata format used by CLARIN is CMD, so a metadata resource proxy should refer to a CMD record as should be indicated by the MIME type “application/x-cmdi+xml”.

###### E8: “Metadata” type resource proxies should use PIDs

A CMD record should be available via a PID \(with\(out\) a part identifier\) \(see [E2](#e2-the-mdselflink-should-be-a-persistent-identifier-pid) and [CE-2013-0095](http://hdl.handle.net/1839/00-DOCS.CLARIN.EU-78) section 6 sub-requirement 8\). General tools, like the VLO, use these links among CMD records to reconstruct the collection hierarchy. To be able to do so it is important that the PID used in the metadata resource proxy of a collection record and the MdSelfLink in the referenced CMD record are equal.

#### Resource {#resource}

###### E9: Specify the MIME type of a resource {#e9}

Give the MIME type \(a.k.a. media type\) of the resource. This enables general tools, like the Language Resource Switchboard, to direct users to tools and/or services that can process or display this type of resources. Sometimes the MIME type is too coarse, e.g., for TEI resources, in that case a format variant can be added to fine tune the type. However, the format variant should come from a controlled vocabulary. The MIME type is also part of the HTTP response when resolving the ResourceProxy reference, which should match the MIME type specified.

###### E10: “Resource” type resource proxies should use PIDs

A resource should be available via a PID \(with or without a part identifier\) \(see [CE-2013-0095](http://hdl.handle.net/1839/00-DOCS.CLARIN.EU-78) section 7\).

#### LandingPage {#landingpage}

###### E11: Provide no more than one LandingPage {#e11}

The landing page ResourceProxy takes the user to a page within the web interface of the repository in which the CMD record resides. The landing page usually serves as a starting point for more detailed scrutiny of the metadata, e.g. by displaying core information up front, while providing links to the finer details. There might be multiple interfaces, but general tools, like the VLO, do not have information to choose which one is appropriate. To prevent a possible random selection of the landing page resource proxies, which could provide a confusing user experience, provide no more than one landing page.

#### SearchPage {#searchpage}

###### E12: Provide no more than one one SearchPage {#e12}

The search page resource proxy takes the user to a place where the record/collection/repository can be searched. There might be multiple search interfaces, but general tools, like the VLO, do not have information to choose which one is appropriate. To prevent a possible random selection of the search page resource proxies, which could provide a confusing user experience, provide no more than one search page.

#### SearchService {#searchservice}

###### E13: Provide no more than one SearchService {#e13}

The search service resource proxy enables tools to search the record/collection/repository. There might be multiple search services, but general tools, like the VLO or the FCS aggregator, do not have information to choose which one is appropriate. To prevent a possible random selection of the search service resource proxies or the use of overlapping services where resources might be returned more than once, which could provide a confusing user experience, provide no more than one search service.

###### E14: A SearchService should support the FCS specification {#e14}

The only search API supported by CLARIN is the one specified in the FCS specification.[^1] Any search service included in a CMD record should thus support this specification.

### Journal Proxies {#journal-proxies}

Not used by CLARIN.

### Resource Relations {#resource-relations}

###### E15: Use ResourceRelation to express any significant binary relationships among resources listed in ResourceProxyList {#e15}

Each ResourceRelation instance must reference the two related resources and be defined by a relationship type. Relationship types should be assigned a concept link describing its meaning, see also C12. When deciding which relationships should be explicitly represented, consider relations which may be useful in several usecases. Some examples of typical or relevant relationships between two resources R1 and R2 include: _R1 annotates R2_, _R1 transcribes R2_, _R1 is parallel to R2_ \(e.g. in a parallel corpus listing each language file as separate resources\), and others.

###### E16: Add roles to both relationship participants when considered useful {#e16}

To convey the full nature of the relationship between two resources, it is sometimes desirable to assign roles to the related parties. If so, it is best practice to assign roles to both parties \(not only one\). Moreover, each role should be assigned a concept link to express its meaning, see also [C14](/modelling_component_metadata/components.md#c14).

###### E17: Use ResourceProxy to express partitive relationships between the described resource as a whole and its constituent resources.

If your resource is decomposed into separate parts, each child resource should be listed as a ResourceProxy instance in the ResourceProxyList. For any child resource having its own CMD record, the corresponding ResourceProxy should be of type Metadata, and its ResourceRef should be set to MdSelfLink of its CMD record. See also [E5](#e5-there-should-be-at-least-one-resource-proxy)-[E8](#e8-metadata-type-resource-proxies-should-use-pids).

This top-down approach is the preferred way of describing resource hierarchies, as it is generally supported throughout the core CLARIN infrastructure. See also [Granularity](/common_approachesproblems/granularity.md).

###### E18: IsPartOf may be used to express a partitive relation between the described resource as a whole and a larger resource or collection {#e18}

This is a bottom-up method of describing resource hierarchies, and constitutes an alternative or additional approach to that described in [E17](#e17-use-resourceproxy-to-express-partitive-relationships-between-the-described-resource-as-a-whole-and-its-constituent-resources). So far, IsPartOf is not widely used nor well supported by the CLARIN infrastructure, hence the [E17](#e17-use-resourceproxy-to-express-partitive-relationships-between-the-described-resource-as-a-whole-and-its-constituent-resources) approach should be preferred whenever feasible. See also [Granularity](/common_approachesproblems/granularity.md).

###### E19. Do not use ResourceRelation to relate resources other than those listed in ResourceProxyList {#e19}

Note that ResourceRelation is strictly connected to ResourceProxy in the sense that both resources related by ResourceRelation must be instances of ResourceProxy. Any other relationships, e.g.

* between ResourceProxy instances and the described resource as a whole or other \(external\) resources,
* non-partitive relations between the described resource as a whole and other \(external\) resources, or
* relations between ResourceProxy instances and other entities mentioned in the CMD record, e.g. persons or institutions

must be expressed using suitable components and elements available in the chosen profile, if any. If no applicable mechanism is available in the current profile, consider extending it with additional components, for instance some dedicated relationship component.

### Foreign attributes {#foreign-attributes}

###### E20: Delete foreign attributes before providing

See [X2](/authoring_component_metadata_records/general_xml.md#x2).

[^1]: See [https://www.clarin.eu/content/federated-content-search-clarin-fcs](https://www.clarin.eu/content/federated-content-search-clarin-fcs)

