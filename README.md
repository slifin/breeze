# 🌌 Signal


Communication based [PHP](http://php.net/) framework.

## Table of Contents
* [About](#about)
* [Writing code intent](#send_the_message)
* [Filtering](#array_filter)
* [Changing array elements](#array_map)
* [Creating a new thing from an array](#array_reduce)
* [Iterating with side effects](#array_walk)


## About

Signal is a communication based framework that encourages the communication of code intent.

## Send the Message

Create a habit of naming things even when the language allows you to be silent:

```php
if ($object['km/s'] > 552) {
}
```
```diff
- if ($object['km/s'] > 552) {
+ $is_faster_than_milkyway = $object['km/s'] > 552;
+ if ($is_faster_than_milkyway) {
```
```php
$is_faster_than_milkyway = $object['km/s'] > 552;
if ($is_faster_than_milkyway) {
}
 ```
 
This allows you to show what your code is _supposed_ to be doing, don't force other programmers to guess 
what your code should be doing based on implementation details: [more examples](http://google.com).




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

Notes:



*A quick and fast rule for this is do not use a PHP operator inside an if statement condition.*

TODO provide PHPCS lint for this: https://pear.php.net/manual/en/package.php.php-codesniffer.coding-standard-tutorial.php
