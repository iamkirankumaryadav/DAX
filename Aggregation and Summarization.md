### Aggregation and Summarization

- In any company, `Millions` of Transaction Data with Thousands of Rows per day have been captured.
- From this type of large data, we can prepare a `Summary` table using `Aggregation` and represent summarize visual.
- Performance of visual will be faster if data is fetching from the summary table instead of Raw Data. 
- Will get more optimized reports for a better experience.
- However, in summary table you will loose the ability to `Cross Filter` on any level of aggregation. 

### DAX Functions for Summarization

`SUMMARIZE`

```DAX

SUMMARIZE (
    Table, // Table in the Data Model | Calculated Table | Function which returns Table | Variable that stores Table Expression.
    Group By Column Name // Column Name from the specified table or any column from a table that has relationship with the first parameter table.
