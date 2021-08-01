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
GENERATE (                                   // Generate and Evaluate Sales Amount 
    VALUES ( 'Product'[Category] ),          // for Distinct combination of Top 3 
    CALCULATETABLE (                         // Product based on Distinct Category.
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

### GENERATE

Equivalent to `APPLY` in `SQL`

```DAX
GENERATE (
    VALUES ( 'Product Category'[Category] ),
    SELECTCOLUMNS (
        RELATEDTABLE ( 'Product Subcategory' ),
        "Subcategory", 'Product Subcategory'[Subcategory]
    )
)
// Combines every row of first argument with every row of second argument.
```
### ROW

Create a one `Row` with specified Column Name. 

```DAX
Row Demo = 
ROW ( 
    "Name", "Kirankumar",
    "Age", 25,
    "Designation", "Data Scientist"
)
```

```DAX
Output :
```
<table>
<tr colspan=3><th>Name</th><th>Age</th><th>Designation</th></tr>
<tr><td>Kirankumar</td><td>25</td><td>Data Scientist</td></tr>
</table>

```DAX
ROW ( "Sales", [Sales Amount], "Margin", [Margin] )
```

```DAX
ROW (
    "Jan Sales",
    CALCULATE (
        SUM ( 'Sales'[Quantity] ),
        'Date'[Month] = "January"
    )
    "Feb Sales",
    CALCULATE (
        SUM ( 'Sales'[Quantity] ),
        'Date'[Month] = "February"
    )
)    
```

`Filter` can be added to the single row.

```DAX
CALCULATETABLE (
    ROW (
        "Sales", [Sales Amount], 
        "Margin", [Margin]
    ),
    'Product'[Color] = "Red"
)
```

### DATATABLE

Create a full `Table`, useful to build small temporary tables.

```DAX
DATATABLE (
          "Price Range", STRING,
          "Minimum Price", CURRENCY,
          "Maximum Price", CURRENCY,
          {
              ( "Low", 0, 10 ),
              ( "Medium", 10, 100 ), 
              ( "High", 100, 1000 )              
          }
)
```
