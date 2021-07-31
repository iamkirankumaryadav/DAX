### Date Table & Time Intelligence

<p href='#calendar'>CALENDAR</p>

- `Time Intelligence` needs date table.
- Must contain all the dates ( days ) for the year ( no gap )
- Must have atleast one field set as a `Date` or `DateTime` datatype.
- Cannot contain duplicate `Date` or `DateTime` values.
- If using `Time` component within `Date` column, all times must be identical ( i.e `12:00:00 AM` )
- Should be marked as a `Date` table.
- If `Time` is present in `Date` field, split the `Time` component into a new column.
- Starting from `1st` January to `31st` December ( Even if the data is not present from 1st January )
- Including every quarter, month, week, day.
- Otherwise `Time Intelligence` will not work. 
- Power BI little bit helps to build the Date table but create manually for accuracy.

### How Power BI builds Date Table 

- `Auto` date / time : Power BI engine automatically creates date and time table in the background.
- But it only considers the dates available in the tables ( Order date, Delivery date, Birthdate, etc )
- And we cannot customize the auto generated date and time.
- The range it selects is unpredective ( Starting Date will be the Birtdate of a Customer which can be more than 100 years )

<h3 name='calendar'> CALENDAR </h3>

Returns a table with one column of all dates between `Start` and `End` date. 

```
CALENDAR (
   DATE ( 2021, 01, 01 ),
   DATE ( 2021, 12, 31 )
)
```

We can also allow the table to take reference from existing table for `Start` and `End` dates.

```
CALENDAR (
   MIN ( 'Order Date' ),
   MAX ( 'Order Date' )
)
```

```
CALENDAR (
   DATE ( YEAR ( MIN ( Calendar[Transaction Date] ) ), 01, 01 ),
   DATE ( YEAR ( MAX ( Calendar[Transaction Date] ) ), 12, 31 )
)
```

### CALENDARAUTO

- Returns a table with one column of dates based on a Fiscal year end month.
- `Range` of dates is calculated automatically based on data in the model.

```DAX
CALENDARAUTO ( FiscalYearEndMonth ) 

// Fiscal Year End Month : 1 to 12 ( 1 - January, 2 - February .... 12 - December )
```

### Time Intelligence

- Useful for `Aggregating` date over time or `Comparing` date over time.
- `YTD` : Year To Date
- `QTD` : Quarter To Date
- `MTD` : Month To Date
- They all need a `Date Table` and `CALCULATE` function.
- `Running` Total
- Same Period
- `Working` Day
- `Fiscal` Year
