Each entity in one entity set can be related to **zero or more** entities in another entity set.
>[!Note]
>One to many and Many to one cardinality are the same.

**Symbol-**
`1:*`

**Example-**
In this scenario, each department can have multiple employees, but each employee is associated with only one department.
```
+----------------+          +-----------------+
|   Department   |          |     Employee    |
+----------------+          +-----------------+
| DepartmentID   |          | EmployeeID (PK) |
|   Name         |          |   Name          |
|   Location     |          |   Position      |
|                |<---------|   Salary        |
+----------------+          +-----------------+
```

### Trick to Identify

Ask question from each side, 
`|Department|<----<lives>----->|Employee|`
`  1                      ??   *      ` `How many Departments can 1 employee have?`
`?? 1                          1      ` `How many Employee can have 1 department?`

If we get 1 on one side in each cases, and many on another side, then it's a one to one cardinality.

