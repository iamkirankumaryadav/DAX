### Scalar Functions 

Use case : `Aggregating` a column of values into a single number.

e.g. `Average` customer age, `Maximum` product profit, `Sum` of revenue, `Count` of orders, etc.

<table>
  <tr><th colspan=2>Aggregation Functions</th></tr>
  <tr><td>SUM</td><td>Sum of all the values in a column.</td></tr>
  <tr><td>AVERAGE</td><td>Mean of all the values in a column.</td></tr>
  <tr><td>MIN</td><td>Minimum of all the values in a column.</td></tr>
  <tr><td>MAX</td><td>Maxmimum of all the values in a column.</td></tr>
  <tr><td>COUNT</td><td>Count of all the values in a column.</td></tr>
  <tr><td>COUNTA</td><td>Count of all the non empty values in a column.</td></tr>
  <tr><td>COUNTROWS</td><td>Count of the number of rows in a column.</td></tr>
  <tr><td>DISTINCTCOUNT</td><td>Count of all the unique rows in a column.</td></tr>
</table>

```DAX
-- Distinct Count 

Total Employee = 
COUNTROWS (
    VALUES (
        'Employee Lookup'
    )
)
```

<table>
  <tr><th colspan=2>Iterator Functions</th></tr>
  <tr><td>SUMX</td><td>Sum of all the values in a column.</td></tr>
  <tr><td>AVERAGEX</td><td>Mean of all the values in a column.</td></tr>
  <tr><td>MINX</td><td>Minimum of all the values in a column.</td></tr>
  <tr><td>MAXX</td><td>Maxmimum of all the values in a column.</td></tr>
  <tr><td>COUNTX</td><td>Count of all the values in a column.</td></tr> 
</table>

`Converting` fields into desired formats i.e. `Text` to `Dates`, `Integers` to `Currency`, etc.

`Evaluating` logical tests and returns value for `TRUE` and `FALSE`

<table>
  <tr><th colspan=2>Logical Functions</th></tr>
  <tr><td>IF</td><td>Add IF ELSE Condition.</td></tr>
  <tr><td>AND</td><td>TRUE only if both are TRUE.</td></tr>
  <tr><td>OR</td><td>FALSE only if both are FALSE.</td></tr>
  <tr><td>NOT</td><td>Condition is NOT True.</td></tr>
  <tr><td>SWITCH</td><td>Add Multiple Case with conditions.</td></tr> 
  <tr><td>COALESCE</td><td>Count of all the values in a column.</td></tr> 
</table>
