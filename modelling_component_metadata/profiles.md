---
editor: Thomas
---

## Profiles {#profiles}

###### P1: Reuse components

\[priority: high\] \[_TODO: check: CMDValidate_\]

A main idea behind the CMD framework is the use of existing components to reduce the amount of work and to improve the general quality of profiles by benefiting from existing work of more experienced users. Therefore it is strongly encouraged to check the existing stock of profiles and components regarding their usefulness for your specific needs.

As it is very likely that at least some of the aspects of every resource type are comparable to other resources \(e.g. standard descriptive metadata like resource name, license or providing organisation\), these are natural candidates for a successful reuse. A profile that does not use existing components or that does not make use of any non-inline components contradicts the general idea of CMDI and is therefore undesirable. For a fast insight on which components are recommended by experienced profile designers, these components are included in the group “recommended” and can be displayed in the standard component registry \[_TODO_\]. For a similar reason it is advised to compare a new design with recommended profiles. \(See section [Recommendations](/recommendations/README.md).\)

###### P2: One component for one aspect

\[priority: medium\]

Different components in a profile should be exclusive concerning their scope. This means that every relevant aspect of a resource type should be dealt with in a single \(possibly complex\) component to avoid semantic overlaps between different parts of a profile.

###### P3: Support broad user groups

\[priority: medium\]

In large federated research infrastructures, a resource may be relevant for user groups that were not primarily targeted and that may lack information about the context in which a resource was originally created. Therefore every resource description should be self-contained and all information that may seem to be implicit \(like language, age, size, format or origin of a resource\) should be made explicit to facilitate the use of a resource in new scientific contexts.

###### P4: Use Documentation

\[priority: medium\] \[_TODO: partially check: CMDValidate_\]

CMDI allows extensive documentation of every part of a CMD metadata schema. This also holds for CMD Profiles. It is strongly encouraged to add a meaningful description to a profile, containing a general explanation of the purpose of the profile. This description should also be understandable for users without expert knowledge in the specific field. Domain-specific terminology may not be suitable for a proper understanding. In this case a general and a domain specific description could be helpful. If the profile has a specific relevance for a concrete scientific domain \(like lexicography or phonetics\), this information should be specified for the profile too.

###### TODO: P5: minimal semantic coverage

\[priority: medium\] \[_TODO: check:CMDValidate_\]

_A profile should \(at least via concept links\) cover a, agreed upon by the CLARIN community, minimal set of concepts, e.g. language and license._



