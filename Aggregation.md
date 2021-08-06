### Aggregation

`Aggregation` function returns a `Scalar` value to a column or an expression evaluated by iterating a table expression.

### AVERAGE

- Return the `Arithmetic Mean` of the values in the column.
- Return a `Scalar` value of `Currency` or `Decimal` type.

`AVERAGE` function internally executes `AVERAGEX`

```DAX
AVERAGE ( 'TableName'[ColumnName] )
```

```DAX
AVERAGEX (
    TableName,
    'TableName'[ColumnName]
)
```

If the Column Values are `String`

```DAX
AVERAGEX (
    TableName,
    VALUE ( 'TableName'[ColumnName] )
)
```
