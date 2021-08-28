### Terms

Unit `Price` : Price of a `single` piece of an item.

Unit `Cost` : Total expenditure incurred by company on produce, store, pack and sell a `single` unit of a product.

Net `Price` : Value at which a `Product` or `Service` is sold after all taxes and other costs are added and all discounts subtracted. What the `customer` pays to `seller`

`Margin` : `Net` Price - `Cost` Price.

`Sales Amount` = `Revenue`

### Basic Measures

```
Sales Amount = SUMX ( Sales, Sales[Net Price] * Sales[Quantity] )

Total Cost = SUMX ( Sales, Sales[Unit Cost] * Sales[Quantity] )

Margin = [Sales Amount] - [Total Cost]
```
