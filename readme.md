# Nova Grouped Field

[![Total Downloads](https://img.shields.io/packagist/dt/dillingham/nova-grouped-field.svg?style=flat-square)](https://packagist.org/packages/dillingham/nova-grouped-field)

This Nova field provides a clean way to combine multiple fields into one output.

# Installation

Installing with composer:

```bash
composer require dillingham/nova-grouped-field
```

# Usage

```php
use NovaGroupedField\Grouped;
```
```php
fields()
{
    return [
        Grouped::make('User')->fields([
            BelongsTo::make('Account'),
            BelongsTo::make('User'),
        ])
    ]
}
```
![nova-grouped-field-1](https://user-images.githubusercontent.com/29180903/48378053-9c387600-e69d-11e8-9faa-dece657fa1ba.png)

# Options

There are a few chainable options available

### seperator($value)

If you would like to override the default slash seperator

```php
Grouped::make('User')->fields([
    BelongsTo::make('Account'),
    BelongsTo::make('User'),
])->seperator('-')
```
![nova-grouped-field-seperator](https://user-images.githubusercontent.com/29180903/48378215-2a146100-e69e-11e8-90c8-269cf42b1b65.png)

### showLabels()

If you want to output the original labels inline with the values

```php
Grouped::make('User')->fields([
    BelongsTo::make('Account'),
    BelongsTo::make('User'),
])->showLabels()
```
![nova-grouped-field-labels](https://user-images.githubusercontent.com/29180903/48378354-5cbe5980-e69e-11e8-8e10-28187f473c5b.png)

### removeLinks()

If you just want plain text output for relationships

```php
Grouped::make('User')->fields([
    BelongsTo::make('Account'),
    BelongsTo::make('User'),
])->removeLinks()
```
![nova-grouped-field-no-links](https://user-images.githubusercontent.com/29180903/48378417-7fe90900-e69e-11e8-8b8a-5e0a5ac2a431.png)

### Native options

`Grouped` is a nova field like any other.

You can use authorization like `->canSee()`

You can decide when to show like `->hideFromIndex()`

You can even override using `displayUsing()`
