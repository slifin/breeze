# <img alt="Icon of the milky way" width="24" height="24" src="https://rawgit.com/slifin/5bd4633c141f50f9d8c6118c179c9550/raw/83661a03839415ce5527ff2e171b7b7c90b3ee78/signal.svg" /> Signal


<strong>Communication array for the [PHP](http://php.net/) language.</strong>


## Table of Contents
* [About](#about)
* [Conditionals](#conditionals)
* [Arrays](#arrays)
* [Functions](#functions)
* [Closures](#closures)



## About
Signal is a document to help writers increase context and meaning expressed through code.

## Conditionals

### Keep adding context to what your code does

You may be skipping good opportunities for variable names by using if statements, in a typical if statement 
variable names appear redundant, drop the if statement and variable names appear natural again.

 <p align="right">❌☹️</p>
 
```diff
- if ($thurst['mph'] > 25020) {
-   $thruster_speed = 0;
- } 
```

 <p align="right">✔🙂</p>

```php
$escape_velocity = $thurst['mph'] > 25020;
$escape_velocity && $thruster_speed = 0;
 ```


### Type hinting at every level

if statements are a shorthand to evaluate a conditional and run a block of code, said block of code must be unnamed, 
local (unreusable), unopinionated about what it imports from the outer scope and type unsafe.



What could we do differently to nesting via the if statement?


 
```php
if ($object['km/s'] > 552) {
 --$engine_speed;
}
```
```diff
- if ($object['km/s'] > 552) {
-  --$engine_speed;
- }
+ $is_faster_than_milkyway = $object['km/s'] > 552;
+ $is_faster_than_milkyway && $engine_speed = (function(int $engine_speed) {
+   return --$engine_speed;
+ })($engine_speed);
```
```php
$is_faster_than_milkyway = $object['km/s'] > 552;
$is_faster_than_milkyway && $engine_speed = (function(int $engine_speed) {
  return --$engine_speed;
})($engine_speed);
 ```


### Preventing future nesting in your code

When we construct our programs in this way we encourage nesting within our scope, particularly when your code is being modified at a later date, it's tempting to modify the code at the nesting point rather than creating a new named operation.


### Use the positive side of the equation


First your brain has to parse the result of ```empty($meteors_on_collision_course)``` and then flip it with ```!```. Remove the two steps and talk about the event directly without additional comprehension steps.

<details>
 <summary>Click here for examples</summary>
<p>

```php 
if (!empty($meteors_on_collision_course)) {
    launch_missiles()
}
```
```diff 
- if (!empty($meteors_on_collision_course)) {
-    launch_missiles()
-}
+count($meteors_on_collision_course) && launch_missiles();
```
```php 
count($meteors_on_collision_course) && launch_missiles();
```
</p>
</details>

## Arrays

### Filtering array children
[array_filter](http://php.net/manual/en/function.array-filter.php)`();`

```php
$earth_diameter = 7917.5;
$smaller_than_earth_planets = array_filter($planets, function (array $planet) use ($earth_diameter) {
  return $planet['size'] < $earth_diameter;
});
```

```php
$earth_diameter = 7917.5;
$smaller_than_earth_planets = [];
foreach($planets as $planet) {
  if ($planet['size'] < $earth_diameter) {
    $smaller_than_earth_planets[] = $planet;
  }
}
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

## Functions

## Closures

## Disclaimer
