### DAX Query

### CROSSJOIN

- `CARTESIAN` Product between two tables.
- Generates `Distinct` combinations between the two columns or tables.

```DAX
ADDCOLUMNS (
    CROSSJOIN (                           // Distinct combination of Brand and Color
        DISTINCT( 'Product'[Brand] ),     
        DISTINCT( 'Product'[Color] )
    ),
    "Sales", [Sales Amount] + 0           // Add New Column that display Sales Amount for the Distinct combinations.
)
```

### TOPN

- Returns the `TOP N` rows sorting in an ascending order.

```DAX
TOPN (
    10,                                       // Top 10 Rows
    ADDCOLUMNS (
        VALUES ( 'Product'[Product Name] ),  // Distinct Values ( Product Name )
        "Sales", [Sales Amount]              // Add New Column and Evaluate Sales Amount
   ),
   [Sales] // Sales Amount is Evaluated so no need to Evaluate again and can be displayed directly.
)

```      

`Top 3` Sales for each Category

```DAX
GENERATE (  
    VALUES ( 'Product'[Category] ), 
    CALCULATETABLE (
        TOPN (
             3,
             ADDCOLUMNS (
                VALUE ( 'Product'[Name] )
                "Sales", [Sales Amount]
             ),
             [Sales]
        )
    )
)
```
