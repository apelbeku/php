
# Typecasting Overview & How It Works

**PHP** is dynamiclly typed or also known as weekly typed language where you are not required to define the type of your variable, and also the type of the variable can change after it has been defined. Dynamiclly typed language are means that the type checking happens at run time while staticlly typed language means that type checking happens at compile time, e.g, java, c, c++, c# are statically type langauge.

## Dynamic Types vs Static Types

Because **PHP** allows such type system it's more flexible, but that flexibility comes at a price of performance and can sometimes result in unexpected bugs. However **PHP** has improved it's type system a lot in latest version and it even support strict types.

**PHP** support 10 primitive types:

- Scalary Types
    - Bool
    - Int
    - Float
    - String
        ```php
        /**
         * 4 Scalar Types is boolean, integer, float, string
         * Boolean is just representation of a truth value, it can either be: true or false
         * Integer is just numeric values without the decimal: 1, 2, 4, 0, -5
         * Float or floating point also knwon as doubles or decimal: 0.1, 1.4, -4.6
         * String is just series of characters that are enclosed with either single or double quote
         */
        $completed = true; # Bool
        $score = 80; # Int is whole number without decimal
        $price = 0.99; # Float is decimal number
        $greeting = "Hello World"; # String is series of characters: 'Hello World';

        echo $completed . <br />;
        echo $score . <br />;
        echo $price . <br />;
        echo $greeting . <br />;

        /**
         * There are a couple ways to to find out the type of variable
         * using gettype()
         * using var_dump()
         */
        echo gettype($completed);
        echo var_dump($greting);
        ```
- Compound Types
    - Array
    - Object
    - Callable
    - Iterable
        ```php
        /**
         * Array is list of items and these can be of many different types
         * another way to print array is using print_r()
         * We'll discuss about Object, Callback, Iterable later
         */
        $companies = [1, 2, 4, 0.9, '4', '10', true];

        echo $companies;
        print_r($companies);
        ```
- Special Types
    - Resource
    - Null
        ```php
        /**
         * We'll discuss about Resource later
         * Null it just simply means no value
         */
        ```

## Automatic Type Detection

How does actually **PHP** know that this is variable, e.g:

```php
$score = 80;

echo $score;
var_dump($score); # we'll get int 80

/**
 * PHP will automatically determine the data type during runtime and in this case PHP will basically figure it figure out that you're trying to define this variable as an integer because it has no quotes around it.
 */
```

##  Type Hinting Example

[Read more here](https://www.phptutorial.net/php-tutorial/php-type-hints/ "PHP type hinting")

##  Type Juggling & Type Coersion

[Read more here](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbEw1OUs3cjRCRGVFNEpGSUxXRHEwblptZlNwd3xBQ3Jtc0ttRE5NZmJoQkw1Q1VpdS1wN2dGRzhKLUtQUEJhSHRLUjBGSmIxT1NRRVlpYWFMSmxkcWZjZk1PTXF5VVhVMWphaW5WSHBHODZBaFg4ci1PMklDQ0RLWWxlbm1LcTA5UXBPMUlEOXJCTXo2LWt2Vk1ySQ&q=https%3A%2F%2Fwww.php.net%2Fmanual%2Fen%2Flanguage.types.type-juggling.php&v=KH4MmQsCDuw "PHP type juggling")

## Strict Mode

Strict mode is you will throw an error if you pass another type even if you pass something that can be converted dynamically.

```php
/**
 * Personally it's recommended to use type hinting
 * and strict type as much i as i can it provides
 * better quality of code where i know exactly
 * what types are accepted and it will avoid
 * unexpected bugs
 */

// This is how you enable strict type
declare(strict_type=1);

function sum(int $x, int $y) {
    return $x + $y;
}

$sum = sum('2', 4);
echo $sum;

var_dump($sum);
```

## Type Casting

```php
$x = '4';

var_dump($x);

/**
 * You could actually force this to be an int type and you could cast anything to the data types using the name of the data type within ()
 */
$x = (int) '4';

var_dump($x);
```
