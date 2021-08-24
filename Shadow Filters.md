### Shadow Filters Context

A shadow filter context is special kind of filter context, created by `Iterators`

When an iterator creates a `row` context, it also creates a shadow filter context.

Shadow filter context contains all the rows which are visible in the table that is iterated.

```
AVERAGEX (
    Customer, 
    CALCULATE ( SUM ( Sales[Quantity] ) )        
```

Here `AVERAGEX` creates a shadow filter on the entire Customer table.
