# 🍃 Breeze
Code less [PHP](http://php.net/) framework.

## Table of Contents
* [About](#about)
* [Creating a story in code](#name_things)
* [How to use array_*](#how_to_use_array_*)
  * [Filtering](#array_filter)
  * [Changing array elements](#array_map)
  * [Creating a new thing from an array](#array_reduce)
  * [Iterating with side effects](#array_walk)

## About

Breeze is a framework aimed at PHP developers to encourage a style of code that helps signal intent of code.


## Name things

Create a habit of when creating something avoid operating on the result immediately:

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
## array_filter

## array_map

## array_reduce

## array_walk

