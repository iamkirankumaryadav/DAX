### Date Table

- `Time Intelligence` needs date table.
- All dates should be present ( no gap )
- Starting from `1st` January to `31st` December ( Even if the data is not present from 1st January )
- Including every quarter, month, week, day.
- Otherwise `Time Intelligence` will not work. 
- Power BI little bit helps to build the Date table but create manually for accuracy.

### How Power BI builds Date Table 

- `Auto` date / time : Power BI engine automatically creates date and time table in the background.
- But it only considers the dates available in the tables ( Order date, Delivery date, Birthdate, etc )
- And we cannot customize the auto generated date and time.
- The range it selects is unpredective ( Starting Date will be the Birtdate of a Customer which can be more than 100 years )
