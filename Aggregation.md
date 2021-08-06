### Aggregation

`Aggregation` function returns a `Scalar` value to a column or an expression evaluated by iterating a table expression.

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
