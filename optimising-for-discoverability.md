## Optimising for discoverability

\[See [CR \#23](https://www.gitbook.com/book/cmdi-taskforce/cmdi-best-practices/changes/23)\]

An important advantage, if not the primary reason for creating metadata for resources and publishing it, is that it can vastly increase the discoverability of these resources. Metadata generally provides information that is not \(directly\) available in the digital object, service, tool or other resource and therefore caters to a use case that is complementary to _content search_.

Most of the best practices described in this document serve the purpose, either implicitly or explicitly, to improve the discoverability of the described resources. Therefore in general it can be said that following the described best practices as closely as possible is the best way to optimise for discoverability. However in this section we will explicitly take the discoverability perspective and focus on a number of salient aspects that either have the potential to strongly affect discoverability, are a common cause of suboptimal discoverability, or may not be obvious to the average metadata modeller or author.

To provide some context, we will first enumerate a number of possible types of scenarios that we consider cases of resource discovery:

* A user visits a **specific repository** where they may or may not expect to find access to a certain resource, or a resource with certain properties. If successful, the desired resource is provided to the user through the platform that was used to initiate the discovery.
* A users visits a metadata-driven catalogue, search engine or other **platform that aggregates metadata** from multiple sources such as the [VLO](https://www.clarin.eu/vlo), and browses or queries the indexed records on basis of a more or less specific set of criteria, eventually ending up at a place that provides \(a path to\) access to the actual resource, which may involve one or more intermediate steps including the 'native' repository that hosts the resource.
* A user performs a search using a **general purpose search engine** \(such as Google\) that crawls web pages and other online content, using salient keywords that match the metadata and/or content of the resource.
* A resource is **referenced** in a paper, in online content such as a website or blog post, or included in a collection that is consumed by a user, and hence discovered.

### Metadata formats and representation

Keep in mind that the VLO and other metadata aggregators by design have a more or less generic search interface and data projection, which means that in most cases they will not be as well suited for searching for resources in a specific context as search platforms tailored to that context. Repositories with a more limited scope \(or set of scopes\) can harness their 'knowledge' about the contained data to provide enhanced search and presentation features. Many repository solutions have a data schema \(encoded in their database or other data storage facility\) is optimised for these purposes. In those cases, CMDI or Dublin Core metadata is exported as a 'secondary' representation. In general this is a good solution, that allows for combining the benefits of specificity and generality. However it is important that the exported metadata is fit for aggregation, which implies a different context than that of the 'native' repository. Factors to keep in mind when designing the export from an internal representation to metadata for harvesting:

* \[sufficient context\]
* \[use of broadly accepted vocabularies\]
* ...

### Metadata completeness and VLO facets

\[Attend to all facets \(search facets and display facets -- e.g. make sure a title of a resource is always provided\)\]

\[Dublin core is not necessarily complete!\]

\[Self-sufficiency of metadata records, take extra care in case of hierarchies\]

### Values and semantics

\[Consider given vocabularies, e.g. resource type \(including links where to find these\)\]

\[Ensure conformity among records of on collection/institution \(e.g. naming conventions\)\]

\[Avoid ambiguities in modelling that can't be resolved technically \(e.g. &lt;date&gt; in very generally named branches\)\]

\[Avoid non-alphanumeric characters in titles \([Discussion \#19](https://www.gitbook.com/book/cmdi-taskforce/cmdi-best-practices/discussions/19)\)\]

### Links and context

\[Importance of landing page\]

