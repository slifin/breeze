# 🌱 Seed 
Code less [PHP](http://php.net/) framework.

## Table of Contents
* [About](#about)
* [Grow a story in code](#name_things)
* [How to use array_*](#how_to_use_array_*)
  * [Why use functions?](#why_use_functions_to_loop)
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
 
This provides additional context to your code that might not be apparant to other readers or when you forget.


## Why use functions to loop?

## array_filter

## array_map

## array_reduce

## array_walk

