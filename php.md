### PHP TUTORIAL, TIPS & TRICKS

## SOURCE
- youtube creator Gio --> program with Gio
-- https://www.youtube.com/playlist?list=PLr3d3QYzkw2xabQRUpcZ_IBk9W50M9pe-

- php doc's operator precendence
-- http://php.net/manual/en/language.operators.precedence.php

- php doc's arrays
-- http://php.net/manual/en/ref.arry.php

- php file handling
-- https://www.youtube.com/watch?v=p7F2GgVxHc0&list=PLr3d3QYzkw2xabQRUpcZ_IBk9W50M9pe-&index=31


 ## OPERATORS 
 - Arithmetic Operators (+ - * / % **)
 - Assignment Operators (= += -= *= /= %= **=)
 - String Operators (. .=)
 - Comparison Operators (== === != !== <> < > <= >= <=> ?? ?:)
 - Error Control Operator ( @ )  Error suppression
 - Increment/Decrement Operators (++ -- )
 - Local Operators ( && || ! and or xor )
 - Bitwise Operators ( & | ^ ~ << >> )
 - Array Operators ( + == === != <> !== )
 - Execution Operators ( `` )
 - Type Operators ( instanceof ) 
 - NullSafe Operator - php 8 ( ? )


## FUNCTIONS

    ```php
    function sum (...$numbers) {
      $sum = 0
      foreach($numbers as $number){
        $sum + $number;
      }
    }

    sum(5, 10);
    sum(6, 7, 8, 9, 10)
    ```
  Because `...$numbers` is an array both invokes (call) of the function sum wil work.

 `declare(strict_types=1);`  is used to make your current file use strick parameters
  witch means you need to use type casting variables and parameters.
  `(int) $var` `function foo(int $x, int|float $y) : int|float { return $x * $y } `




 ## TIPS & TRICKS 
 - destroy a variable unset($var);


