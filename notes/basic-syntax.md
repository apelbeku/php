
# Basics PHP syntax

Default **APACHE** web directory is located in ```/var/www/html```, and if you want your file to be interpreted as **PHP** then your file with ```.php```. The **PHP** files can also have **HTML** and **Css** and even **JavaScript** in them, so it would work pretty much the same way.

## Basics syntax

The way **PHP** is parsed is that it looks for the opening and closing tags and interprets everything in between as **PHP**

```php
<?php Anything between this code block will be interpreted as PHP ?>
```

If your file entirely contains **PHP** you do not need the closing tag and in fact we should not have the closing tag, and that's to make sure no accidental white space or new lines are added after the **PHP** closing tag which could mess up your website.

```php
<?php
```

## Hello World!

This is how you ```print``` **Hello World**.

```php
<?php echo 'Hello World!'; ?>
```

## Run PHP in terminal

Type in terminal.

```shell
php <name-of-the-file.php>
```

## Print vs Echo

Another way to ```print``` something:

- ```php
    <?php print 'Hello World!' 
    ```
    - ```print``` has return value of 1
    - you can ```echo print```
        ```php
        <?php echo print 'Hello World!'
        ```
        and you will get Hello World!1
    - this means that ```print``` could be used within expressions while ```echo``` can't.
    - another way to ```print```
        ```php
        <?php print('Hello World1')
        ```
- ```php
    <?php echo 'Hello World!'
    ```
    - you can't ```print echo```, you will get parser error
    - another way to ```echo```
        ```php
            <?= 'Hello', ' ', 'World!'
        ```
    - if you use this you can't concatenate
        ```php
            <?php echo('Hello World')
        ```
    - also ```echo``` is marginaly faster than ```print```, so i would just suggest to use ```echo``` unless you have a specific reason to use ```print```

## Escaping Quotes

- we can use double quote
    ```php
    <?= "Joe's Invoice"
    ```
- we can use backslash
    ```php
    <?= 'Joe\'s Invoice'
    ```
- recommended using double quote

## Variables

Various rules when creating variable in **PHP**:

- must start with a letter or an underscore
    ```php
    $name / $_name
    ```
- the letter can be uppercase or lowercase
    ```php
    $NAME / $name
    ```
- do not start with number or a special character
    ```php
    $1name / $@name
    ```
- don't use
    ```php
    $this
    ```
    becuase it's refer to Object, and we'll talk about it later

By default in **PHP** variables are assigned by value.

```php
$x = 1;
$y = $x;

$x = 4;
echo $y;

"you will get 1 because it's assigned by value, if you want y change whenever x changes you should write like this"

$x = 1;
$y = &$x;

$x = 4;
echo $y;
```

### Variable within text

```php
$firstname  = 'apel';

echo 'Hello $firstname';
```
If you want to get value from the variable you need to change from single quote to double quote

```php
$firstname  = 'apel';

echo "Hello $firstname";

"Some developer will write like this"

echo "Hello {$firstname}"
"or"
echo "Hello" . $firstname;
```

## PHP in HTML

How to embed **PHP** in **HTML**
```html
<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
</head>
<body>

<h1><?= 'Hello World'?></h1>
<p>If you just need to ```print``` something you should use this shorthand version</p>
<p>If you need to process some php then you need</p>
<h1>
    <?php
        $x = 10;
        $y = 9;

        echo $x . ', ' . $y;

        "or we can print content within a paragraph for example"

        echo <p> $x . ', ' . $y; </p>
        
        "this is good for dynamically html generate but in general i would say that's not good idea to mix HTML directly in you PHP"
    ?>
</h1>
</body>
</html> 
```

## Comments

Various way to comment in **PHP**:
- single line comment
    ```php
    // This is single line comment.
    # Or another way of single line comment.
    ```
- multiline comment
    ```php
    /*
        This is multiline comment.
    */
    ```
- doc log comment
    ```php
    /**
     * This is Doc log comment.
     * for write documentation
     * about your source code.
     * /
    ```