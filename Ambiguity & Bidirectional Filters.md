### Ambiguity 

- `Bidirectional` filters creates `Ambiguous` models ( Uncertain, Not clear )
- In a `data model`, you can traverse through one table to another table according to the relationship (`One` to `Many` is the best relationship)
- Normally traversal happens in only one direction, but due to certain requirement we need to enable `bidirectional` filters.
- While traversing the `filters` of the tables also move along the direction.
- If you are traversing from source to destination through more than one path & in both directions then it means `Ambiguity`
- Engine does not know exactly which path it should follow in order to move a filter from one table to another table.
- There is a set of rules with bidirectional filters.
- `Correct` model : Only Unidirectional relationships ( No bidirectional relationship anywhere )
- Model will not complain about the `Ambiguity` but the calculations may give wrong results.
- Try to avoid `Ambiguity` as much as you can ( Try only use One to Many relationships in the model )
