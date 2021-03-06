# <img alt="Icon of the milky way" width="24" height="24" src="https://rawgit.com/slifin/5bd4633c141f50f9d8c6118c179c9550/raw/83661a03839415ce5527ff2e171b7b7c90b3ee78/signal.svg" /> Signal


<strong>Communication array for the [PHP](http://php.net/) language.</strong>


## About
Signal is a document to help writers increase context and meaning expressed through writing code.
If you've ever read some PHP code and could not work out the original **intent** of the code, then this document is for you.

## Conditionals

### Every opportunity to name and describe:

You may be skipping good opportunities for variable names by using if statements, in a typical ```if``` statement 
variable names are just extra work, why bother?! 

It's likely if you're using if statements then you're not giving a name to many conditions, if you 
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
### Nesting, it's not a matter of if, it's a matter of when

In the previous example we saw ```$thruster_speed = 0;``` happen inside a boolean shortcut, why do that instead of using an if statement? 

Well the problem is that if statement blocks evolve in such a way that encourages deep nesting, in a boolean shortcut at most you can do one operation, if that operation is complex you are forced to call out to a seperate function or rewrite the code.

We want other developers to make small composable testable functions, so we are not going to make it easy to modify our code to add nesting code, they can either follow our function call and think about the semantics of our function or make their own.

Only **you** can prevent rats nesting in code:

<p align="right">❌☹️</p>

```diff
- foreach ($data as $k => $item) {
-  foreach ($item as $current) {
-    if (isset($current['object'])) {
-      if ($current['object']) {
-        // 200 lines later we're still in here, send help.
-      }
-    }
-  }
-}
```

This code was only possible because of blocks, if statements, foreach statements and other language constructs nested block sin this manner

### Variable names
Variable names are the meat of your story the intent of your code, and yet how many times have you seen code like this?

```php
foreach ($data as $item) {
}
```
It's possible to write bad variable names in any situation but if you were forced to write this out as a function, you'd have to write some documentation on what $data|$item is, and as you do so it might occur to you that $data|$item isn't adding a whole lot of value to the story of your code.

### Why should I make a function? 

Here are some advantages to calling out to a function over writing your code deeper into a block never to be used again:

  - Variables are explicitly imported into the operation
  - Parameters can be type hinted
  - The symbols table is clean
  - Functions have names, and names have meaning which can signal intent.
  - Functions have doc types which have words which can signal intent.
  - Functions have return types which have types which can signal intent.
  - Thing goes in, thing goes out, you can't explain that! (except when you can) 
  - Testable, it's impossible to test the contents of an if statement block if it's nested, but more than possible with functions
  

### Free functions not class functions

Methods are dirty shit compared to functions, methods are not free functions, they are bound to objects that you might not necessarily want to instantiate, they can be intercepted with what we actually call magic. They often encourage code that is not input/output testing small parts of the system becomes harder and moving code horitzontially in the object tree involes language assisted copy and paste.

## Arrays

If you want to stop using foreach loops for everything, here is a list of operations done functionally, you'll generally speaking have much more composable code if you do one thing at a time in each loop, it is possible to do many things by composing functions but that's not something I'd encourage at this early stage.

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

## Breaking third party object jails

## Disclaimer
