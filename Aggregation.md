### Aggregation

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
    'Table'[Column]
)
```

If the Column Values are `String`

```DAX
AVERAGEX (
    Table,
    VALUE ( 'Table'[Column] )
)
```

### COUNT

- Counts the number of `Rows` in the table where the specified `Column` has non blank value.

```DAX
COUNT ( 'Table'[Column] )
```

### COUNTA

- Similar to `COUNT`, can operate on a `BOOLEAN` data type.

### COUNTX

- The `COUNT` function internally executes `COUNTX`, without any performance difference.

```DAX
COUNTX (
    Table,
    'Table'[Column]
)
```        

### COUNTROWS

- Counts the number of `Rows` in the table or specified `Column` including `blank` rows.
- We can use `CALCULATE` with `COUNTROWS` to ignore `BLANK()`

```DAX
CALCULATE (
    COUNTROWS ( Table ),
    NOT ISBLANK ( 'Table'[Column] )
)
```
