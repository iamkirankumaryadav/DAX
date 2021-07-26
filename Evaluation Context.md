### Evaluation Context 

Easy to `understand` and easy to forget so `practice`

Any `Slicer` of `Filter` which is being applied to the report will change the way the number is calculated.

Value of each `cell` is calculated according to the different combinations of applied filters.

### 1. Filter Context  

`Filters` working on your model

Defined by : 

- `Row` Selection
- `Column` Selection
- Report `Filters`
- `Slicer` Selection

### 2. Row Context

An existing iteration happening over each `row` of the table.

Calculation happening `row` by `row`, then there is row context on the table.

Starting any expression with `SUMX` or any iterator creates a row context on the table.

Calculated column is also calculated at `row` context automatically.
