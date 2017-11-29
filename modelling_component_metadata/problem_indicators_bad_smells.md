---
editor: Thomas
---

## Problem indicators \(“bad smells”\) {#problem-indicators-bad-smells}

|TODO|
|----|
|No “recommended” components as smell?|

\(Bad\) Smells are used as simple indicators for bad or inefficient designs \(typically in programming languages\). To identify a specific “smell” in a profile does not necessarily mean that the design is broken and should be replaced. Instead it should be seen as a warning sign that there may be a problem which should be checked. Measures to eliminate actual problems by changing the design are often called refactorings. In the following some “smells” and refactorings \(adapted from their counterpart in object oriented programming\) are shortly discussed:

* A _Standalone profile_ does not reuse any components or only to a little degree. In this case it may be useful to evaluate the existing component stock to find reuse candidates.
* If a profile allows the description of a more general resource type or allows the description of resource aspects that most likely won’t be used, one speaks of _Speculative Generality_. Another indication is an extensive use of optional elements/components \(cardinality of 0\). As a consequence a typical metadata file will only instantiate a very small subset of all possible elements or components. In this case it may be useful to remove unnecessary elements or components to reduce the complexity of the overall profile. Be aware that this may be an acceptable design for profiles that are primarily used for representing metadata from other formats. Also, confer [C6](/modelling_component_metadata/components.md#c6) above.
* _Another kind of Speculative Generality_ is creating a profile that will fit a whole set of different resource types, where a specific instance file will only instantiate \(resource-\)specific parts. In this case it may be useful to extract resource type independent aspects into a single component and create a profile for every resource type while reusing this common component.
* If inline parts of a profile seem to be applicable for other resource types as well, it may be a useful to _extract_ these parts into an independent _component_ to promote its reuse in other profiles.
* A _Lazy Component_ is a non-inline component that is used in a profile of which only small parts are actually intended to be used. In this case it may be reasonable to only include the used elements of this component in the profile.
* The name of a profile should give even inexperienced users some understanding about the described resource type. If this is not the case it may be useful to _rename_ the _profile_. If a more detailed description is necessary, this can be specified in the description section of the profile.
* Profiles that refer to external resources via elements or attributes of type ‘anyURI’ may be candidates for a redesign where these references may be explicitly specified in resource proxy elements in the CMD resource section \(also see recommendations with respect to resource proxies in metadata records\).
* In general it is recommended to store metadata content in elements instead of using attributes, as this often leads to a more comprehensible design and eases automatic extraction of content. The extensive use of attributes for storing metadata content may be an indicator for a necessary redesign. In those cases the usage of elements or even the creation of a new metadata component may be reasonable. See also [C8](/modelling_component_metadata/components.md#c8) above.



