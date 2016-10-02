# php-lambda
[![Build Status](https://travis-ci.org/nerd-components/lambda.svg?branch=master)](https://travis-ci.org/nerd-components/lambda)
[![Coverage Status](https://coveralls.io/repos/github/nerd-components/lambda/badge.svg?branch=master)](https://coveralls.io/github/nerd-components/lambda?branch=master)
[![StyleCI](https://styleci.io/repos/60102687/shield?branch=master)](https://styleci.io/repos/60102687)

Generates lambda function using given string pattern.

## Example
```php
use function Lambda\l;

// Unindexed placeholders mode
$sum = l('$ + $');

echo $sum(2, 4); // will output 6


// Indexed placeholders mode
$func = l('$0 + ($0 * $1)');

echo $func(2, 6); // will output 14


// Filtering function
$numbers = range(1, 10);

$evens = array_filter(l('$ % 2 == 0'), $numbers); // will produce array [2, 4, 6, 8, 10]
```
