# Haskell-Basics
# Haskell Programming Guide

Welcome to the Haskell Programming Guide. This guide will introduce you to the fundamental concepts and practices in Haskell, a powerful functional programming language. Below you will find an organized structure covering various aspects of Haskell programming.

## Table of Contents

1. [Introduction to Haskell](#introduction-to-haskell)
2. [Getting Started](#getting-started)
3. [Basic Computations](#basic-computations)
    - [Data Types](#data-types)
    - [Expressions](#expressions)
    - [Function Applications](#function-applications)
4. [Modules](#modules)
5. [Defining Functions](#defining-functions)
6. [Recursive Functions](#recursive-functions)
7. [Data Structures](#data-structures)
    - [Lists](#lists)
    - [Strings](#strings)
    - [Tuples](#tuples)
8. [Higher-Order Functions](#higher-order-functions)
9. [Creating New Data Types](#creating-new-data-types)
10. [Type Classes](#type-classes)
11. [Input and Output](#input-and-output)
12. [Error Handling](#error-handling)
13. [Advanced Topics](#advanced-topics)
    - [Concurrency](#concurrency)
    - [Parallelism](#parallelism)

## Introduction to Haskell

Haskell is a purely functional programming language named after the logician Haskell Curry. It supports high-level programming with features like type inference, lazy evaluation, and strong static typing.

## Getting Started

### Installation

To get started with Haskell, you need to install the Haskell Platform, which includes the Glasgow Haskell Compiler (GHC) and the GHCi interactive environment.

- [Download Haskell Platform](https://www.haskell.org/downloads)

### Setting Up Your Environment

1. Install the Haskell Platform.
2. Open your terminal or command prompt.
3. Start GHCi by typing `ghci`.

### Hello World

Create a simple "Hello World" program to ensure your setup is correct.

```haskell
main = putStrLn "Hello, World!"
```

Run the program using GHCi:

```sh
ghci HelloWorld.hs
*Main> main
```

## Basic Computations

### Data Types

Haskell supports various basic data types:

- **Integers**: Whole numbers (e.g., `5`, `-3`)
- **Floating-point numbers**: Numbers with decimals (e.g., `3.14`)
- **Characters**: Single characters (e.g., `'a'`, `'Z'`)
- **Booleans**: True or False values (`True`, `False`)

### Expressions

Expressions in Haskell can involve arithmetic operations, comparisons, and logical operations.

```haskell
-- Arithmetic
5 + 3
8 * 2

-- Comparison
5 > 3
3 == 3

-- Logical
True && False
not True
```

### Function Applications

Functions are applied using the prefix notation.

```haskell
sqrt 9
```

## Modules

Modules in Haskell help organize and reuse code. A module can export functions, types, and classes.

### Creating a Module

```haskell
module Geometry (hypotenuse) where

hypotenuse :: Floating a => a -> a -> a
hypotenuse a b = sqrt (a^2 + b^2)
```

Load the module in GHCi:

```sh
ghci Geometry.hs
*Geometry> hypotenuse 3 4
```

## Defining Functions

Functions are the core of Haskell programming. You can define simple and recursive functions.

### Simple Functions

```haskell
add :: Int -> Int -> Int
add x y = x + y
```

### Recursive Functions

```haskell
factorial :: Integer -> Integer
factorial 0 = 1
factorial n = n * factorial (n - 1)
```

## Data Structures

### Lists

Lists are fundamental in Haskell.

```haskell
-- Creating a list
numbers = [1, 2, 3, 4, 5]

-- List operations
head numbers
tail numbers
```

### Strings

Strings are lists of characters.

```haskell
greeting = "Hello, Haskell!"
```

### Tuples

Tuples are used to store fixed numbers of elements.

```haskell
pair = (1, "one")
```

## Higher-Order Functions

Functions that take other functions as arguments or return functions.

```haskell
map (*2) [1, 2, 3, 4]
filter even [1, 2, 3, 4, 5, 6]
```

## Creating New Data Types

Define new data types using the `data` keyword.

```haskell
data Shape = Circle Float | Rectangle Float Float
```

## Type Classes

Type classes define a set of functions that can be used for different types.

```haskell
class Eq a where
  (==) :: a -> a -> Bool
```

## Input and Output

Haskell handles I/O operations in a functional way.

```haskell
main = do
  putStrLn "Enter your name:"
  name <- getLine
  putStrLn ("Hello, " ++ name ++ "!")
```

## Error Handling

Handle errors using the `Either` type or the `Maybe` type.

```haskell
safeDiv :: Int -> Int -> Maybe Int
safeDiv _ 0 = Nothing
safeDiv x y = Just (x `div` y)
```

## Advanced Topics

### Concurrency

Haskell provides support for concurrent programming.

```haskell
import Control.Concurrent

main = do
  forkIO (putStrLn "Hello from thread")
  putStrLn "Hello from main thread"
```

### Parallelism

Leverage Haskell's parallelism capabilities.

```haskell
import Control.Parallel

main = do
  let x = fib 35 `par` fib 36 `pseq` (fib 35 + fib 36)
  print x
```

---

This guide should give you a solid starting point in Haskell programming. For more detailed examples and advanced topics, refer to the provided PDF documents and explore the Haskell community resources.
