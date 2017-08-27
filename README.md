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

Signal is a communication based framework that encourages the communication of code intent through documentation.

## Send the Message

Create a habit of naming things that previously you may have left unnamed:

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

## Use the positive side of the equation

```php 
if (!empty($meteors_on_collision_course)) {
    launch_missiles()
}
```
```diff 
- if (!empty($meteors_on_collision_course)) {
-    launch_missiles()
-}
+$no_meteors_on_collision_course = empty($meteors_on_collision_course);
+$no_meteors_on_collision_course ?: launch_missiles();
```
```php 
$no_meteors_on_collision_course = empty($meteors_on_collision_course);
$no_meteors_on_collision_course ?: launch_missiles();
```

When the ```!``` operator is used your brain first has to parse the result of ```$meteors_on_collision_course``` and then flip it with ```!```. Remove the two steps and talk about the event directly with variable names.


## Loop with functions
Loops are anonymous functions on 
### Filtering array children
[array_filter](http://php.net/manual/en/function.array-filter.php)`();`

```php
$array = array_filter($array, function () {
  return 
});
```

### Changing array children
[array_map](http://php.net/manual/en/function.array-map.php)`();`
```php
$array = array_map(function () {
  return 
}, $array);
```
### Create a new thing from array children
[array_reduce](http://php.net/manual/en/function.array-reduce.php)`();`
```php
$array = array_reduce($array, function () {
  return 
}, $intial);
```
### Perform side effect for each array child
[array_walk](http://php.net/manual/en/function.array-walk.php)`();`
```php
array_walk($array, function () {
  return 
});
```
### Sort array children
[usort](http://php.net/manual/en/function.usort.php)`();`
```php
usort($array, function () {
  return 
});
```

Notes:



*A quick and fast rule for this is do not use a PHP operator inside an if statement condition.*

TODO provide PHPCS lint for this: https://pear.php.net/manual/en/package.php.php-codesniffer.coding-standard-tutorial.php
