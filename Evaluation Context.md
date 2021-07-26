### Evaluation Context 

Easy to `understand` and easy to forget so `practice`

Any `Slicer` of `Filter` which is being applied to the report will change the way the number is calculated.

Value of each `cell` is calculated according to the different combinations of applied filters.

### 1. Filter Context  

`Filters` working on your model.

Defined by : 

- `Row` Selection
- `Column` Selection
- Report `Filters`
- `Slicer` Selection
- `Filter` tables


### 2. Row Context

An existing iteration happening over each `row` of the table.

- Calculation happening `row` by `row`, then there is row context on the table.
- Starting any expression with `SUMX` or any iterator creates a row context on the table.
- Calculated column is also calculated at `row` context automatically, they have there own `row` context.
- A `Filter` context filters table and `Row` context iterates over each rows of the table.

### Filters and Relationships

- `Row` Context 
- `Filter` Context
- `One` Side
- `Many` Side

`Row` Context do not interact in anyway with Relationships.

`Filter` Context automatically moves through Relationships ( Following the `Rules` developed by the `Model` )

`Filter` Context moves over Relationship from `One` Side to `Many` Side, therefore appying a `FILTER` on `One` Side automatically filters any table on the `MANY` Side.

### RELATED

`Row` context on the `Many` Side of the Relationship and you want to access a column that is on the `One` Side.

### RELATEDTABLE

`Row` context on the `One` Side of the Relationship and you want to access a column that is on the `Many` Side.
- All the rows on the `Many` Side which have relationship with the Current `Row` on the `One` Side.
