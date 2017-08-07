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

Breeze is a framework aimed at PHP developers to encourage a style of code that creates good habits around 
naming things and actions within code.


## Name things

We subltly avoid naming things by doing certain things in code
Avoid creating something and operating on it immediately.

For example instead of this:

    if ($person['age'] > 18) {
    }

Prefer this:

    $uk_drinking_age = $person['age'] > 18;
    if ($uk_drinking_age) {
    }
## array_filter

## array_map

## array_reduce

## array_walk

