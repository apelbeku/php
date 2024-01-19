
# Null Data Type

Null is special data type that representts a variable with no value

## Condition For Being Null

a variable can be null:

- If it's assigned the ```constant null```
- It hasn't been defined yet
- Or it's has been unset

### Null Constant

```php
$x = null;

echo $x;
var_dump($x);
```

the other way to check it using function call ```is_null()```

```php
$x = null;

var_dump(is_null($x)); // or we can using comparison operator
var_dump($x === null);
```

### Undefined

```php
var_dump(is_null($x));
```

### Unset

```php
$x = 123;

var_dump($x);

unset($x);

var_dump($x);
```

## Casting

When null casted to a string, it's casting to an empty string, e.g:

```php
$x = null;

var_dump((string) $x); # This is what happend when you trying to echo $x = null
```

