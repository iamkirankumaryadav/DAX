# DAX
Data Analysis Expressions | [SQLBI](https://www.sqlbi.com/) | [DAX Guide](https://dax.guide/) | [DAX Formatter](https://www.daxformatter.com/) | [DAX Do](https://dax.do/) | [DAX Patterns](https://www.daxpatterns.com/)

`DAX` is a functional language, the execution flows with function calls.

```DAX
Amount = SUM (
           FILTER ( VALUES ( 'Date'[Year] ), 'Date'[Year] < 2005 ),
           IF ( 'Date'[Year] >= 2000, [Sales Amount] * 100, [Sales Amount] * 90 )
         )
```

### Important Terms

1. Data Table or `Fact` Table : Contains measurable values (cost, quantity and prices)
2. Lookup or `Dimension` Table : Provides descriptive attributes about each dimension.
3. `Foreign` Key : Contains multiple instances of each value, and are used to match the `Primary` keys in related Lookup tables.
4. `Primary` Key : Uniquely identifies each `Row` of a table, and match `Foreign` keys in related Data tables.
5. `Cardinality` : The uniqueness of values in the column. 


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
                                            <tr><th colspan=3>Comparison Operator</th></tr>
                                            <tr><td>Equal to</td><td>=</td><td>[City] = 'Mumbai'</td></tr>
                                            <tr><td>Greater than</td><td>></td><td>[Age] > 18</td></tr>
                                            <tr><td>Less than</td><td><</td><td>[Age] < 18</td></tr>
                                            <tr><td>Greater than or Equal to</td><td>>=</td><td>[Age] >= 18</td></tr>
                                            <tr><td>Less than or Equal to</td><td><=</td><td>[Age] <= 18</td></tr>
                                            <tr><td>Not equal to</td><td><></td><td>[City] <> "Mumbai"</td></tr>
                                 </table>
                      </td>
                      <td>
                                 <table>
                                            <tr><th colspan=2>String or Logical Operator</th></tr>
                                            <tr><td>&</td><td>[City] & " " & [State]</td</tr>
                                            <tr><td>&&</td><td>[State] = "MH" && [Country] = "IND"</td</tr>
                                            <tr><td>||</td><td>[State] = "MH" || [Country] = "IND"</td</tr>
                                            <tr><td>IN</td><td>[Region] IN {"AMS","APJ","EMEA"}</td</tr>
                                 </table>
                      </td>
           </tr>         
</table>
