---
editor: Menzo
---

## Multilingual metadata {#multilingual-metadata}

Multilinguality should be considered for components and elements. If a language other than English is allowed/possible, an English version should be provided wherever feasible. A content language tag \(`@xml:lang` attribute\) should be used to determine the language of the respective metadata item. The choice of the language tag should be based on the [W3C recommendations on this topic](https://www.w3.org/International/questions/qa-choosing-language-tags), i.e. use an [BCP 47](https://tools.ietf.org/rfc/bcp/bcp47.txt) [language tag](https://tools.ietf.org/rfc/bcp/bcp47.txt) (see also [CS3](/authoring_component_metadata_records/the_component_section.md#cs3)).

All elements allowing for values that do not come from an \(implicit or explicit\) vocabulary are good candidates for being multilingual. Especially titles and descriptions should be multilingual. Provide English variants first, or if not feasible start with the ‘native’ language followed by English. Set the content language tag \(`@xml:lang` attribute\) for all variants, including English and/or the ‘native’ language, i.e., do not have an multilingual element without an `@xml:lang` attribute. Also do not allow multiple variants for a language, e.g., there should be only one English or native variant.

When an external vocabulary is used they should provide at least an english label, but they might provide additional labels in other languages. When the label is also the value, the english label should be preferred, unless the \(local\) primary audience of the record is native. Renderers of the record can look up the additional labels to deal with a multilingual setup.

