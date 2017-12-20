[← Terug](/)

# Laravel en PHP

Alle richtlijnen die hier beschreven staan zijn precies dat, richtlijnen. Het is de bedoeling dat iedereen zich zo goed mogelijk aan deze richtlijnen houd, maar er kan van worden afgeweken indien hier een goed reden voor is.

- [Artisan commands](#artisan-commands)
- [Ternary operators](#ternary-operators)

## PHP

Alle PHP code die we schrijven moet voldoen aan de [PSR-1](http://www.php-fig.org/psr/psr-1/) en [PSR-2](http://www.php-fig.org/psr/psr-2/) standaarden. Hiernaast moet iedere applicatie die wij ontwikkelen zo goed mogelijk voldoen aan de punten beschreven op [12factor.net](https://12factor.net/). Wij volgen deze standaarden om het ontwikkelen van een applicatie met een team van meerdere personen te stroomlijnen, applicaties duurzaam en onderhoudbaar te maken. En om ieder project dat wij opleveren met zo min mogelijk frictie te kunnen hosten in een moderne, schaalbare cloud omgeving. 

### Artisan commands

De naam van ieder artisan command zou kebab-case moeten zijn. 

```php
// Good
php artisan delete-old-records

// Bad
php artisan deleteOldRecords
```

Een command zou altijd feedback moeten geven om te laten zien dat het succesvol uitgevoerd is.

```php
class Foo extends Command
{
    public function handle()
    {
        // Do something

        $this->comment('Done!');
    }
}
```

Wanneer een artisan command in de scheduler gebruikt wordt zou hier altijd de `::class` constant voor gebruikt moeten worden in plaats van de signature.

```php
class Kernel extends ConsoleKernel
{
    protected function schedule(Schedule $schedule)
    {
        // Good
        $schedule->command(Foo::class, ['--force'])->daily();
        
        // Bad
        $schedule->command('foo --force')->daily();
    }
}
```

### Ternary operators

Ieder gedeelte van een ternary if statement zou op een eigen regel moeten staat, behalve als het een heel korte statement is.

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
