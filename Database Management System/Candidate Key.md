
Candidate key is a [[Super Key]] of minimum size. A candidate key cannot contain any extraneous attribute.

>[!Note]
>Every candidate is a super key, but all super keys are not candidate key.

Consider the following entity set-

| ID  | Name     | Phone_Number | username   | address |
| --- | -------- | ------------ | ---------- | ------- |
| 1   | david    | 09939843     | dav112     | LA      |
| 2   | samantha | 09889899     | samantha69 | CA      |
| 3   | alex     | 08989883     | alexX      | NY      |

- Here **id** is a candidate key
- **(id,username)** is also a candidate key

But **(id,name)** is **not** a candidate key, because it contains extraneous attribute (**name**)

