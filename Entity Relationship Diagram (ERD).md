#dbms #uiu #Computer-Science 

>[!Contents]
> [[Entity Relationship Diagram (ERD)#Components of ERD|Components of ERD]]
> [[Entity Relationship Diagram (ERD)#ERD Notations|ERD Notations]]
> 	- [[Chen Notation]]
> 	- [[Crow's Foot Notation]]
> 
> 


An Entity Relationship Diagram (ERD) describes all the table within the database and the relations between them.
### Components of ERD
There are 3 components of ERD-
	- Entity
	- Attributes
	- Relationships
ERDs can be created using drawing tools like [LucidChart](https://jovian.com/outlink?url=https%3A%2F%2Fwww.lucidchart.com%2Fpages%2Fhow-to-draw-ERD) or [ERDplus](https://erdplus.com). Here's the ERD for the Classic Models database:
### Entity
An entity refers to a distinct and identifiable object, concept, or thing that can be represented and stored in the database. For example, a customer, product, or order is an entity. Entities are the basic building blocks of a database. An entity is typically represented as a row in a table in a [[Relational Databases and SQL]], and entity set is represented as a table. An entity has two main parts:

- **Attributes:** Attributes are the properties of an entity. For example, the attributes of a customer might include their name, address, and phone number. Represented as columns in [[Relational Databases]].
- **Relationships:** Relationships are the connections between entities. For example, a customer might have many orders, and an order might have many products. Set of relationships of same category is called relationship set.
#### Types of Entity Set
Entity sets are of two types-
 1. [[Strong Entity Set]]
 2. [[Weak Entity Set]]
### Types of Attributes
There are several types of attributes which include-
	- [[simple attribute]]
	- [[composite attribute]]
	- [[derived attribute]]
	- [[multi-valued attribute]]
	- [[descriptive attribute]]
### Key Attributes
  - [[Super Key]]
  - [[Candidate Key]]
  - [[Primary Key]]
  - 

### Relationships
A relationship is a connection between two or more entities.
**Relationship Set**
A relationship set is a set of relationships of the same type.
#### Types of Relationships
Relationship sets are of two types-
	- [[Strong Relationship Set]]
	- [[Weak Relationship Set]]
#### Cardinality of Relationship Set
In Entity-Relationship Diagrams (ERDs), cardinality refers to the number of entities that can be related to each other in a relationship set.
There are three main types of cardinality:
	- [[one to one cardinality]]
	- [[one to many cardinality]]
	- [[many to many cardinality]]

### ERD Notations
There are different notations of ERD. But some of the most common notations include-
	- [[Chen Notation]]
	- [[Crow's Foot Notation]]

