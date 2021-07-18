# DAX
Data Analysis Expressions | [SQLBI](https://www.sqlbi.com/) | [DAX Guide](https://dax.guide/) | [DAX Formatter](https://www.daxformatter.com/) | [DAX Do](https://dax.do/) | [DAX Patterns](https://www.daxpatterns.com/)

`DAX` is a functional language, the execution flows with function calls.

```DAX
Amount = SUM (
           FILTER ( VALUES ( 'Date'[Year] ), 'Date'[Year] < 2005 ),
           IF ( 'Date'[Year] >= 2000, [Sales Amount] * 100, [Sales Amount] * 90 )
         )
```

### Important Terms

1. Data Table or `Fact` Table : Contains measurable values (cost, quantity and prices)
2. Lookup or `Dimension` Table : Provides descriptive attributes about each dimension.
3. `Foreign` Key : Contains multiple instances of each value, and are used to match the `Primary` keys in related Lookup tables.
4. `Primary` Key : Uniquely identifies each `Row` of a table, and match `Foreign` keys in related Data tables.
5. `Cardinality` : The uniqueness of values in the column. 

### Evaluation Order 

1. `Individual` functions : Left to Right ( Startting from first parameter and following the order )

```DAX
IF(Logical, Return IF True, Return IF False)
```

2. `Nested` functions     : Inside Out ( Start from innermost function and work outward )

```DAX
= SUMX (
       FILTER (
              RELATED ( )
       )
  )
```

### Important points about Data Modeling

1. Use `Star` schema (One to Many) relationship.
2. Always create a relationship with `one way` filters.
3. Only include the data you need for analysis.
4. Split out individual `Date` and `Time` components from `DateTime` field.
5. `Disable` the refreshing of Data if that do not need refresh everytime from the Power Query Editor.

<table>        
           <tr><th colspan=2>Arithmetic Operator</th></tr>
           <tr><td>Addition</td><td>+</td></tr>
           <tr><td>Subtraction</td><td>-</td></tr>
           <tr><td>Multiplication</td><td>*</td></tr>
           <tr><td>Division</td><td>/</td></tr>
           <tr><td>Exponent</td><td>^</td></tr>
</table>

<table>
        <tr><th colspan=3>Comparison Operator</th></tr>
        <tr><td>Equal to</td><td>=</td><td>[City] = 'Mumbai'</td></tr>
        <tr><td>Greater than</td><td>></td><td>[Age] > 18</td></tr>
        <tr><td>Less than</td><td><</td><td>[Age] < 18</td></tr>
        <tr><td>Greater than or Equal to</td><td>>=</td><td>[Age] >= 18</td></tr>
        <tr><td>Less than or Equal to</td><td><=</td><td>[Age] <= 18</td></tr>
        <tr><td>Not equal to</td><td><></td><td>[City] <> "Mumbai"</td></tr>
</table>

<table>
       <tr><th colspan=2>String or Logical Operator</th></tr>
       <tr><td>&</td><td>[City] & " " & [State]</td></tr>
       <tr><td>&&</td><td>[State] = "MH" && [Country] = "IND"</td></tr>
       <tr><td>||</td><td>[State] = "MH" || [Country] = "IND"</td></tr>
       <tr><td>IN</td><td>[Region] IN {"AMS","APJ","EMEA"}</td></tr>
</table>

### Error Handling

Helps us to identify `missing` data. ( Quality assurance and testing )

1. `IFERROR()` : IFERROR(Value, ValueIfError) 

```DAX
Error Check = 
IFERROR (
        1/0,
        BLANK()
)        
```

2. `ISBLANK()` : ISBLANK(Value)

```DAX
IF (
   ISBLANK (
           [Sales (Last Year)]
   ),
   "No Sales",
   [Sales (Last Year)]
)
```
                                                                                                         
### Important Functions 

### 1. CALCULATE
- `Evaluate` a given expression or formula under a set of defined `filters`.

```DAX
=
CALCULATE ( Expression, Filter1, Filter2 )

# Expression : An existing Measure or a DAX Formula for a valid measure.
# Filter     : Filter Expressions (Asia[Country] = "India") or (Student[Age] > 18)
```

### Table and Filter Functions

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
           <tr><td>EXCEPT</td><td>Caretsian product of two tables ( All possible combinations)</td></tr>
           <tr><td>INTERSECT</td><td>Caretsian product of two tables ( All possible combinations)</td></tr>
</table>

`Cartesian` Product 
- Resulting table contains `m` * `n` rows 
- Resulting table contains `m` + `n` columns.
- Column names should be `different` in all the columns.

`Union`
- All tables must contain same number of `columns`
- Columns are combined by `position`
- Column names are determined by `first` table.
- Union creates `Duplicate` rows.
