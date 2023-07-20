#dbms #Computer-Science 

### Components of Relational Schema
The main components of Relational Schema are-
 - Relations
 - Tuple(row, unordered)
 - Attributes(columns, unordered)
 - Domain (column type)
 - Primary key
 - Foreign Key
### Converting [[Entity Relationship Diagram (ERD)]] to Relational Schema
#### Strong Entity Set to Relational Schema
![[ERD_vs_rel-sc.jpg]]
For [[one to many cardinality]], primary key of one side comes to the many side as a foreign key.
#### Weak Entity Set to Relational Schema
![[Weak-entity_to_rel-scm.png]]
#### [[composite attribute]] to Relational Schema
![[composite-attrib-to-rel-scm.jpg]]

#### [[multi-valued attribute]] to Relational Schema

![[multi-attrib-to-rel-scm.jpg]]

#### [[derived attribute]] to Relational Schema

![[derived-attrib-to-rel-scm.jpg]]

#### [[one to one cardinality]] to Relationship Schema

![[one-to-one-to-rel-scm.jpg]]

>[!Note]
>- Foreign key can be on either side
>- Arrow point to the entity set from where Foreign key was brought

#### [[one to many cardinality]] to Relationship Schema

![[one-to-many-to-rel-scm.jpg]]
>Foreign key must be on the many side.
>arrow points to the owner of the foreign key

#### [[many to many cardinality]] to Relationship Schema

![[many-to-many-to-rel-scm.jpg]]
>Another table created whose name is the name of the relationship
>The table will contain all the primary keys from both entity set and the [[descriptive attribute]] (if there is any)

