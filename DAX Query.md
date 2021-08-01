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
    10,                                  // Top 10 Rows
    VALUES ( 'Product'[Product Name] ),  // Distinct Values ( Product Name )
    [Sales Amount]                       // Evaluate Sales Amount
)
```      
