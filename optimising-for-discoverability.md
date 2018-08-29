## Optimising for discoverability

\[See [CR \#23](https://www.gitbook.com/book/cmdi-taskforce/cmdi-best-practices/changes/23)\]

An important motivation for creating and publishing high quality metadata for resources is that doing so can vastly increase the discoverability of these resources. Metadata generally provides information that is not \(directly\) available from the associated digital object, service, tool or other resource itself, and therefore caters to use cases complementary to _content search_.

Most of the best practices described in this document serve the purpose, either implicitly or explicitly, to improve the discoverability of the described resources. Therefore in general it can be said that following the described best practices as closely as possible is the best way to optimise for discoverability. However in this section we will explicitly assume the perspective of discoverability and focus on a number of salient aspects that either have the potential of strongly affecting discoverability, are a common cause of suboptimal discoverability, or may not be obvious to the average metadata modeller or author.

A few examples of scenarios we consider cases of resource discovery and believe should be recognised and considered in the context of metadata modelling and authoring:

* A user visits a **specific repository** where they may or may not expect to find access to a certain resource, or a resource with certain properties. If successful, the desired resource is provided to the user through the platform that was used to initiate the discovery.
* A user visits a metadata-driven catalogue, search engine or other **platform that aggregates metadata** from multiple sources, such as the [Virtual Language Observatory](https://www.clarin.eu/vlo), and browses or queries the indexed records on basis of a more or less specific set of criteria, eventually reaching a location that provides \(a path to\) access to the actual resource, which may involve one or more intermediate steps including one or more interactions with the 'native' repository (see above) that hosts the resource.
* A user performs a search using a **general purpose search engine** \(such as Google\) that crawls web pages and other online content, using salient keywords that match the metadata and/or content of the resource. Results that lead the user to the resource may include the repository or another search or aggregation platform.
* A resource is **referenced** in a paper, in online content such as a website or blog post, or included in a collection that is consumed by a user, and hence discovered. The reference has to be actionable in some way and provide direct or indirect access to the actual resource in order for the discovery process to be considered successful.

Metadata creators can choose to optimise for one or more types of discovery scenarios.

### Metadata formats and representation

By design, metadata aggregators such as the VLO have a more or less **generic search interface and data model**, which means that in most cases they will not be as well suited for searching for resources in a specific context as search platforms tailored to that context. I.e., repositories with a relatively limited scope in terms of content can harness their 'knowledge' about the contained information and its shape to provide enhanced means of search, exploration and presentation. In fact, many repository solutions have a data schema \(encoded in their database or other data storage facility\) that is optimised for these purposes. In those cases, CMDI or for example Dublin Core metadata is often only made available (exported) as 'secondary' form of representation. In many cases this is an apt solution, that makes it possible to combine the benefits of specificity and generality. However it is also important that the exported metadata is not merely available but actually **fit for aggregation**, which implies a different context than that of the 'native' repository. Factors to keep in mind when designing the export from an internal representation to metadata for harvesting:

* \[sufficient context\]
* \[use of broadly accepted vocabularies\]
* \[SH 2018-07-19:\]\[coverage of categories for the intended harvesting platforms\]
* ...

### Metadata completeness and VLO facets

Providing correct and complete metadata improves discoverability. The more information you provide about your resources and their context, the higher the expected recall for queries that match your data. If you are looking for good representation and discoverability through the VLO, pay attention to its **facets**, which can be considered one of the main entry points into the data aggregated into the VLO. Ideally as many facets are covered as possible by _each metadata record_. Furthermore, a number of non-facet fields are displayed prominently in the search results, in particular a record's **title and description**, as well as licence and availability information. Records that are lacking this essential information not only are harder to find that those which do, but also are less likely to receive a high ranking, even if there is a match to a user's query.

A repository may simply export its metadata to **Dublin Core **. This is one of the requirements of OAI-PMH \[footnote\]. However, one has to be aware that the set of attributes included in 'pure' Dublin Core does not necessarily allow for complete or semantically unambiguous metadata. If you are looking to tune your metadata to one ore more parts of the CLARIN infrastructure, it's worth investigating the option of exporting to a fitting CMDI profile, or to make your own dedicated profile. If this is not an option, you can also consider using the [OLAC extensions](http://www.language-archives.org/OLAC/metadata.html) to enrich your Dublin Core metadata.

Finally, be aware of any context that your repository solution provides that is not directly encoded in the metadata of a single resource. The VLO, and the CLARIN infrastructure in general, will generally assume that a metadata record is self-sufficient. For example, if the name of your organisation is not included in a record, it will also not be associated with the described resources by the VLO. A metadata hierarchy might provide additional context, such as project information, collection details or legal status, but this will not cause this information to be presented in the context of the resource in a salient way unless it is explicitly included in its own metadata record.

To find out how well your metadata record will be represented in the VLO you may consult the **Metadata Curation Module**. Here, you are able to upload your metadata record, browse through a list of available profiles or upload a profile URL in order to obtain a "score" and an overview of facet coverage for the respective profile or file.

### Values and semantics

\[Consider given vocabularies, e.g. resource type \(including links where to find these\)\]

\[Ensure conformity among records of a collection/institution \(e.g. naming conventions\)\]

Facet "collection": If you are preparing a set of records that belong to one collection, this collection can be specified in the CMDI header in each record and thus made findable via the VLO facet. If so, make sure that the collection is named homogeneously accross records so that the collection name will appear only once in the VLO collection facet. [Prefix collection]

\[Modeller's responsibility to avoid ambiguities that can't be resolved technically \(e.g. &lt;date&gt; in very generally named branches: date of what \(creation/description/submission/modification\)?\): naming and most importantly concept/context\]

\[Avoid non-alphanumeric characters in titles \([Discussion \#19](https://www.gitbook.com/book/cmdi-taskforce/cmdi-best-practices/discussions/19)\)\]

### Links and context

\[Importance of landing page\]

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNzQxNzMyOTZdfQ==
-->