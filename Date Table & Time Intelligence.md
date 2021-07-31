### Date Table & Time Intelligence

- `Time Intelligence` needs date table.
- Must contain all the dates ( days ) for the year ( no gap )
- Starting from `1st` January to `31st` December ( Even if the data is not present from 1st January )
- Including every quarter, month, week, day.
- Otherwise `Time Intelligence` will not work. 
- Power BI little bit helps to build the Date table but create manually for accuracy.

### How Power BI builds Date Table 

- `Auto` date / time : Power BI engine automatically creates date and time table in the background.
- But it only considers the dates available in the tables ( Order date, Delivery date, Birthdate, etc )
- And we cannot customize the auto generated date and time.
- The range it selects is unpredective ( Starting Date will be the Birtdate of a Customer which can be more than 100 years )

### CALENDARAUTO

`CALENDARAUTO` : Automatically creates a calendar table based on the dataset content.

### CALENDAR

We can manually specify `Start` date and `End` date.

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

### Mark as Date table

- Need to `mark` calendar as date table.
- `Set` the column containing the `[Date]`

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
