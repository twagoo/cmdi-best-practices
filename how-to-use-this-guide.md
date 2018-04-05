## How to use this Guide {#scope}

Although the guide will express the best practices in strict wording, it is possible, and sometimes even allowed to break a best practice. To indicate the impact of breaking a best practice a priority level is given:

1. _High priority_: a CMD record not following this best practice severely counters the ground principle of CMDI, e.g. reusable components with explicit semantics, or common best practices for resources on the web, e.g. URLs should be resolvable not dead links;
2. _Medium priority_: default priority of a best practice, which means it can be broken if you have good local \(technical or organizational\) reasons to deviate;
3. _Low priority_: a CMD record meeting this best practice is better adapted to the CLARIN infrastructure, but not following it will not have bad consequences.

Best practices with a _high_ priority should be followed. If a best practice with a medium level priority is not followed the reasons why should always be documented.

Compliance with some best practices can be \(partially\) assessed automatically. CLARIN provides the following tools and services:

1. CMDValidator:[^1] The validator for CMD components and profiles is in general used via the Component Registry;
2. CMDI Instance Validator:[^2] The corresponding validator for CMD records;
3. CLARIN curation module:[^3] This service provides insight into the quality of CMD profiles, records and endpoints, which can be accessed directly via their URLs.

The functionalities of the two more low level validators are being integrated into the CLARIN curation module to provide a single service for CMD quality assessment.

Some best practices have a direct relationship with the CLARIN B Centre requirements \([CE-2013-0095](http://hdl.handle.net/11372/DOC-78)\), which is indicated next to the priority. A CLARIN B Centre will have to meet such a requirement and the best practice.

[^1]: See [https://github.com/clarin-eric/cmd-validate/releases](https://github.com/clarin-eric/cmd-validate/releases)

[^2]: See [https://github.com/clarin-eric/cmdi-instance-validator/releases](https://github.com/clarin-eric/cmdi-instance-validator/releases)

[^3]: See [https://clarin.oeaw.ac.at/curate/](https://clarin.oeaw.ac.at/curate/)

