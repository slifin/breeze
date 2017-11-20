# <img alt="Icon of the milky way" width="24" height="24" src="https://rawgit.com/slifin/5bd4633c141f50f9d8c6118c179c9550/raw/83661a03839415ce5527ff2e171b7b7c90b3ee78/signal.svg" /> Signal


Communication array for the [PHP](http://php.net/) language.


## Table of Contents
* [About](#about)
* [Conditionals](#conditionals)
* [Arrays](#arrays)
* [Functions](#functions)
* [Closures](#closures)



## About
Signal is a document to help writers increase context and meaning expressed through code.

## Conditionals

### Keep describing what your code does

Provide context to your ```if``` statements by including variable names whenever possible

You might be skipping good opportunities for variable names by refusing to use a variable name
inside your if statement. By dropping the habit of using if statements you can drop the habit 
of leaving things unnamed.

<details>
 <summary>Click here for details</summary>
<p>
 
```php
if ($object['km/s'] > 552) {
  myOperation();
}
```
```diff
- if ($object['km/s'] > 552) {
-   myOperation();
- }

+ $is_faster_than_milkyway = $object['km/s'] > 552;
+ $is_faster_than_milkyway && myOperation();
```
```php
$is_faster_than_milkyway = $object['km/s'] > 552;
$is_faster_than_milkyway && myOperation();
 ```
</p>
</details>

### Type hinting at every level

```if``` statements are a shorthand to evaluate a conditional and run a block of code, said block of code must be unnamed, 
local (unreusable), unopinionated about what it imports from the outer scope and type unsafe.

When we construct our programs in this way we encourage nesting within our scope, particularly when your code is being modified at a later date, it's tempting to modify the code at the nesting point rather than creating a new named operation.

What could we do differently to nesting via the if statement?

<details>
 <summary>Click here to see code</summary>
<p>
 
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
</p>
</details>


### Prevent maintainers from nesting in your code



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

Notes:



*A quick and fast rule for this is do not use a PHP operator inside an if statement condition.*

TODO provide PHPCS lint for this: https://pear.php.net/manual/en/package.php.php-codesniffer.coding-standard-tutorial.php

<details>
 <summary>Summary</summary>
<p>
'''js
const x = 1
''' (change to `)
</p>
</details>


Focus on writing code that describes *why* it is performing its operations by using function names
that describe the purpose of the code


<figure>
    <p><code>Life is good, said HTML5 to XHTML.</code></p>
    <figcaption>In this code block, we see HTML5 speaking to XHTML.</figcaption>
</figure>
