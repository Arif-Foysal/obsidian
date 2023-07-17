#dbms #Computer-Science 

a primary key that consists of multiple attributes or columns. It is used when a single attribute cannot uniquely identify each record, but a combination of multiple attributes can.
Let's consider an example of a composite primary key in the context of an "Order Items" table in an e-commerce database.

```
+---------------------+
|    Order Items      |
+---------------------+
| [PK] Order ID       |
| [PK] Item ID        |
|      Quantity       |
|      Price          |
+---------------------+
```
In this example, the composite primary key consists of two attributes: "Order ID" and "Item ID". Each attribute, on its own, may not be sufficient to uniquely identify an order item. However, by combining both attributes, we can ensure the uniqueness of each record.