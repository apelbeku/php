
# Float Data Type

Floating point numbers are (also known as ```float```, ```doubles```, ```real numbers```)

```php
$x = 13.5;

echo $x;
```

You could also writing ```float``` in exponential form, e.g:

- positive
    ```php
    $x = 13.5e3; # the output is 13500

    echo $x;
    ```
- negative
    ```php
    # you could do a negative numbers too
    $y = 13.5e-3; # the output is 0.0135

    echo $y;
    ```
Even when we do with the positive and doesn't contain decimal it's still float

```php
$x = 13.5e3;

var_dump($x);
echo $x;
```

## Readability Purpose

Since **PHP**-7.4 you could actually have underscore within your numbers for better readability.

```php
$x = 13_000.5e3; # It will works
$y = 13_000.5; # It will works too

var_dump($x, $y);
echo $x, $y;
```


## Floating Number Size

Just like integer the size of floating numbers is depend on the platform, we can check it using predefined ```const```:

- ```PHP_FLOAT_MIN```
- ```PHP_FLOAT_MAX```

Be aware of their limited precisions, e.g:

```php
$x = floor((0.1 + 0.7) * 10);

echo $x;
```

You will think it will return ```8```, but it's will get ```7``` because ```0.1``` and ```0.7``` don't have an exact representation as the ```floating point number``` is in ```base 2 (binary)``` and ```binary``` is used internally to store the ```floating numbers```. in this case ```0.1``` and ```0.7``` times ```10``` actually equal to ```7.9999999999999991118``` and ```floor()``` basically just rounds all the numbers down

### ```floor()``` is round down when ```ceil()``` is round up:

```php
$x = ceil((0.1 + 0.7) * 10);

echo $x;
```

Also ```ceil()``` can result unexpected value

```php
/**
  * The 0.1 + 0.2 will result 3.000000000000000004
  * that's way you will get 4 becuase 3 round up to 4
  * NEVER TRUST FLOATING NUMBERS TO THE LAST DIGIT
  */
$x = ceil((0.1 + 0.2) * 10); # The output is 4

echo $x;
```

## Never Ever Compare Floating Numbers For Equality

[Hightly Recommend Read More](https://floating-point-gui.de/ "Floating Number & How To Compare It")

```php
$x = 0.23;
$y = 1 - 0.77;

var_dump($x, $y);

if ($x == $y) {
    echo "YES";
} else {
    echo "NO";
}

// The result will NO
```

## Some Operations Or Calculations Might Result in ```NAN``` Or ```INF```

- ```NAN```
    ```php
    /**
      * NAN or Not A Number
      */
    echo log(-1); // The result will be NAN, it's because the oeparationc cannot be compute
    ```
- ```INF```
    ```php
    /**
      * INF or Infinite
      * You will happend if you out of the bound of the maximum floating value that can be stored on the platform
      */
    echo PHP_FLOAT_MAX + 2;; // The result will be INF
    ```

## ```is_nan()``` And ```is_infinite()```

- chekcking is ```infinite```
    - ```is_infinite()```
    - ```is_finite()``` will tell you if the numbers is not ```infinite```
- chekcking is ```nan```
    - ```is_nan()```

## Float Casting

```php
$x = 5;

var_dump((float) ($x)); # other way you can use function called floatvar()
var_dump(floatvar ($x)); #  i personally prefer (float)
```
