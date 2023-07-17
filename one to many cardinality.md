Each entity in one entity set can be related to **zero or more** entities in another entity set.
>[!Note]
>One to many and Many to one cardinality are the same.

**Symbol-**
`1:*`

**Example-**
In this scenario, each department can have multiple employees, but each employee is associated with only one department.


### Trick to Identify

Ask question from each side, 
`|Employee|<----<lives>----->|Address|`
`  1                      ??   1      ` `How many Addresses can 1 employee have?`
`?? 1                          1      ` `How many Employee can have 1 address?`

If we get 1 on both sides in each cases, then it's a one to one cardinality.

