[← Terug](/)

# Laravel en PHP

Alle richtlijnen die hier beschreven staan zijn precies dat, richtlijnen. Het is de bedoeling dat iedereen zich zo goed mogelijk aan deze richtlijnen houd, maar er kan van worden afgeweken indien hier een goed reden voor is.

- [Ternary operators](#ternary-operators)

## PHP

Alle PHP code die we schrijven moet voldoen aan de [PSR-1](http://www.php-fig.org/psr/psr-1/) en [PSR-2](http://www.php-fig.org/psr/psr-2/) standaarden. Hiernaast moet iedere applicatie die wij ontwikkelen zo goed mogelijk voldoen aan de punten beschreven op [12factor.net](https://12factor.net/). Wij volgen deze standaarden om het ontwikkelen van een applicatie met een team van meerdere personen te stroomlijnen, applicaties duurzaam en onderhoudbaar te maken. En om ieder project dat wij opleveren met zo min mogelijk frictie te kunnen hosten in een moderne, schaalbare cloud omgeving. 

### Ternary operators

Ieder gedeelte van een ternary if statement zou op een eigen regel moeten staat, behalve als het een heel kort statement is.

```php
// Good
$result = $foo instanceof Model
    ? $foo->name
    : 'A default value';

$result = $foo ? 'foo' : 'bar';

// Bad
$result = $foo instanceof Model ?
    $foo->name : 
   'A default value';
```
