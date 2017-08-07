# 🍃 Breeze
Code less [PHP](http://php.net/) framework.

## Table of Contents
* [About](#about)
* [Creating a story in code](#name_things)
* [Filtering](#array_filter)
* [Changing array elements](#array_map)
* [Creating a new thing from an array](#array_reduce)
* [Iterating with side effects](#array_walk)

## About

Breeze is a framework aimed at PHP developers to encourage a style of code that helps signal intent.


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
## array_filter

## array_map

## array_reduce

## array_walk

