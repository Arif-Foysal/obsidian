#dbms 

Each entity in one entity set can be related to at most one entity in another entity set.

**Symbol-**
`1:1`

**Example:**
"Employee" and "Address." In this scenario, each employee is associated with at most one address, and each address is associated with at most one employee.
```
+----------------+                 +-----------------+
|    Employee    |                 |     Address     |
+----------------+                 +-----------------+
| EmployeeID (PK)|                 | AddressID (PK)  |
|   Name         |                 |    Street       |
|   Position     |                 |    City         |
|   Salary       |                 |    State        |
|                |<----<lives>---->|    Zip Code     |
+----------------+                 +-----------------+
```
### Notation
**Chen Notation**
The relationship set connects to each entity set with an **arrow** on each side. Just like the example. 

OR

Some people represent one to one in this way-
![[one-to-one.png]]

### Trick to Identify

Ask question from each side, 
`|Employee|<----<lives>----->|Address|`
`  1                      ??   1      ` `How many Addresses can 1 employee have?`
`?? 1                          1      ` `How many Employee can have 1 address?`

If we get 1 on both sides in each cases, then it's a one to one cardinality.
