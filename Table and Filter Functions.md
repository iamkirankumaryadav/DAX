### Table and Filter Functions

`DAX` has more than `250` functions, many of them manipulate tables.

Filter `Tables` or filter results of `Measures`

<table>
           <tr><th colspan=2>Filter Data</th></tr>
           <tr><td>ALL</td><td>Returns all the rows in a table, or all the values in a column, ignoring any filters.</td></tr>
           <tr><td>FILTER</td><td>Returns a filtered table based on one or more filtered expressions.</td></tr>
           <tr><td>DISTINCT</td><td>Returns a single column table of unique values</td></tr>
           <tr><td>VALUES</td><td>Returns a single column of unique values when a column name is passed. if a table is passed, VALUE returns the entire table including duplicates and blank rows.</td></tr>
           <tr><td>SELECTEDVALUE</td><td>Returns a value when there is only one value in a specified column.</td></tr>
           <tr><td>ALLEXCEPT</td><td>Removes all context filters in a table except the filter is applied to the specified columns.</td></tr>
           <tr><td>ALLSELECTED</td><td></td></tr>
</table>

Specify or add `Columns` based on existing data.

<table>
           <tr><th colspan=2>Add Data</th></tr>
           <tr><td>SELECTCOLUMNS</td><td></td></tr>
           <tr><td>ADDCOLUMNS</td><td></td></tr>
           <tr><td>SUMMARIZE</td><td>Create a summary of table grouped by specified columns</td></tr>           
</table>

Generate new `Rows`, `Columns` and `Tables` from scratch.

<table>
           <tr><th colspan=2>Create Data</th></tr>
           <tr><td>ROW</td><td>Returns a single row table with new specified columns.</td></tr>
           <tr><td>DATATABLE</td><td>Returns a new static data.</td></tr>
           <tr><td>GENERATESERIES</td><td>Returns a single column table containing sequential values.</td></tr>  
           <tr><td>{ } Table Constructor</td><td>Returns a table containing columns and rows.</td></tr>  
</table>

<table>
           <tr><th colspan=2>Calculated Table Joins</th></tr>
           <tr><td>CROSSJOIN</td><td>Caretsian product of two tables ( All possible combinations )</td></tr>
           <tr><td>UNION</td><td>Stacks two table together ( Vertically )</td></tr>
           <tr><td>EXCEPT</td><td>Returns all rows from left table which do not appear in right table.</td></tr>
           <tr><td>INTERSECT</td><td>Returns all rows from left table which also appears in right table ( Common )</td></tr>
</table>

`Cartesian`  
- Resulting table contains `m` * `n` rows 
- Resulting table contains `m` + `n` columns.
- Column names should be `different` in all the columns.

`Union`
- All tables must contain same number of `columns`
- Columns are combined by `position`
- Column names are determined by `first` table.
- Union creates `Duplicate` rows.

`Except`
- All tables must contain same number of `columns`
- Columns are combined by `position`
- Column names are determined by `left` table.
- Relations cannot be created with 3rd table.
- Useful in the case to find employee and customer `churning`

`Intersect`
- All tables must contain same number of `columns`
- Accepts only `2` Tables.
- Result of INTERSECT(T1,T2) will be different from INTERSECT(T2,T1)
- Union creates `Duplicate` rows.
- Column names are determined by `left` table.
- Relations cannot be created with 3rd table.
- Useful in the case to find active customer, repeat purchases and new employee or new customers in recent period.
