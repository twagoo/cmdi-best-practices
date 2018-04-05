## Dealing with uncertainty

In many cases one has to model for uncertainty. For example, the creation date of a document may not be known or only by approximation. Rather than making a field for such information optional, it might be desirable to provide the metadata creator with an option to make this uncertainty explicit. A "string" typed field provides this option \(i.e. it allows the metadata creator to enter "?" or "unknown"\) but does so at the cost of value "safety" - in this example it does not enforce a standardised date format. A better approach is to require a value of a more specific type if applicable, for example a date or integer. Alternatively a vocabulary or pattern can be used to constrain the values that may be entered, optionally including a literal value like 'Unknown'. You can also add an \(optional\) attribute with type "boolean" or a vocabulary to allow the metadata creator to specify the level of uncertainty.

```
<cmdp:birthYear certainty="uncertain">1180</cmdp:birthYear>
```

Note that in many cases making an element optional is a valid modelling decision for cases where information might not be available. However, preferably this would be reserved for

```
<cmdp:birthYear confidence="not found"/>
```

Notice that this provides more information than leaving out the unknown birth year. The confidence value tells us that one has been looking for the birth year but it has not been found yet. Leaving out the birth year would mean in this case that its unknown, but has also not been researched.

| Note by Menzo |
| :--- |
| This is analogous to the ambiguity of NULL values in databases, but that's probably too technical to refer to. See also [https://trac.clarin.eu/wiki/CmdiNillableFields](https://trac.clarin.eu/wiki/CmdiNillableFields) |



