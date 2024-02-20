# String Data Type

String is a series of character, when a value is enclose within single or double quote it's string.

## Different Single & Double Quote

| Single               | Double           |
| -------------------- | ---------------- |
| can not use variable | can use variable |

```php
$firstname = 'apel';
$lastname = "${firstname} beku";

echo $lastname;
```

## Accessing Specific Character In String

We can use 0-base index to access it which is the same way as accessing array.

```php
$firstname = 'apel';
$lastname = 'beku';

$name = $firstname . ' ' . $lastname;
echo $name . <br />;

// $name[2] = 3; If you want modify specific character
// $name[-2] = 3; Same way if you want modify it from back
echo $name[3]; // This will echo e from 'apel'
echo $name[-4]; // If you want echo from the back

// $name[10] = 2; It will add the empty string and add the 2 to the last, be aware of it
var_dump($name);
```

## Heredoc & Nowdoc

Heredoc and Nowdoc are ways to handle long and multiline string that may contain complex expression, single or double qoute without need to escape them

| Heredoc                             | Nowdoc                             |
| ----------------------------------- | ---------------------------------- |
| Treat string if using doouble quote | Treat string if using single quote |
| you could have avriable             | you couldn't have variable         |

### Heredoc

```php
$x = 2
$y = 3

$text = <<<TEXT
Line 1 $x
Line 2 $y
Line 4
Line 3 ' "

TEXT;

// nl2br() to make new line
echo nl2br($text);
```

### Nowdoc

```php
$x = 2
$y = 3

$text = <<<'TEXT'
Line 1 $x
Line 2 $y
Line 4
Line 3 ' "

TEXT;

// nl2br() to make new line
echo nl2br($text);
```
