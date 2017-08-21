# 🌱 Seed 
Habit based [PHP](http://php.net/) framework.

## Table of Contents
* [About](#about)
* [Tell a story in code](#name_things)
* [Array functions](#array_functions)
  * [Why use array functions for looping](#Why_use_array_functions_for_looping)
  * [Filtering](#array_filter)
  * [Changing array elements](#array_map)
  * [Creating a new thing from an array](#array_reduce)
  * [Iterating with side effects](#array_walk)
  * [Function reuse](#function_reuse)

## About

Seed is a habit based framework that encourages the communication of code intent.

## Name Things

Create a habit of naming things even when the language allows you to be silent:

For example instead of this:

```php
if ($person['age'] > 18) {
}
```

Prefer this:

```diff
+ $uk_drinking_age = $person['age'] > 18;
+ if ($uk_drinking_age) {
- if ($person['age'] > 18) {
```
```php
$uk_drinking_age = $person['age'] > 18;
if ($uk_drinking_age) {
}
 ```
 
The name provides additional context to your code.

*A quick and fast rule for this is do not use a PHP operator inside an if statement condition.*

TODO provide PHPCS lint for this: https://pear.php.net/manual/en/package.php.php-codesniffer.coding-standard-tutorial.php
## Loop with functions
Loops are anonymous functions on 
### Filtering
[array_filter](http://php.net/manual/en/function.array-filter.php)`();`

```php
$array = array_filter($array, function () {
  return 
});
```

### Changing array elements
[array_map](http://php.net/manual/en/function.array-map.php)`();`
```php
$array = array_map(function () {
  return 
}, $array);
```
### Creating a new thing from a loop
[array_reduce](http://php.net/manual/en/function.array-reduce.php)`();`
```php
$array = array_reduce($array, function () {
  return 
}, $intial);
```
### Perform side effect from a loop
[array_walk](http://php.net/manual/en/function.array-walk.php)`();`
```php
array_walk($array, function () {
  return 
});
```
### Sort an array
[usort](http://php.net/manual/en/function.usort.php)`();`
```php
usort($array, function () {
  return 
});
```
