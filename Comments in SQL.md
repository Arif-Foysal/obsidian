In SQL, you can write comments to add explanatory or descriptive text that is ignored by the database engine.
## Single Line Comment
Use two consecutive dashes (`--`) to start a single-line comment. Anything after the double dashes until the end of the line will be treated as a comment and ignored by the database engine. For example:
```
-- This is a single-line comment in SQL
SELECT * FROM table_name; -- This is another comment after a SQL statement

```
## Multi Line Comment
Multi-line comments: Enclose the comments between `/*` and `*/` to create a multi-line comment. Everything within these delimiters, including line breaks, will be treated as a comment. For example:
```
/* This is a multi-line
   comment in SQL */
SELECT column1, column2
FROM table_name
WHERE condition;
/* This is another comment */
```

It's worth noting that the comment syntax may vary slightly depending on the specific database system you are using.