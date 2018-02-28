[← Terug](/)

# Laravel en PHP

Alle richtlijnen die hier beschreven staan zijn precies dat, richtlijnen. Het is de bedoeling dat iedereen zich zo goed mogelijk aan deze richtlijnen houd, maar er kan van worden afgeweken indien hier een goed reden voor is.

- [Artisan commands](#artisan-commands)
- [CRUD](#crud)
- [Development environment](#development-environment)
- [Development packages](#development-packages)
- [File and Folder name conventions](#file-and-folder-name-conventions)
- [Form request validation](#form-request-validation)
- [Resource structure](#resource-structure)
- [Ternary operators](#ternary-operators)
- [Variables](#variables)

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

### CRUD

Hou de volgende standaard aan met het ontwikkelen van een crud:

Index:
```php
    /**
     * @return View
     */
    public function index(): View
    {
        return view('user.index', [
            'users' => User::orderBy('name')->paginate(25),
        ]);
    }
```
Create:
```php
    /**
     * @return View
     */
    public function create(): View
    {
        return view('user.create', [
            'user'  => new User(),
        ]);
    }
```

Store:
```php
    /**
     * @param UserRequest $request
     * @return RedirectResponse
     */
    public function store(UserRequest $request): RedirectResponse
    {
        if (User::create($request->all())) {
            return redirect()
                ->route('user.index')
                ->with('success', __('notifications.success'));
        }

        return redirect()
            ->route('user.index')
            ->with('failed', __('notifications.failed'));
    }
```

Edit:
```php
    /**
     * @param User $user
     * @return View
     */
    public function edit(User $user): View
    {
        return view('user.edit', [
            'user'  => $user,
        ]);
    }
```

Update:
```php
    /**
     * @param UserRequest $request
     * @param User        $user
     * @return RedirectResponse
     */
    public function update(UserRequest $request, User $user): RedirectResponse
    {
        if ($user->update($request->all())) {
            return redirect()
                ->route('user.index')
                ->with('success', __('notifications.success'));
        }

        return redirect()
            ->route('user.index')
            ->with('failed', __('notifications.failed'));
    }
```

Destroy:
```php
    /**
     * @param User $user
     * @return RedirectResponse
     * @throws \Exception
     */
    public function destroy(User $user): RedirectResponse
    {
        if ($user->delete()) {
            return redirect()
                ->route('user.index')
                ->with('success', __('notifications.success'));
        }

        return redirect()
            ->route('user.index')
            ->with('failed', __('notifications.failed'));
    }
```


### Development environment

Bij Divtag gebruiken we de volgende lokale ontwikkel omgevingen:

- [Homestead](https://laravel.com/docs/5.5/homestead "Homestead")
- [Valet](https://laravel.com/docs/5.5/valet "Valet")

### Development packages

Packages die standaard in de master van een project worden gezet in sprint 0.

Packages met de ``` --dev ``` flag:

- [Laravel debugbar](https://github.com/barryvdh/laravel-debugbar "Laravel debugbar")
- [Laravel ide helper](https://github.com/barryvdh/laravel-ide-helper "Laravel ide helper")
- [Doctrine DBAL](https://github.com/doctrine/dbal "Doctrine DBAL")
- [Squizlabs php_codesniffer ](https://github.com/squizlabs/PHP_CodeSniffer "PHP Codesniffer")

Packages ***zonder*** de  ``` --dev ``` flag:

- [Predis](https://github.com/nrk/predis "Predis")
- [Sentry](https://github.com/getsentry/sentry-laravel "Sentry")

Package die gebruikt wordt voor formulieren, ***zonder*** de ```--dev``` flag

- [Laravel collective Form](https://laravelcollective.com/docs/master/html "Laravel collective Form")

### File and Folder name conventions

- Controllers worden geschreven in enkelvoud en CamelCase
- View folders worden geschreven in enkelvoud en snake_case
- View files worden geschreven in enkelvoud en snake_case

### Form request validation

Gebruik wanneer er meerdere validatie regels op een veld zijn altijd een array, hierdoor blijft de validatie een stuk beter leesbaar en kan er zonder problemen van meerdere regels code gebruikt worden gemaakt wanneer er veel validatie regels nodig zijn.

```php
public function rules()
{
    // Good
    return [
        'title' => ['required', 'min:10', 'max:255'],
    ];
    
    // Bad
    return [
        'title' => 'required|minx:10|max:255',
    ];
}
```

Zet binnen een request consistent de regels in strings of arrays. Anders worden de regels snel onoverzichtelijk.

```php
public function rules()
{
    // Good
    return [
        'title'       => ['required'],
        'description' => ['required', 'max:255'],
    ];
    
    // Bad
    return [
        'title'       => 'required',
        'description' => ['required', 'max:255'],
    ];
}
```

Gebruik de methodes van de `Rule` class wanneer deze beschikbaar zijn. Hierdoor kunnen de regels makkelijker leesbaar geformat worden en is er syntax highlighting beschikbaar. Dit maakt de regels een stuk beter leesbaar, zeker wanner er complexe regels nodig zijn zoals bij `unique` of `exists` regels vaak het geval is.

```php
public function rules()
{
    // Good
    return [
        'email' => [
            Rule::unique('users', 'email_address'),
        ],
    ];
    
    // Bad
    return [
        'email' => [
            'unique:users,email_address',
        ],
    ];
}
```

### Resource structure

De folder structuur in de resource map van de blade views:

```php
resources/
        views/
            layouts/
                    app.blade.php  
                    auth.blade.php
        
                    partials/
                            left_nav.blade.php
                            top_nav.blade.php
        
            user/
                    index.blade.php
                    create.blade.php
                    edit.blade.php
                    
                    partials/
                            form.blade.php
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

### Variables

Alle variabelen worden geschreven in CamelCase.

```php
    $normalVariable = 'data';
```

Uitzondering:

Data sturen naar de view gaat middels een array.
Array keys worden geschreven in snake_case.
Deze variabelen worden in de view aangeroepen met snake_case.

```php
    // Controller:
    return view('license_type.index', [
        'license_types' => $licenseTypes,
    ]);
    
    // View:
    @foreach ($license_types as $licenseType)
        // loop
    @endforeach
```