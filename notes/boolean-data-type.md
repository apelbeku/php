# Boolean Data Types

Boolean is a simple representation of a truth value, it can iether be `true` or `false`

`true` or `false` are predefined constant that comes with **PHP** and they are also case insensitive, so you can use UPPERCASE or LOWERCASE or you can mix and match highly recommended to just stick with one and stay consistent, i personally prefer
with lowercase

```php
/**
 * Booleans are mostly used within control
 * structures like loops or if else conditionals
 */
$isComplete = true;

if ($isComplete) {
    # do something
    echo "success";
} else {
    # do something
    echo "fail";
}
```

Other data types that could be converted to
booleans on the fly by **PHP**, and they could be
evaluated to either `true` or `false`

- `Int 0 -0 = false;`
- `floats  0.0 -0.0 = false;`
- `'' = false;`
- `'0' = false;`
- `[] = false;`
- `null = false;`
- anything else pretty much will evaluate as true even the negative numbers

## Checking Boolean

Checking boolean type whether is string or interger

- using `var_dump()`
- using `is_bool()`

```php
$isComplete = true;

var_dump($isComplete);
// or
var_dump(is_bool($isComplete));
```
