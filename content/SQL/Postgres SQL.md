
`CREATE DATABASE database_name;` - creates new database.
`\l` - lists all the databases.
`\c database_name` - connect to a database.
`\d` - display the tables.
`CREATE TABLE table_name();` - creates a table in the database.
`\d tablename;`- display the info about that table.

```sql
ALTER DATABASE database_name RENAME TO new_database_name;
```
- That renames the database.
`DROP DATABASE database_name;` - used to delete the database.

*Tables need **columns** to describe the data in them*

```sql
ALTER TABLE table_name ADD COLUMN column_name DATATYPE;
``` 
- This alters the table and insets a column in the table with a specific data type.

```sql
ALTER TABLE table_name DROP COLUMN column_name;
```
 - This deletes the column from the table
 
 ```sql
ALTER TABLE table_name RENAME COLUMN column_name TO new_name;
```
- This Renames the column.

```sql
INSERT INTO table_name(column_1, column_2) VALUES(value1, value2);
```
- Rows are the actual data in the table. You can add one like this:

```sql
SELECT columns(*) FROM table_name;
```
-  You can view the data in a table by querying it with the `SELECT` statement.

```sql
DELETE FROM table_name WHERE condition;
```
- Deletes the row from the table where the condition met.

```sql
DROP TABLE table_name;
```
- Deletes the table from the database

```sql
INSERT INTO characters(name, homeland, favorite_color)
VALUES('Mario', 'Mushroom Kingdom', 'Red'),
('Luigi', 'Mushroom Kingdom', 'Green'),
('Peach', 'Mushroom Kingdom', 'Pink');
```
##### Data Types:
INT - Integer
Varchar(x) - String values.
SERIAL - The `SERIAL` type will make your column an `INT` with a `NOT NULL` constraint, and automatically increment the integer when a new row is added.