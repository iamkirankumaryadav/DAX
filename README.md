# DAX

`Data Analysis Expressions` | [SQLBI](https://www.sqlbi.com/) | [DAX Guide](https://dax.guide/) | [DAX Formatter](https://www.daxformatter.com/) | [DAX Do](https://dax.do/) | [DAX Patterns](https://www.daxpatterns.com/)

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
           VALUES ( 'Date'[Year] ), 
           'Date'[Year] < 2005 ),
           IF ( 
              'Date'[Year] >= 2000, 
              [Sales Amount] * 100, 
              [Sales Amount] * 90 
           )
    )
)
```

### DAX Data Types

Selection of the accurate data type helps to reduce the `size` of a data model and improve `performance` when to `refresh` data and use of any report.

1. `Whole` Number
2. `Decimal` Number ( floating point number )
3. `Boolen` ( TRUE / FALSE )
4. `Text` ( String )
5. `Currency` ( money )
6. `Date` ( DateTime )
7. `String`

### DAX type handling

Operator `Overloading` : Results are based on the `operators` used.

e.g. 

1. "5" + "4" = 9 ( Arithmetic Operation )
- Here even if we try to add numbers within `quotes` DAX converts string to integers and `add` the numbers.
- `DAX` knows that `+` is used to `Add` numbers. 

2. 5 & 9 = 59 ( Concatenation )
- Here due to `&` DAX will consider Integers as string and `concatenate` the strings. 

### DAX Function Category

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

### Components of DAX Data Model

- A `Data Model` consists of `Data`, `Calculations` and `Formatting` rules and it combines to create an object.
- This object helps to `Explore` and `Understand` the `Dataset`

1. `Data`
2. `Tables`
3. `Columns`
4. `Relationships`
5. `Measures`
6. `Hierarchies`

### Calculations

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

### Important Terms

1. `Data` or `Fact` Table : Contains `quantitative` values ( cost, quantity and prices )
2. `Lookup` or `Dimension` Table : Provides `descriptive` attributes about each dimension.
3. `Foreign` Key : Contains `multiple` instances of each value, and are used to match the `Primary` keys in related `Lookup` tables.
4. `Primary` Key : Uniquely identifies each `row` of a table, and match `Foreign` keys in related `Fact` tables.
5. `Cardinality` : The `uniqueness` of values in the column. 

### Important Facts

1. When we increase the number of `columns` the number of `rows` also increases because the combination increases.
2. The limit of excel is `Million` rows.
3. When then limit exceeds we need `Power Pivot` or `Power BI`

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
       <tr><th colspan=2>Text + Logical Operator</th></tr>
       <tr><td>&</td><td>[City] & " " & [State] ( Concatenate )</td></tr>
       <tr><td>&&</td><td>[State] = "MH" && [Country] = "IND"</td></tr>
       <tr><td>||</td><td>[State] = "MH" || [Country] = "IND"</td></tr>
       <tr><td>IN</td><td>[Region] IN {"AMS","APJ","EMEA"}</td></tr>
</table>

`AND` ( A, B ) or A `&&` B

`OR` ( A, B ) or A `||` B

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
