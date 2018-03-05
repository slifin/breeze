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

You may be skipping good opportunities for variable names by using if statements, in a typical ```if``` statement 
variable names are just extra work, why bother?! 

It's likely if you're using if statements then you're not giving a name to every condition, if you 
change your if statement usage you can change the habit of not naming your conditions:

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
### What happened to my if statement?

In the previous example we saw ```$thruster_speed = 0;``` happen inside a boolean shortcut, why do that instead of using an if statement? 

Well the problem is that if statement blocks evolve in such a way that encourages deep nesting, in a boolean shortcut at most you can do one operation, if that operation is complex you are forced to call out to a seperate function or rewrite the code.

We want other developers to make small composable functions so we are not going to make it easy to modify our code to add nesting code, they can either follow our function call and think about the semantics of our function or make their own.

Stop nesting in my shit!

### Why should I make a function? 

In the previous section I talked about the idea of calling out to a function from a boolean short circuit here are some advantages to calling out to a function: 

  - Variables are explicitly imported into the operation
  - Parameters can be type hinted, my advise to use scalars and arrays whenever possible (TODO footnote on why)
  - The symbols table is clean
  - Functions have names, and names have meaning which can signal intent.
  - Functions have doc types which have words which can signal intent.
  - Functions have return types which have types which can signal intent.
  

### Free functions not class functions

Functions are mathmatical 

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
