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
                                            <tr><th colspan=3>Arithmetic Operator</th></tr>
                                            <tr><td>Addition</td><td>+</td><td>1 + 3</td></tr>
                                            <tr><td>Subtraction</td><td>-</td><td>7 - 3</td></tr>
                                            <tr><td>Multiplication</td><td>*</td><td>5 * 3</td></tr>
                                            <tr><td>Division</td><td>/</td><td>10 / 5</td></tr>
                                            <tr><td>Exponent</td><td>^</td><td>5 ^ 2</td></tr>
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
                                            <tr><th colspan=3>String or Logical Operator</th></tr>
                                            <tr><td>Concatenate Strings</td><td>&</td><td>[City] & " " & [State]</td</tr>
                                            <tr><td>AND</td><td>&&</td><td>[State] = "MH" && [Country] = "IND"</td</tr>
                                            <tr><td>OR</td><td>||</td><td>[State] = "MH" || [Country] = "IND"</td</tr>
                                            <tr><td>OR with Multiple Values</td><td>[Region] IN {"AMS","APJ","EMEA"}</td</tr>
                                 </table>
                      </td>
           </tr>         
</table>
