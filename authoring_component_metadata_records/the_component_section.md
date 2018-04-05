---
editor: Susanne
---

## The component section {#the-component-section}

### Extensiveness {#extensiveness}

###### CS1: Provide extensive metadata with regard to the profile

In general, it should be aimed at providing ‘complete’ metadata information with regard to the selected profile, i.e. the information asked for by the profile’s components, elements etc. should be provided as exhaustively as possible. In case optional elements of the selected profile are not assigned values, those elements should be left out of the metadata instance, i.e. empty elements without metadata information either as element or attribute values should be avoided.

### Resource proxy references {#resource-proxy-references}

###### CS2: refer to a ResourceProxy for resource specific metadata components {#cs2}

It is possible to refer to the resource a Components section specifically applies to by including the respective Resource Proxy id in the `@cmd:ref` attribute of the component’s root element. Don’t refer back to all Resource Proxies, which is possible with CMDI 1.1, as this is the implicit default.

### Text Elements and Attributes {#vocabularies}

###### CS3: In case of multilinguality, explicitly name the languages used

The default language for element contents is English, meaning that English wording should be provided for each element of the CMDI profile used. Additionally, other languages may be used, complementing the English version of a CMDI record. The possibility of multilinguality has to be already included in the design of the component. For the specification of the language applied, each element should be provided with an `@xml:lang` attribute. Use an [BCP 47](https://tools.ietf.org/rfc/bcp/bcp47.txt) [language tag](https://tools.ietf.org/rfc/bcp/bcp47.txt) to unambiguously identify the respective language within `@xml:lang`.

###### CS4: Use specific rather than \(only\) generic metadata

The information provided should be specific rather than generic \(e.g. two items “`gesture`” and “`speech`” for modality would be preferred to one item “`multimodal`”\). Similarly, there should be exactly one value per element. In case of several suitable values use several elements accordingly \(e.g. prefer `<modality>gesture</modality><modality>speech</modality>` to `<modality>gesture, speech</modality>`\). Note: In cases where controlled vocabularies are provided, the values are governed by those. However, also when metadata creators are free to type any string, it is best practice to avoid assigning enumerations of \(what is generally perceived as\) distinct values to one and the same element or attribute.

### Vocabularies

###### CS5: In open vocabularies make use of the suggested items before introducing extensions

In case of an open vocabulary provided for an element or attribute the proposed vocabulary should be applied wherever possible and only extended in case of gaps with regard to contents/concepts. If the proposed vocabulary is extended, try to avoid overlapping meanings and ambiguities among vocabulary items.

###### CS6: Provide consistent vocabulary items

The vocabulary used should be consistent throughout a repository. In this standardized wording and spelling \(e.g. for named entities such as organizations, collections, etc.\) should be used and abbreviations should be avoided or provided together with their proper expansion. Items of the vocabulary used should be mutually exclusive so that they hence may be unambiguously applied.

