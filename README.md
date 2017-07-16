# 🍃 Breeze
Code less, low cyclomatic complexity, [PHP](http://php.net/) framework.

## Table of Contents
* [About](#about)
* [If Statement](#if)
  * [Setting defaults](#setting-defaults)
  * Set variable based on condition
  * Run a code block based on condition
  * Run a code block based on condition with return
* [Foreach Statement](#foreach)
  * Iterate a data structure
  * Remove elements in a data structure
  * Change elements in a data structure 
  * Collect a new thing from all elements in a data structure

## About

Breeze is a series of alternative constructs for your code to decrease [cyclomatic complexity](https://en.wikipedia.org/wiki/Cyclomatic_complexity). 

#### 🔬 Code Review

Cyclomatic complexity is often used as a software measurement by [PHPMD](https://phpmd.org/), [Scruitinzer](https://scrutinizer-ci.com) and other code review tools.

To decrease cyclomatic complexity avoid nameless conditionals/functions and code blocks, Breeze contains context dependent alternatives.

## If
```php
if () {}
```
The if statement is a short hand [language construct](https://en.wikipedia.org/wiki/Language_construct), it is comprised of:
  * A conditional that can be nameless
  * A code block that is nameless and imports the parent scope
  
### Setting Defaults
😕 - One code block, one condition 
```php
if (isset($myVariable)) {
  $myVariable = 5;
}
```
😇 - Explicit variable names, transform is transparent to a debugger observing symbols table
```php
$issetMyVariable = isset($myVariable);
$defaultMyVariable = 5;
$myVariable = $issetMyVariable ? $myVariable : $defaultMyVariable; 
```

😇 - DOUBLE CHECK ORDER OF OPERATIONS HERE
```php
$myVariable = $myVariable ?? $defaultMyVariable = 5;
```

### Set Variable Based on Condition
## Foreach
```php
foreach () {}
```

TODO look up - https://github.com/phpmetrics/PhpMetrics need to work out cyclomatic complexity for each snippet
