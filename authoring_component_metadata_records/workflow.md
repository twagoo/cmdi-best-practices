---
editor: Hanna
---

## Workflow {#workflow}

The workflow for creation of CMDI records for hosted resources will depend on the specific conditions and requirements at your centre. CMDI files can be created \(semi-\)manually \(by editing XML files or using tools such as CMDI Maker,[^1] COMEDI,[^2] and Arbil[^3] - this will usually be done by the resource owners\), or by automatic conversion from existing metadata formats with the usual benefits and disadvantages of manual and automatic data creation respectively.

Concerning metadata quality assessment in the workflow, some aspects can be checked before CMDI is imported into the VLO:

* all CMDI metadata must validate against the profile XSD
* manually created CMDI should go through automatic consistency checks
* all CMDI metadata should be checked for features that cannot be covered by the profile XSD - the [CMDI Validator](https://github.com/clarin-eric/cmdi-instance-validator/releases/latest) includes a set of Schematron rules that can be used for additional specific Schematron checks \(and adapted as necessary\)
* the [CLARIN Curation Module](https://clarin.oeaw.ac.at/curate/) should be used to asses records

The following aspects on the other hand need to be checked after VLO import:

* appropriateness of all normalised and mapped values for VLO facets \(cf. VLO-mapping\) - any mapping issues should be reported via [cmdi@clarin.eu](mailto:cmdi@clarin.eu)
* appropriateness of the display of resource hierarchies, especially in cases where MdSelfLink and/or ResourceProxy values are changed as part of the workflow.



[^1]: See http://cmdi-maker.uni-koeln.de/, but notice that CMDI Maker only supports 2 profiles!

[^2]: See http://clarino.uib.no/comedi/

[^3]: See https://tla.mpi.nl/tools/tla-tools/arbil/, but notice that Arbil is not maintained anymore!

