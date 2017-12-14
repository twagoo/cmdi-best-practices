---
editor: 'Twan (Components), Susanne (Vocabularies), Menzo (Concepts)'
---

Components

### Modelling principles {#modelling-principles}

###### C1: Provide detailed documentation

\[priority: medium\] \[_TODO: partially check: CMDValidate_\]

There are various places in a component or profile specification that can be used to document your definitions. The _description_ of a component or profile \(at the very top of the Component Editor\) should be used to summarise its context and usage scenario as envisioned by the modeller. The best way to communicate the _semantics_ of the components, elements and attributes within a specification is by means of a well chosen concept link \(see [section](#concepts) below\). The “_Documentation”_ fields that are also available for all of these should contain more 'operational' information, for example where or how to obtain an appropriate value or what 'soft' constraints or guidelines apply that are not covered by the value scheme or cardinality of the documented item. It can also be used to clarify the semantics in case the best fitting concept is too broad or no matching concept can be found.

### Naming {#naming}

###### C2: Components, element and attribute names should be in English

\[priority: medium\]

Since English is the de facto standard language within CLARIN, and most components and profiles are already defined using English names for components, elements and attributes, it is considered best practice to use English for any new component or profile. This contributes to reusability since it is not desirable for profiles or components to be defined in multiple languages. Moreover, metadata creators are most likely to accept or prefer profiles defined using English constituents.

Note that using English names for your components, elements and attributes does not mean that the values necessarily have to be in English. CMDI has explicit support for multilinguality; see the section on [Multilingual metadata](../common_approachesproblems/multilingual_metadata.md).

###### C3: Be verbose, avoid abbreviations and acronyms

\[priority: low\]

When naming elements, attributes and in particular components, be verbose to make sure any metadata modeller or creator understands their purpose. For example "SignLanguageCorpus" is more likely to be understood than "SL-Corpus". Some very common and generally understood abbreviations can be used, such as "info" for information or "param" for parameter.

To some degree, exceptions can also be made for the names of projects or institutions, in particular if the abbreviation constitutes the common reference to such an entity and the full name is rather long \(e.g. "Institut für Deutsche Sprache" versus IDS\). In general, this only applies to the profile level. Reusable components should be defined to be reusable across institutions and projects and the naming should reflect that.

The same goes for formats or standards that are referenced, for example in the case of a CMDI profile that models the OLAC or MODS format. In such cases, it is strongly recommended to include a fully expanded version of the abbreviated name in the component description or element/attribute documentation.

###### C4: Avoid project specific terminology

\[priority: medium\]

Unless strictly necessary, do not use terminology or name variations that link a component or one of its constituents to your project. If you create an extended version of an existing component, for example by adding an element or attribute, do not include your project name in the name of your new component unless the adaptation completely restricts its usage to the context of your project. You can use the 'group' property of component to distinguish new components from similarly named existing ones, and include the name of your project in there, if desired.

#### Naming patterns {#naming-patterns}

###### C5: Aim for a uniform naming pattern but don't let it stand in the way of using existing components

\[priority: low\] \[_TODO: partially check: CMDValidate_\]

As a metadata modeller, you will come across various naming patterns. By following the naming pattern recommendations below you have the best chance of reaching a largely uniform style within your components and profiles. However, when looking for existing components to use there is a good chance that you will come across deviating naming patterns. Although less aesthetically pleasing, this should not prevent you from reusing a specific component. When creating a new version of an existing component or profile \(for example adding elements that you require but are absent from the original\) you may want to consider fixing the naming style to match the recommendation below.

The most important thing is to use a naming pattern that is as consistent as possible across your profile and component definitions. This may mean that the best choice is to adopt an existing ‘style’ based on the components you are reusing or recycling. In other cases, we suggest using "UpperCamelCase" for components \(starting with an uppercase letter\) and “lowerCamelCase” \(starting with lowercase\) for elements and attributes, then capitalise every subsequent first character of the individual words in a name. Whitespace is not allowed. Avoid alternative styles such as "snake case" \(for example "Example\_Profile\_Instance"\) and "train case" \("Example-Profile-Instance"\). Acronyms can be separated from the rest of a name for readability with a hyphen, for example "LAT-SignLanguageSession".

### Constraints and value schemes {#constraints-and-value-schemes}

###### C6: Discourage empty string values {#c6}

\[priority: low\] \[_TODO: check: CMDI Instance Validator_\]

When making an element or attribute mandatory and give it the simple type "string", this should imply the requirement of a non-empty value. In other words, do not encourage the creation of empty elements or attributes in the metadata but rather consider making an element or attribute optional.

###### C7: Use an appropriately restrictive value scheme

\[priority: medium\] \[_TODO: check CMDValidate_\]

Don’t use string type if a more specific type can be used.

###### C8: Prefer elements over attributes {#c8}

\[priority: low\] \[_TODO: check: CMDValidate_\]

Attributes generally serve as place to annotate, i.e. provide information about the content of their parent element or component, which is a relatively rare requirement. Attributes lack a number of features that are available on elements, such as the option of being multilingual \(as attributes cannot be annotated\), the usage of value concept links \(for the same reason\) and have a maximum cardinality of one. Therefore attributes should only be introduced if there is an actual need to provide 'meta-metadata', for example to indicate a degree of uncertainty regarding a value, or to specify a unit of measure. Always consider grouping closely related information \(such as language name and language code\) in a component rather than making one information item an attribute of the other.

###### C9: Prefer vocabularies over booleans {#c9}

\[priority: medium\] \[_TODO: check: CMDValidate_\]

Many aspects described in metadata are of a binary nature. For example, a resource may be openly available or not; or a record may represent either a ”branch” or a “leaf’” in a hierarchical collection. It may be tempting to model this using the _boolean_ value scheme, for example by means of a field “publiclyAvailable” or “collectionLeaf” that takes either “true” or “false” as its value. However, be aware that this approach makes the semantics of the value more opaque than necessary. By creating a vocabulary containing two \(or more\) concept-specific values, you can provide explicit semantics to the values. For example, in comparison to the examples given above, a field ‘availability’ could have value scheme ‘public’ / ‘restricted’; a field ‘collectionLevel’ could have ‘branch’ / ’leaf’. Provide concept links for the vocabulary items if available.

### Reuse and recycling {#reuse-and-recycling}

###### C10: Model components with broad reusability in mind

\[priority: high\]

When creating a new component, try not to model only for your specific needs but also consider potential other applications of your component. The reason you are creating a new component is that all existing ones were too generic or too specific. Evaluate similar components candidates and the reasons they do not fit your needs, and see if similar arguments against using them could be applied to your component. Things to look at are:

* generic naming \(see the Naming best practices above\);
* granularity; try to cover just one aspect with your component, or a particular, common combination of aspects by combining other independent components
* permissiveness of cardinalities; if _you_ don’t _need_ multiple instances of a field for your particular use case, that doesn’t mean that an upper bound of 1 is always the best choice - as long as multiple values are conceptually sound, do not exclude such use cases unnecessarily \(also see [Constraints and value schemes](#constraints-and-value-schemes) best practices above\)

###### C11: Reuse or recycle components where possible

\[priority: high\] \[_TODO: check: CMDValidate_\]

The power of the CMDI model lies in the possibility of reusing and recombining components. Metadata modellers can benefit from the effort that other modellers put into designing, documenting and semantically annotating CMDI components. Existing components, in particular the **recommended** ones \(see section _TODO: Recommendations_\) have been tested in practice and have a good chance of being optimised for e.g. facet mapping in the VLO. Therefore it is advised to always look for existing components that fully or partially meet your requirements \(see [Workflow](../authoring_component_metadata_records/workflow.md)\). Multiple existing components can be combined into new components \(reused\) if they fit, and optionally new components can be created using existing components as a template \(this can be referred to as 'recycling'\), for example when additional elements within a component are required or different cardinalities are desired.

_TODO: Contact the owner of a component to discuss the needed changes, which could lead to a revision of the component. This process could be supported \(partially\) by the Component Registry. At the moment, the conversation will in general have to be initiated via the registry maintainer \(contact: cmdi@clarin.eu\)._

It may not always be clear if an existing component can serve as a good basis for a new component. In some cases the better option may actually turn out to be to create a component from scratch. Although it is hard to draw a clear line that is generally applicable, we can provide some guidelines as to whether a component **can** be considered fit for "recycling":

* The only required change is the insertion \(at any point in the structure\) or deletion of one or more elements, attributes or components. In case of deletion being the only required change, do consider _reusing_ the component.
* OR: a majority of child components, elements and attributes can be retained as is \(possibly with a change in order\)
* OR: all or nearly all child components, elements and attributes can be retained \(possibly with a change in order\) but one or more need to be enriched \(e.g. adding a concept link or documentation\) or slightly modified \(change in cardinality or multilingual property\) or replaced \(in case of a linked component\)

The following signs indicate that a given component may **not** be a suitable template for a new component with specific requirements:

* A majority of child components, elements and attributes would need to be removed or modified
* The concept link of the component itself needs to be changed to one that is not closely related to the original one \(an indication that the component is semantically too distinct from the one required\)
* The component does not comply with one or more best practices in a way that can be resolved with small adaptations in the new component

### Value vocabularies {#value-vocabularies}

* [ ] Reuse existing \(CLAVAS\) vocabularies.
* [ ] Open vs closed vocabularies
* [ ] Importing CLAVAS vocabularies
* [ ] Discuss general vs specific vocabularies
* [ ] ...

###### C12: Prefer controlled vocabularies {#c12}

\[priority: medium\] \[_TODO: check: CMDValidate_\]

In order to minimize inconsistencies regarding the selection of values as well as variance due to spelling conventions or typing errors, metadata modellers should provide specifications for the vocabulary intended as element and attribute contents wherever possible.

The best way to provide a vocabulary is by referencing an existing vocabulary of the CLARIN Vocabulary Access Service \(CLAVAS\).[^1] In case CLAVAS does not contain a suitable vocabulary for a considered domain it is possible to propose a new vocabulary for CLAVAS. In that case please contact: cmdi@clarin.eu. Note, however, that the person or group proposing a vocabulary to CLAVAS has to take the responsibility for maintaining it or for securing its long-term maintenance.

A CLAVAS vocabulary can be used as a closed or open vocabulary. Use an open vocabulary if MD providers should still be able to use individual \(not predefined\) vocabulary items. The open vocabulary then represents a set of suggestions for vocabulary items that should be considered. Be aware, however, that this does not restrict metadata creators to these suggestions, i.e. they can introduce variant spellings of semantically equivalent values. Another way to restrict the vocabulary is to provide fixed value lists for elements or attributes. This is the recommended procedure for centre-specific vocabularies. Centres should, however, endeavour to use generic labels which can be interpreted or even re-used outside the centre’s reach \(see [M1](/modelling_component_metadata/README.md#m1)\).

Furthermore, the CLARIN Component Registry offers the option to provide patterns conveying conventions for the style of value strings or to specify the datatype of a value \(e.g. if it should be a date, time, integer, or boolean\)\(see [Constraints and value schemes](#constraints-and-value-schemes)\). If none of the above ways is feasible, it should be considered to use means for checking, external to the CMDI infrastructure \(e.g. Schematron constraints\) while keeping the CMDI profile unrestrictive with regard to element and attribute values.

###### C13: Make use of @cmd:ConceptLink {#c13}

A vocabulary included in CMDI might consist of a link to an external vocabulary \(in general a CLAVAS vocabulary\) or an enumeration of vocabulary items. In case of the latter, add a Concept Link to each item of the proposed vocabulary to determine its semantics \(see [C14](#c14)\).

### Concepts {#concepts}

| TODO |
| --- |
| See best practices in [https://www.clarin.eu/sites/default/files/trippel-zinn-CLARIN2016\_paper\_15.pdf](https://www.clarin.eu/sites/default/files/trippel-zinn-CLARIN2016_paper_15.pdf) |

| TODO |
| --- |
| How to select a matching \(semantically close enough\) concept? When do you need to suggest a new concept? |

| TODO |
| --- |
| For guidelines for concept definitions see the CCR coordinators. |

In CMDI the semantics of all building blocks, e.g., components, elements and values, can be made explicit by adding a concept link. Such a link refers to an entry in a semantic registry, typically the CLARIN Concept Registry \(CCR; [clarin.eu/conceptregistry](http://www.clarin.eu/conceptregistry)\). Central parts of the CLARIN infrastructure use this semantic overlay to overcome the heterogeneity in both structure and naming of profiles and components.

###### C14: Add concept links to all elements, attributes and vocabulary items {#c14}

As a basis the semantics of most values in a metadata record should be made explicit. This is done by adding concept links to both elements and attributes. And where possible to the value itself, i.e., adding concept links to closed/open vocabulary items. In the case of open vocabulary items these concept links should also be expressed as _value concept links_ in the metadata records itself.

Reusing existing components will, in many cases, bring along concept links, potentially already optimised for mapping to VLO facets. In case you have to assess this mapping yourself it is good to inspect the existing VLO concept to facet mapping at [vlo.clarin.eu/mapping](http://vlo.clarin.eu/mapping).

###### C15: Add concept links to salient components {#c15}

Values, attributes and elements always exist within a component. Such a component, and possible ancestor components, can be used to provide semantic context. For example, the component ‘Actor’ provides the role a person plays within the metadata record. However, sometimes CMDI forces one to introduce an intermediate component that covers only data structuring needs, with but no semantic use. For example, a ‘description’ component that contains a ‘description’ element. There is no need to attach concept links to such components. Next to such corner cases a good general approach is to add a concept link to at least the ‘root component’ of a reusable component.

| TODO |
| --- |
| Refer to approved concepts |

###### C14: Refer to a concept that is “as generic as possible but as specific as needed”

As is the case with naming and structuring components and elements concept links should also be as generic as possible, i.e., foster reuse of the component by not pinpointing the semantics too specifically. For example, a generic ‘person name’ concept can be used without indication of the role the person plays within the component or profile. However, a general name concept might not be suited as it needs to be explicit that it is a person’s name. But see C13 to still use generic concepts and add specific semantics using the context.

###### C15: Refer to a persistent semantic registry

The preferred semantic registry of CLARIN is the CLARIN Concept Registry \(CCR; [clarin.eu/conceptregistry](http://www.clarin.eu/conceptregistry)\). This registry issues persistent identifiers to its entries and thus concept links in CMDI are stable even when the underlying technology of the registry changes. Next to the CCR also the Dublin Core elements or terms, which use PURLs as persistent identifiers, are considered stable enough. If you consider to refer to another semantic registry please contact the CCR Content Coordinators \([clarin.eu/ccr](http://www.clarin.eu/ccr)\) so the persistency of the registry can be assessed and the use of its \(persistent\) identifiers as concept links can be considered.

###### C16: If no matching concept can be found suggest a new or modified concept

Although the CCR concepts and the Dublin Core elements/terms already cover a lot of use cases one might encounter the need for a new concept, or would like to adapt a CCR concept just a little bit to make it fit better. The new concept specification, in the form of a preferred name and definition, or the modification should be suggested to the CCR Content Coordinators \([clarin.eu/ccr](http://www.clarin.eu/ccr)\).

| TODO |
| --- |
| Reference to the CCR Guidelines. |

The semantic richness, in the form of concept links, is also part of the quality assessment of a component and profile \(see workflow section below\).

[^1]: See [https://vocabularies.clarin.eu/clavas/](https://vocabularies.clarin.eu/clavas/)

