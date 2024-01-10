
# Integer Data Type

Integer are numbers wihout any decimal points. the size of an integer though depends on the platform for 32-bit system it's from negative 2 bilion to positive 2 billion and for 64-bit it's much more, and you can check that easily by using predefined ```const```.

- ```PHP_INT_MIX```
- ```PHP_INT_MAX```
- ```PHP_INT_SIZE```

Integer can be specified in different way:

- decimal or base 10
    ```php
    $x = 10;
    $y = 5;

    echo $x, $y;
    ```
- hexadecimal or base 16
    ```php
    /**
      * Hexadecimal numbers are prefixed by 0x
      */
    $x = 0x2A; # the output is 42

    echo $x;
    ```
- octal or base 8
    ```php
    /**
      * Octal numbers are prefixed by 0
      */
    $x = 05; # the output is 5
    $y = 055; # the output is 45

    echo $x, $y;
    ```
- binary or base 2
    ```php
    /**
      * Binary numbers are prefixed by 0b
      */
    $x = 0b11; # the output is 3
    $y = 0b110; # the output is 6

    echo $x, $y;
    ```

## When There's An Overflow Of Integer

If you encounter an overflow of integers, the value will change from ```int``` to ```float```

```php
$x = PHP_INT_MAX + 1;

echo $x;
/**
  * When int goes out of bounds it will get changed into the float data type
  */
var_dump($x);
```

## Casting An Integer

You could cast values using ```(int)``` / ```(integer)``` this would both cast the value into an integer. This is how other data types are cast into ```integer```:

- ```boolean```
     - ```true``` = 1
     - ```false``` = 0
- ```float``` will be rounded down
    - 5.98 = 5
    - 4.70 = 4
-```string```
    - '5.9' = 5
    - '89' = '89'
    - '87noermica' = 87
    - "if it's cannot to be converted to int it will return zero" = 0
- ```null```
    - ```null``` = 0

## Checking Is Integer

You can check variable is ```int``` using function called ```is_int()```.

```php
$x = (int) null; # the output is true
$y = null; # the output is false

echo $x, $y;
var_dump(is_int($x, $y));
```

## Readability Purpose

Also as of **PHP**-7.4 for readability purposes you could use underscore within your ```int```:

- ```$x = 2_000_000_000;``` It's just add readability to the number without using comma or anything
- ```$x = '2_000_000_000';``` If you turn this into a ```string``` it's will treat as a ```string```
- ```$x = (int) '2_000_000_000';``` If it's casted to ```int``` it will be casted into 2 anything after that will be removed
