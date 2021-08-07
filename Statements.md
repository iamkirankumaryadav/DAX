### Statements

<table>
  <tr colspan=2><th>Index</th><th>Keywords</th></tr>
  <tr><th>1</th><td><a href=#var>VAR</a></td></tr>
  <tr><th>2</th><td><a href=#return>RETURN</a></td></tr>  
</table>

<h3 name=var>VAR</h3>

The `VAR` keyword introduces variables in an expression.

The results ( defined value or evaluated expressions ) of `VAR` statement is returned by `RETURN` statement.

```DAX
VAR Pi = 3.14                                                         // Defined 

VAR AreaOfCircle = SUMX ( Math, Pi * Math[Radius] * Math[Radius] )    // Expression

RETURN AreaOfCircle
```

<h3 name=return>RETURN</h3>

The `RETURN` keyword consumes variables defined in previous `VAR` statements.

It access to all expressions and results defined in the `VAR` statements before or above `RETURN`. 

```DAX
VAR Name = "Kirankumar"

RETURN Name
```
