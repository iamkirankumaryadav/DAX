### Hierarchies 

- Predefined exploration path
- `Year` `Quarter` `Month` `Day` 
- `Category` `Sub Category` `Product`
- `Continent` `Country` `State` `City` `Pincode`
- Make browsing a `Model` easier.
- All columns of Hierarchy should belong to same table ( You cannot create Hierarchy between columns of different tables )
- Use `RELATED` to move column in the right place.

### Parent / Child Hierarchy

`Manager` `Salesperson` ( Where one person report another person )

`CDO` `Zonal Manager` `BDM` `Branch Manager` `Branch Assistant` `Field Executive`

- Leaf Node should not be expanded.
- Each Node contains SUM of all child nodes.
