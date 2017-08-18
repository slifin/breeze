# 🌱 Seed 
Code less [PHP](http://php.net/) framework.

## Table of Contents
* [About](#about)
* [Grow a story in code](#name_things)
* [Array functions](#array_functions)
  * [Why use array functions for looping](#Why_use_array_functions_for_looping)
  * [Filtering](#array_filter)
  * [Changing array elements](#array_map)
  * [Creating a new thing from an array](#array_reduce)
  * [Iterating with side effects](#array_walk)
  * [Function reuse](#function_reuse)

## About

Seed is a framework aimed at PHP developers to encourage a style of code that helps signal intent of code.

## Name Things

Create a habit of naming things by not operating on anything without a name:

For example instead of this:

```php
if ($person['age'] > 18) {
}
```

Prefer this:

```php
$uk_drinking_age = $person['age'] > 18;
if ($uk_drinking_age) {
}
 ```
 
This provides additional context to your code to others when your code grows.

*A quick and fast rule for this is do not use a PHP operator inside an if statement condition.*

## Loop with functions

### Filtering
```php
array_filter();
```

### Changing array elements
```php
array_map();
```
### Creating a new thing from a loop
```php
array_reduce();
```
### Perform side effect from a loop
```php
array_walk();
```
### Sort an array
```php
usort();
```
