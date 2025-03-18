
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
- For Adding multiple rows at once.

```sql
UPDATE table_name SET column_name=new_value WHERE condition;
```
- Updating Rows.

```sql
SELECT columns(*) FROM table_name ORDER BY column_name;
```
- Orders the table by the column.

```sql
ALTER TABLE table_name ADD PRIMARY KEY(column_name);
```
- This creates primary key in the table. It's a column that uniquely identifies each row in the table.

```sql
ALTER TABLE table_name DROP CONSTRAINT constraint_name;
```
- This deletes the primary key from the column
- constraints name is shown below the table column e.g. 'characters_pkey'
![[Pasted image 20250318045440.png]]

set a **foreign key** so you can relate rows from this table to rows from your `other` table.
```sql
ALTER TABLE table_name ADD COLUMN column_name DATATYPE REFERENCES referenced_table_name(referenced_column_name);
```


There's your foreign key at the bottom. These tables have a "one-to-one" relationship. **One** row in the `characters` table will be related to exactly **one** row in `more_info` and vice versa.
![[Pasted image 20250318051549.png]]

```sql
ALTER TABLE table_name ADD UNIQUE(column_name);
```
- Add the `UNIQUE` constraint to the column.

```sql
ALTER TABLE table_name ALTER COLUMN column_name SET NOT NULL;
```
- Sets the column to be not null. means it cannot be empty

```sql
SELECT column_name, column_name2 FROM tabel_name;
```
- Lists column A & B from the table.

```sql

INSERT INTO table_name(foreign_key_column, date_column, c2, c3) VALUES(1, 'YYYY-MM-DD', num, num)
```
- Adds values to the column with foreign_key.

```sql
SELECT column1, column2 FROM table_name WHERE column='condition';
```
- Shows the the rows data where the condition is met.

```sql
CREATE TABLE table_name(column_name DATATYPE CONSTRAINTS);
```
- creates a table with column.

```sql
ALTER TABLE table_name ADD COLUMN column_name DATATYPE CONSTRAINT REFERENCES referenced_table_name(referenced_column_name);
```


"Many-to-many" relationships usually use a **junction** table to link two tables together, forming two "one-to-many" relationships.
Your junction table will use the primary keys from the `one_table` and `other_table` tables as foreign keys to create the relationship.

```sql

ALTER TABLE table_1 ADD FOREIGN KEY(column_name) REFERENCES table_2(coulmn_name);
```
- here the junction table tables joins the two tables as foreign key to create one to many relationship.
  
Every table should have a primary key. Your previous tables had a single column as a primary key. This one will be different. You can create a primary key from two columns, known as a **composite** primary key. Here's an example:

```sql
ALTER TABLE table_name ADD PRIMARY KEY(column1, column2);
```

```sql
INSERT INTO table_name(column_1, column_2) VALUES(value_1, value_2), (value_1, value_2);
```
- This adds rows data to the junction table.

you can get all the data from both tables with a `JOIN` command:

```sql
SELECT columns(*) FROM table_1 FULL JOIN table_2 ON table_1.primary_key_column = table_2.foreign_key_column;
```
- you can chain on more joins to join the tables together.
##### Data Types:
INT - Integer
Varchar(x) - String values.
SERIAL - The `SERIAL` type will make your column an `INT` with a `NOT NULL` constraint, and automatically increment the integer when a new row is added.
`NUMERIC(4, 1)`  data type is for decimals. `NUMERIC(4, 1)` has up to four digits and one of them has to be to the right of the decimal.