#dbms #Computer-Science 

A **weak entity set** is an entity set that cannot be uniquely identified by its own attributes alone. It must be associated with another entity set, called the **identifying entity set**, in order to be uniquely identified.

>Weak entity set will have a [[partial key]] that will be combined with a [[Primary Key]] of another entity set.

**Example**

```
+----------------+          +-----------------+
|      Loan      |          |    installment  |
+----------------+          +-----------------+
| Loan_no (PK)   |          | Inst_no         |
|   Amount       |          |   Date          |          
|                |<---------|   Amount        |
+----------------+          +-----------------+
```

If we enter some data to the tables
```
|  ID  |  Amount  |    |  no  |  Date  |  Amount  |
|------|----------|    |  I1  |  1/1/23| 1000     |
|  1   |  5000    |    |  I2  | 5/1/23 | 500      | 
|  2   |  10000   |    |  I1  | 3/2/23 |  1500    |
                       |  I2  | 5/2/23 |  2000    |

```


### Notation

![[Weak-entity-set.png]]








