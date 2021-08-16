### Summarization

- In any company, `Millions` of Transaction Data with Thousands of Rows per day have been captured.
- From this type of large data, we can prepare a `Summary` table using `Aggregation` and represent summarize visual.
- Performance of visual will be faster if data is fetching from the summary table instead of Raw Data. 
- Will get more optimized reports for a better experience.
- However, in summary table you will loose the ability to `Cross Filter` on any level of aggregation. 

### DAX Functions for Summarization

`SUMMARIZE`

- Creates a `Summary` of the table by grouping and aggregating multiple columns on the basis of existing relationships.
- Other `Columns` from the `RELATED Tables` can be included ( If `Many` to `One` Relationships exist to reach Reference Tables )

```DAX

SUMMARIZE (
    Table,                  // Table in the data model | Calculated table | Function which returns table | Variable that stores table expression.
    Group By Column Name,   // Column name from the specified table or any column from a table that has relationship with the first parameter table.
    Name,                   // Name for the summary column in double quotes ("")
    Expression              // Aggregation component of the summary table.
)
```
