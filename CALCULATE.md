### CALCULATE

The most important funtion in `DAX`

- Overwrite a `filter context` at the individual columns level

`ALL` : Remove  previous existing filters on the table, Return `Distinct` values if only one `column` is passed.

`KEEPFLTERS` : Add filters over existing filter or without removing current existing filter.

`REMOVEFILTERS` : Similar to `ALL`

`INTERSECT` : Multiple filters.

`OVERWRITE` : Nested filters. 

`ADDFILTER` : Similar `KEEPFILTERS`

### Expanded Tables

Expanded tables contain all the columns of the base ( `fact` table ) table plus all the columns ( `lookup` table ) on the `ONE` side of the relationship.

