# 🍃 Breeze
Code less, low cyclomatic complexity, PHP framework.

## Table of Contents
* [Concept](#Concept)
* [If Statement](#if)
  * Setting defaults
  * Variable set to one or the other based on condition
  * Run a code block based on condition
  * Run a code block based on condition with return
* [Foreach Statement](#foreach)
  * Iterate a data structure
  * Remove elements in a data structure
  * Change elements in a data structure 
  * Collect a new thing from all elements in a data structure

## Concept

Breeze is a series of alternative constructs for your code to decrease [cyclomatic complexity](https://en.wikipedia.org/wiki/Cyclomatic_complexity). 

To decrease cyclomatic complexity avoid nameless conditionals/functions and code blocks,
Since these are the foundations of modern code, this document contains context dependent alternatives.

## If
```php
if () {}
```
The if statement is a short hand [language construct](https://en.wikipedia.org/wiki/Language_construct), it is comprised of:
  * A conditional that can be nameless
  * A code block that is nameless and imports all parent scope
  
### Setting Defaults

## Foreach
```php
foreach () {}
```
