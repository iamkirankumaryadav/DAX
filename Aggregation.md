<table>
    <tr><th><h3>Aggregation Functions</h3></th></tr>
</table>


`Aggregation` function returns a `Scalar` value to a column or an expression evaluated by iterating a table expression.

### AVERAGE

- Return the `Arithmetic Mean` of the values in the column.
- Return a `Scalar` value of `Currency` or `Decimal` type.

```DAX
AVERAGE ( 'Table'[Column] )
```

### AVERAGEA

- Similar to `AVERAGE`, handles non numeric data.
- `AVERAGEA` manages a `BOOLEAN` data type as an integer ( `FALSE` : `0` & `TRUE` : `1` )
- `AVERAGEA` always considers a `STRING` as `0`, regardless of the content of the string.

### AVERAGEX

- `AVERAGE` function internally executes `AVERAGEX`,  without any performance difference.
- `AVERAGEX` ignores `BLANK()`
- `AVERAGEX` considers `0`

```DAX
AVERAGEX (
    Table,
    Table[Column]
)
```

If the Column Values are `String`

```DAX
AVERAGEX (
    Table,
    VALUE ( Table[Column] )
)
```

### COUNT

- Counts the number of `Rows` in the table.
- `COUNT` does not count `BLANK()` rows, but it counts `empty` strings.

```DAX
COUNT ( Table[Column] )
```

### COUNTA

- Similar to `COUNT`, can operate on a `BOOLEAN` data type.

### COUNTX

- Count the number of values which result from evaluating an expression for each row of a table.
- The `COUNT` function internally executes `COUNTX`, without any performance difference.
- When function finds no rows it returns `Blank`

```DAX
COUNTX (
    Table,         // Table
    Table[Column]  // Expression
)
```        

### COUNTROWS

- Counts the number of `Rows` in the table including `blank` rows.
- We can use `CALCULATE` with `COUNTROWS` to ignore `BLANK()` and `Empty` string.

```DAX
CALCULATE (
    COUNTROWS ( Table ),
    NOT ISBLANK ( Table[Column] ) && Table[Column] <> "" // Ignore rows with BLANK() and Empty string values.
)
```

Count the `DISTINCT` rows in the table

```DAX
COUNTROWS ( DISTINCT ( Table ) )  or DISTINCTCOUNT ( Table[Column] )
```

Count whether a column has only one value.

```DAX
COUNTROWS ( VALUES ( table[column] ) ) = 1 or HASONEVALUE ( table[column] ) )
```

### COUNTBLANK

- Counts the number of `BLANK()` rows in the column.
- It returns `BLANK()`, if there are no rows.
- `Empty` string is considered as a `BLANK()` for `COUNTBLANK`

```DAX
COUNTBLANK ( Table[Column] )
```

Equivalent faster expression for counting `Blank` rows.

```DAX
CALCULATE (
    COUNTROWS ( Table ),
    KEEPFILTERS ( ISBLANK ( Table[Column] ) )
)
```

Equivalent faster expression for counting rows with `Empty` strings.

```DAX
CALCULATE (
    COUNTROWS ( Table ),
    KEEPFILTERS ( Table[Value] = "" )
)
```

### DISTINCTCOUNT


### DISTINCT

- Returns a single column table of `Unique` Values.
- Does not return the `Blank` row.


### VALUES

- Returns a single column table of `Unique` Values.
- Similar to `DISTINCT` but also have additional `Blank` rows for the values which is not found.
