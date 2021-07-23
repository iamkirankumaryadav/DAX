### 1 Entity = 1 Table

All the information that describes a business entity should be included in `individual` table.

- e.g. Customer, Product, Employee, Sales, Return, Store, etc.

A right way to define a table is `expand` it's attributes.

- e.g. Product Table should have Name, Group, Category, Sub Category, etc.

So that we can create a `relationship` between two different Table ( Business Entities )

It creates a better `granularity` and help us to describe each attribute in more simple way.

### Normalization

- `Remove` the duplicated or redundant data.

- `Reduce` the size of the table.

- Having a seperate table for each Business entity.

### Denormalization

- Creating a `single` table with all Business entity and attributes including redundancy and duplicated data.

### Star Schema

- `Best` Schema for Power BI
- Separation between `Facts` and `Dimensions`

#### 1. Fact 
- Data table with all the important `quantitative` numeric metrics.  
- price, quantity, cost, margin, etc.
- Transactions, Sales, Returns, etc.
- Especially used for Aggregating ( SUM, AVERAGE, MIN, MAX, COUNT )
- Contains various `Foreign` keys and related to many dimension tables. 

#### 2. Dimension
- Something that describes a `fact`
- Describes the `qualitative` attributes of the table ( group, category, subcategory )
- No duplicates or redundancy.
- Especially used for grouping, slicing and filtering.
- Contains only `Primary` keys and `Unique` keys ( Single row for each data )
