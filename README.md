# DAX

`Data Analysis Expressions` 

[SQLBI](https://www.sqlbi.com/) | [DAX Guide](https://dax.guide/) | [DAX Formatter](https://www.daxformatter.com/) | [DAX Do](https://dax.do/) | [DAX Patterns](https://www.daxpatterns.com/)

<table>
	<tr colspan=2><th>Index</th><th>Title</th></tr>
	<tr><th>1</th><td><a href=#type>Data Type</a></td></tr>
	<tr><th>2</th><td><a href=#operators>DAX Operators</a></td></tr>
	<tr><th>3</th><td><a href=#function>Function Category</a></td></tr>
	<tr><th>4</th><td><a href=#comp>Components of DAX Data Model</a></td></tr>
	<tr><th>5</th><td><a href=#calculate>Calculated Column, Measure and Table</a></td></tr>
	<tr><th>6</th><td><a href=#imp>Important Facts and Points</a></td></tr>
	<tr><th>7</th><td><a href=#var>Dax Variable</a></td></tr>
	<tr><th>8</th><td><a href=#context>Row, Filter and Query Context</a></td></tr>
	<tr><th>9</th><td><a href=#order>Evaluation Order</a></td></tr>	
</table>

Programming language that resembles `Excel` 
- Power Pivot
- Power BI
- Designed for data models and business calculations.

`DAX` is a functional language, the execution flows with function calls.

It means, calculations mostly use `functions` to generate the results.

`DAX` is designed for enhancing `Data Modeling`, `Reporting` and `Analytics` capability.

```DAX
SUM (
    FILTER ( 
    	VALUES ( 'Date'[Year] ), // Distinct Year
        'Date'[Year] < 2005 ),   // Year before 2005
        IF ( 
	   'Date'[Year] >= 2000, // Condition | Expression
           [Sales Amount] * 100, // If TRUE
           [Sales Amount] * 90   // If FALSE
        )
    )
)
```

<h3 name=type>DAX Data Types</h3>

Selection of the accurate data type helps to reduce the `size` of a data model and improve `performance` when to `refresh` data and use of any report.

1. `Whole` Number
2. `Decimal` Number ( floating point number )
3. `Boolen` ( TRUE / FALSE )
4. `Text` ( String )
5. `Currency` ( money )
6. `Date` ( DateTime )
7. `String`

<h3 name=operators>Operators in DAX</h3>

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
       <tr><th colspan=2>Text + Logical Operator</th></tr>
       <tr><td>&</td><td>[City] & " " & [State] ( Concatenate )</td></tr>
       <tr><td>&&</td><td>[State] = "MH" && [Country] = "IND"</td></tr>
       <tr><td>||</td><td>[State] = "MH" || [Country] = "IND"</td></tr>
       <tr><td>IN</td><td>[Region] IN {"AMS","APJ","EMEA"}</td></tr>
</table>

`AND` ( A, B ) or A `&&` B

`OR` ( A, B ) or A `||` B

### DAX type handling

Operator `Overloading` : Results are based on the `operators` used.

e.g. 

1. "5" + "4" = 9 ( Arithmetic Operation )
- Here even if we try to add numbers within `quotes` DAX converts string to integers and `add` the numbers.
- `DAX` knows that `+` is used to `Add` numbers. 

2. 5 & 9 = 59 ( Concatenation )
- Here due to `&` DAX will consider Integers as string and `concatenate` the strings. 

<h3 name=function>DAX Function Category</h3>

There are more than `200` DAX functions, there are `9` categories in DAX function.

1. `Date` and `Time`
2. `Time Intelligence`
3. `Information`
4. `Logical`
5. `Mathematical`
6. `Statistical`
7. `Text`
8. `Parent` / `Child`
9. `Other` 

<h3 name=comp>Components of DAX Data Model</h3>

- A `Data Model` consists of `Data`, `Calculations` and `Formatting` rules and it combines to create an object.
- This object helps to `Explore` and `Understand` the `Dataset`

1. `Data`
2. `Tables`
3. `Columns`
4. `Relationships`
5. `Measures`
6. `Hierarchies`

<h3 name=calculate>Calculations</h3>

There are `3` types of Calculations in `DAX`

1. Calculated `Columns`
2. Calculated `Measures`
3. Calculated `Tables`

### Calculated Columns  

- Column computed using a `DAX` language.
- Calculation happens `row` by `row` and stored in the model.
- Consumes `memory` in the model.

### Calculated Measures  

- Computes at `aggregate` or `report` level.
- Useful to calculate `percentage`, `ratio` and `aggregations`
- Columns cannot be directly referenced in the Measure, it will be always surrounded by some `Aggregate` function.
- Consumes `CPU` at query time.

### Calculated Tables

- Creates new table or slice the subset from some existing table.
- Consumes `memory` in the model.

<h3 name=imp>Important Terms</h3>

1. `Data` or `Fact` Table : Contains `quantitative` values ( cost, quantity and prices )
2. `Lookup` or `Dimension` Table : Provides `descriptive` attributes about each dimension.
3. `Foreign` Key : Contains `multiple` instances of each value, and are used to match the `Primary` keys in related `Lookup` tables.
4. `Primary` Key : Uniquely identifies each `row` of a table, and match `Foreign` keys in related `Fact` tables.
5. `Cardinality` : The `uniqueness` of values in the column. 

### Important points about Data Modeling

1. Use `Star` schema (One to Many) relationship.
2. Always create a relationship with `one way` filters.
3. Only include the data you need for analysis.
4. Split out individual `Date` and `Time` components from `DateTime` field.
5. `Disable` the refreshing of Data if that do not need refresh everytime from the Power Query Editor.

### Important Facts

1. When we increase the number of `columns` the number of `rows` also increases because the combination increases.
2. The limit of excel is `Million` rows.
3. When then limit exceeds we need `Power Pivot` or `Power BI`

<h3 name=var>DAX Variable</h3>

- `Variables` make the calculation easier to understand.
- Writing any complex or `nested` expression using `DAX` functions, variables can help to break these complex calculations into smaller, more useful sections.
- `Reduce` complexity, Easy to `Debug`, Improve `readability` and Improve `performance`

```DAX
VAR name = expression

RETURN name or expression
```
	
<h3 name=context>Context in DAX</h3>

- `Context` is how `DAX` apply layers of `filters` to calculations and tables.
- Used in the calculations so that they `return` relevant results for every value.
- Produce a result related to each and every value of a visual or pivot table including rows and columns total.

#### 1. Row Context 	

- `Row Context` is related to current `rows`
- If you create a `Calculated Column`, the `Row Context` involves the values of all the `Columns` ( entire `Row` )
- If that table has a `relationship` with other table, then it includes all the `related` values from that `Table` for that `Row`
- In `Iterative` functions in `DAX` over table, each `Row` has its own `Row Context`

#### 2. Filter Context  

- Applying `Filters` on set of values of `Columns` or `Tables` using `DAX` calculations.
- `Filter Context` applies on the top of `Row Context` and `Query Context` 

1. `Attributes` in `rows` or `columns`
2. By `Slicer`
3. Through `Filter Pane`
4. To the `Calculated Measure`

#### 3. Query Context

- Combination of `Row Context` and `Filter Context` creates a final query for `DAX`
- Users explicitly mention `Row Context` and `Filter Context` for `DAX`
- `DAX` implicitly creates the `Query Context` from that `Row Context` and `Filter Context`

<h3 name=order>Evaluation Order</h3>

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
