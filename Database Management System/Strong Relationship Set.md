#dbms #Computer-Science 

Strong relationship set is a set of relations between two [[Strong Entity Set]]s. 

Let's consider an example of a strong relationship set between two entities: "Student" and "Course." In this scenario, each student can enroll in multiple courses, and each course can have multiple students. The relationship between the "Student" and "Course" entities is considered strong because both entities rely on each other to establish the enrollment relationship accurately.
```
+----------------+          +-----------------+
|    Student     |          |     Course      |
+----------------+          +-----------------+
| StudentID (PK) |          |   CourseID (PK) |
|   Name         |          |     Name        |
|   Age          |          |    Instructor   |
|   GPA          |          |   Credits       |
+----------------+          +-----------------+
| [FK] CourseID  |<-------->|                 |
+----------------+          +-----------------+
```

### Notation
**Chen Notation**
![[strong_rel_set.png]]