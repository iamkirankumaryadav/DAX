# DAX
Data Analysis Expressions | [SQLBI](https://www.sqlbi.com/) | [DAX Guide](https://dax.guide/) | [DAX Formatter](https://www.daxformatter.com/) | [DAX Do](https://dax.do/) | [DAX Patterns](https://www.daxpatterns.com/)

`DAX` is a functional language, the execution flows with function calls.

```DAX
Amount = SUM (
           FILTER ( VALUES ( 'Date'[Year] ), 'Date'[Year] < 2005 ),
           IF ( 'Date'[Year] >= 2000, [Sales Amount] * 100, [Sales Amount] * 90 )
         )
```
