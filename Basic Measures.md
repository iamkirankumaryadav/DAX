### Terms

Unit `Price` : Price of a `single` piece of an item.

Unit `Cost` : Total expenditure incurred by company on produce, store, pack and sell a `single` unit of a product.

Net `Price` : Value at which a `Product` or `Service` is sold after all taxes and other costs are added and all discounts subtracted. What the `customer` pays to `seller`

`Margin` : `Net` Price - `Cost` Price.

`Sales Amount` = `Revenue`

### Basic Measures

Any Model contains cetain basic measures.

```
Sales Amount = SUMX ( Sales, Sales[Net Price] * Sales[Quantity] )

Total Cost = SUMX ( Sales, Sales[Unit Cost] * Sales[Quantity] )

Margin = [Sales Amount] - [Total Cost]

Sales Quantity = SUM ( Sales[Quantity] )
```

### Pre Aggregated Measures

YTD, MTD, SPLY

```
YTD Sales Amount = 
CALCULATE (
    [Sales Amount],
    DATESYTD ( Date[Date] )
)

YTD Total Cost =
CALCULATE (
    [Total Cost],
    DATESYTD ( Date[Date] )
)    

YTD Margin = 
CALCULATE (
    [Margin],
    DATESYTD ( Date[Date] )
)  

YTD Sales Quantity = 
CALCULATE (
    [Sales Quantity],
    DATESYTD ( Date[Date] )
)  
```
