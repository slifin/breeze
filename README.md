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

## Name things

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

# array functions

## Why use array functions for looping

## array_filter

## array_map

## array_reduce

## array_walk

