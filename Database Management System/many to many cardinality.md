Many-to-many cardinality refers to a type of relationship between two entities where multiple instances of each entity can be associated with multiple instances of the other entity.

**Symbol-**
`*:*`

**Example-**
```
+----------------+         +-----------------+
|    Student     |         |     Course      |
+----------------+         +-----------------+
| StudentID (PK) |         | CourseID (PK)   |
|   Name         |         |     Name        |
|   Age          |         |    Instructor   |
|   GPA          |         |   Credits       |
|                |---------|                 |
+----------------+         +-----------------+
```

### Trick to Identify

Ask question from each side, 
`|Student|----<Takes>-----|Course|`
`  1 ------------------- ??   * ` `How many Courses can 1 student have?`
`?? * ----------------------- 1 ` `How many students can have 1 course?`

If we get many on each side, then it's a many to many cardinality.