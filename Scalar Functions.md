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
// Better way to count the Distinct Rows.

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

```DAX
// How the Code is written

Measure Name =
SUM ( 'Table Name'[Column Name] )

// How it's interpreted by DAX

Measure Name =
SUMX (
   'Table Name',
   'Table Name'[Column Name]
)
```

`Converting` fields into desired formats i.e. `Text` to `Dates`, `Integers` to `Currency`, etc.

<table>
  <tr><th colspan=2>Rounding Functions</th></tr>
  <tr><td>INT(Number)</td><td>Round a number to an Integer.</td></tr>
  <tr><td>ROUND(Number, Digit)</td><td>Round a number to a specific digit.</td></tr>
  <tr><td>ROUNDUP(Number, Digit)</td><td>Round a number up.</td></tr>
  <tr><td>ROUNDDOWN(Number, Digit)</td><td>Round a number down.</td></tr>
  <tr><td>MROUND(Number, Multiple)</td><td>Round a number to desired multiple.</td></tr>
  <tr><td>TRUNC(Number)</td><td>Remove decimals.</td></tr>
  <tr><td>FIXED(Number)</td><td>Round a number down and return as text.</td></tr> 
  <tr><td>CEILING(Number)</td><td>Round up a number to nearest integer.</td></tr> 
  <tr><td>FLOOR(Number)</td><td>Round down a number to nearest integer.</td></tr> 
</table>

```DAX
// Decimal Value  
INT(3.14567)          = 3
ROUND(3.14467, 2)     = 3.14
ROUNDUP(3.14467, 2)   = 3.15
ROUNDDOWN(3.14467, 2) = 3.14
FIXED(3.14467, 2)     = '3.14'

// Time Value
MROUND(9:34:15 AM, "0.15")   = 9:30:00 AM  -- Minute Round.
FLOOR(9:34:15 AM, "0.15")    = 9:30:00 AM  -- Rounds the minute component down to nearest multiple.
CEILING(9:34:15 AM, "0.15")  = 9:45:00 AM  -- Rounds the minute component up to nearest multiple.
```

`Evaluating` logical tests and returns value `TRUE` or `FALSE`

<table>
  <tr><th colspan=2>Logical Functions</th></tr>
  <tr><td>IF</td><td>Add IF ELSE Condition.</td></tr>
  <tr><td>AND</td><td>TRUE only if both are TRUE.</td></tr>
  <tr><td>OR</td><td>FALSE only if both are FALSE.</td></tr>
  <tr><td>NOT</td><td>Condition is NOT True.</td></tr>
  <tr><td>SWITCH</td><td>Add Multiple Case with conditions.</td></tr> 
  <tr><td>COALESCE</td><td>Count of all the values in a column.</td></tr> 
</table>

`Check` the value or data type of the value and returns `TRUE` or `FALSE`

<table>
  <tr><th colspan=2>Logical Functions</th></tr>
  <tr><td>ISBLANK</td><td>Check whether a value is blank.</td></tr>
  <tr><td>ISERROR</td><td>Check whether a value is an error.</td></tr>
  <tr><td>ISLOGICAL</td><td>Check whether a value is a logical value.</td></tr>
  <tr><td>ISNUMBER</td><td>Check whether a value is a number.</td></tr>
  <tr><td>ISNONTEXT</td><td>Check whether a value is not a text.</td></tr>
  <tr><td>ISTEXT</td><td>Check whether a value is text.</td></tr>
  <tr><td>SWITCH</td><td>Add Multiple Case with conditions.</td></tr> 
  <tr><td>COALESCE</td><td>Count of all the values in a column.</td></tr> 
</table>
