# Constants and Variables

**Constants** are the values that cannot change once they are defined, unlike **Variable** where you could define and override the raw varaibles after they're defined.

```php
// variable
/**
 * The return is beku becuase last variable
 * override the value.
 */
$firstname = 'apel';

$firstname = 'beku';

echo $firstname;
```

## Various Way To Define Const

- using `define()`

  ```php
  /**
   * The name of the constant follows the same rules as the variable
   * Convention way to define name with all UPPERCASE
   */
  define('name', 'value');

  define('STATUS_PAID', 'paid');

  // When referenced a cons you don't need $
  echo STATUS_PAID;

  /**
   * You cannot change value of the const
   * This will give you and error.
   * define('STATUS_PAID', 'void');
   */

  /**
   * Check if the const is defined
   * The response is boolean.
   * echo defined('STATUS_PAID');
   */
  ```

- using `const`
  ```php
  /**
   * Different between const and define is
   * Const actually defined at compile time
   * While define() are defined at runtime
   * It's mean you can't use const in control structure like loop, if else
   * But you can use define in it.
   * if(true) {
   *  define('STATUS_PAID', 'paid');
   * }
   */
  const STATUS_PAID = 'paid';

  echo STATUS_PAID;
  ```

## When To Use `const`

Whenever you have static data that doesnt' change too often, e.g:

- STATUS_PAID
- STATUS_VOID
- STATUS_PEDDING
- STATUS_DECLINED

## Predefined `const`

**PHP** also have predefined and magic `const`:

- Predifined `const`

  - [Read more about predifined const](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbTdmVk95aXN4dmctZmJtazFGR0E0TUQyV1lUZ3xBQ3Jtc0treEpuMEZUYVNvSVgtMEFUb19NZDlucXlKS0J4TGhVeDFwa2YzME82OUxNdlBqcWVVRUstcXlCRUZkZkZfd01EY3plWVluMEo3T1R3VV9VLTd4SGFRZWlKX1hOSDQ3VzhBcGczVkRSem5vMS10SC0wSQ&q=https%3A%2F%2Fwww.php.net%2Fmanual%2Fen%2Freserved.constants.php&v=6JtP8xk1U_k)

  ```php
  echo PHP_VERSION;
  echo PHP_BINDIR;
  echo PHP_BINARY;
  echo PHP_CONFIG_FILE_PATH;
  ```

- Magic `const`

  - [Read more about magic const](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbVpmd0V1dzhJRkt6cVJHVVpobWwzSVdzRGh3Z3xBQ3Jtc0ttcDdBdHBlYzA5OWthMlZ3MUVfOGFNRVNCdjF6c3k0NzlaV0FYb2xUM2NYV3FpYTk3TGZKN2FoV2FOMUw2YUxNOVRzbG5oTFl0M2pUbEVWVnpTcFhJWXBxVFlyUXFXQVVMSlRRSFA3R05pRnVDWlA0RQ&q=https%3A%2F%2Fwww.php.net%2Fmanual%2Fen%2Flanguage.constants.magic.php&v=6JtP8xk1U_k)

  ```php
  echo __LINE__;
  echo __FILE__;
  echo __FUNCTION__;
  echo __METHOD__;
  ```

## Variable Variable

`Variable variable` basically takes the value of the variable and treats that as the name of the new variable.

```php
$foo = 'bar';
$$foo = 'baz';

// It's will work
echo $foo, $bar;

/**
 * The other proper way to do it
 */
echo $foo, $$foo;
echo "$foo, ${$foo}";
echo "$foo, {$$foo}";
```
