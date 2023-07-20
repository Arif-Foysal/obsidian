#dbms #Computer-Science 

A super key is an attribute or a combination of attributes that can uniquely identify an entity in a table. A super key can have duplicate values.
For example, consider the following entity set-

| ID  | Name     | Phone_Number |
| --- | -------- | ------------ |
| 1   | david    | 09939843     |
| 2   | samantha | 09889899     |
| 3   | alex     | 08989883     |

In this student entity set, we can uniquely identify a student by it's **id**. So **id** is a super key in this entity set.

We can also identify a student using a combination of **id** and **name**. So, (**id,name**) is a super key combined.
>[!Note] 
>Here Name is called an **extraneous attribute** because it has no role identifying a student.
	But **name** alone cannot be a super key, because there can be multiple students with same names, and we cannot uniquely identify them just by their name.

**(id,name,phone_number)** is also a super key cause we can still identify a student uniquely with this attribute.