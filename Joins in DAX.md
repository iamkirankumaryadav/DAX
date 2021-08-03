### Joins

How to create `Joins` in `DAX` with / without `Relationships`

### Standard Relationship in DAX

- When a `Data Model` has more than one table, it is possible to have a `Relationship` between them.
- The `Relationship` between them is used by `DAX` during calculations.

### 1. One to Many Relationship

- The `Dimension` table has a `unique` row and for every row, there are multiple rows in the `Fact` table.

### 2. One to One Relationship

- The columns in both table have `unique` values.

### Important Points 

- Only a `single` Column in both the tables can be used to create or define the `Relationship`
- More than one column can not be used for defining any `Relationship`
- We can create a new column with the combinations of multiple columns and then it can be used to create `Relationship`

### Matching Criteria 

`Operators` ( =, >=, <=, <> )

`Self` Join is not possible.

### Joining without a Relationship

`DAX` Functions which help us to Calculate without a Standard Relationship.

1. `CROSSJOIN` : Cartesian Product ( Columns Names of both the tables should be different ) 

2. `GENERATE` :

3. `NATURALINNERJOIN` : Matching values with the `same` column name and data type in both the tables.

4. `NATURALLEFTOUTERJOIN` : All the values of the first table and the matching values of the second table.

5. `UNION` : A table that containes all the rows from both the tables including duplicates ( Same column name and numbers )

6. `EXCEPT` : Create a table except few rows based on the given condition.

7. `INTERSECT` : Only the common rows in both the tables.
