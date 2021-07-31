### CALCULATE

The most important funtion in `DAX`

### Expanded Tables

Expanded tables contain all the columns of the base ( `fact` table ) table plus all the columns ( `lookup` table ) on the `ONE` side of the relationship.

### Context Transition

Process of turning `Row` context into `Filter` context.

By default, Calculated Columns understand `Row` context but no `Filter` context.

To Create `Filter` context at `Row` level, `CALCULATE` is used. 

### Evaluation Order 

```
Sales of Store 7 (CALCULATE) = 
CALCULATE (
    [Sales],                    // 3rd
    Store[Store ID] = 7,        // 1st Filters are evaluated first.
    Product[Group] = "Gadgets"  // 2nd
)
```

If the Function contains `Modifiers`

```
Sales of Store 7 (CALCULATE) = 
CALCULATE (
    [Sales],                    // 4th
    Store[Store ID] = 7,        // 2nd Filters are evaluated after Modifiers.
    Product[Group] = "Gadgets"  // 3rd
    ALL (                       // 1st Modifier is evaluated first
         Store                  
    )
)
```

### CALCULATE Modifiers

<table>
    <tr><th colspan=2>Modify Filters</th></tr>
    <tr><td>ALL</td><td></td></tr>
    <tr><td>ALLSELECTED</td><td></td></tr>
    <tr><td>ALLNOBLANKROW</td><td></td></tr>
    <tr><td>ALLEXCEPT</td><td></td></tr>
    <tr><td>KEEPFILTERS</td><td></td></tr>
    <tr><td>REMOVEFILTERS</td><td></td></tr>
</table>

`ALL` is a table function and `CALCULATE` Modifier.

`ALL` : Ignores  previous existing filters on the table, Return `Distinct` values if only one `column` is passed.

`KEEPFLTERS` : Does not remove an existing column or table filter ( adds new filter context )

`REMOVEFILTERS` : Removes Filters from the specified tables or columns.

`INTERSECT` : Multiple filters.

`OVERWRITE` : Nested filters. 

`ADDFILTER` : Similar `KEEPFILTERS`

<table>
    <tr><th colspan=2>Use Relationships</th></tr>
    <tr><td>USERELATIONSHIP</td><td>Use ( Inactive ) Relationship</td></tr>   
</table>

<table>
    <tr><th colspan=2>Change Filter Propagation ( Flow )</th></tr>
    <tr><td>CROSSFILTER</td><td>Between two connected tables</td></tr>   
</table>
