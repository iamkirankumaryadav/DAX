# DAX
Data Analysis Expressions | [SQLBI](https://www.sqlbi.com/) | [DAX Guide](https://dax.guide/) | [DAX Formatter](https://www.daxformatter.com/) | [DAX Do](https://dax.do/) | [DAX Patterns](https://www.daxpatterns.com/)

`DAX` is a functional language, the execution flows with function calls.

```DAX
Amount = SUM (
           FILTER ( VALUES ( 'Date'[Year] ), 'Date'[Year] < 2005 ),
           IF ( 'Date'[Year] >= 2000, [Sales Amount] * 100, [Sales Amount] * 90 )
         )
```

<table align=center>
           <tr><th colspan=3><h3>DAX Operators</h3></th></tr>
           <tr>
                      <td>
<table>
           <tr><th colspan=2>Arithmetic Operator</th></tr>
           <tr><td>Addition</td><td>+</td></tr>
           <tr><td>Subtraction</td><td>-</td></tr>
           <tr><td>Multiplication</td><td>*</td></tr>
           <tr><td>Division</td><td>/</td></tr>
           <tr><td>Exponent</td><td>^</td></tr>
</table>
                                 </td>
                       <td>
<table>
           <tr><th colspan=2>Comparison Operator</th></tr>
           <tr><td>Equal to</td><td>=</td></tr>
           <tr><td>Greater than</td><td>></td></tr>
           <tr><td>Less than</td><td><</td></tr>
           <tr><td>Greater than or Equal to</td><td>>=</td></tr>
           <tr><td>Less than or Equal to</td><td><=</td></tr>
           <tr><td>Not equal to</td><td><></td></tr>
</table>
                                 </td>
                       <td>
<table>
           <tr><th colspan=2>String or Logical Operator</th></tr>
           <tr><td>Concatenate Strings</td><td>&</td></tr>
           <tr><td>AND</td><td>&&</td></tr>
           <tr><td>OR</td><td>||</td></tr>
           <tr><td>OR with Multiple Values</td><td>IN</td></tr>
</table>
                                 </td>
           </tr>
           
</table>
