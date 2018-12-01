---
layout:     post
title:      programming languages Coursera Note Week2
subtitle:    "\"programming languages\""
date:       2018-12-01
author:     demerzel
header-img: img/post-bg-2015.jpg
catalog: true
tags:
    - Coursera
    - programming languages
    - SML
---


# programming languages Coursera Note Week2
#coursera/programming-languages#

## variables binding
First program:
ML comment :  (* this is a comment *)
val x = 34; 

emacs: 
new file: c-x c-f
save: c-x c-s
open ML REPL : c-c c-s

use “first.sml”;

```
(* this is a comment  *)
val x = 34; (* int *)
(* static environment: x: int *)

(* dynamic environment : x --> 34 *)

val y = 17;
(* static environment: x: int y : int  *)
(* dynamic enivornment : x --> 34, y --> 17 *)

val z = (x+y) + (y+2);
(* static environment : x : int ,y : int, z : int *)
(* dynamic environment : x --> 34, y --> 17, z --> 70 *)

val q = z+1;
(* static environment : x : int, y : int, z : int , q : int *)
(* dynamic environment : x --> 34, y --> 17, z --> 70, w --> 71 *)

val abs_of_z = if z < 0 then 0 - z else z; (* bool *) (* int *)
(* abs_of_z : int *)
(* dynamic environment : ..., abs_of_z --> 70 *)

val abs_of_z_simpler = abs z;


```

the result:
```
Standard ML of New Jersey v110.84 [built: Tue Sep 04 08:31:43 2018]
- use "first.sml";
[opening first.sml]
val x = 34 : int
val y = 17 : int
val it = () : unit
-
- x;
val it = 34 : int
- 
```

in ML, we can just use the early var binding.


## expressions rules
```
- true;
val it = true : bool
- 42;
val it = 42 : int
- 3<0;
val it = false : bool
```

For expressions, think about three things:
* syntax
* valid types
* evaluation

all values are expressions
not all expressions are values

**Conditional expression:**
syntax:
if e1 then e2 else e3
where if , then , and else are keywords and
e1, e2 ,and e3 are subexpressions

Type-checking:
e1 must have type bool
e2 and e3 must have the same type t
the type of the entire expression is also t

Evaluation:
first evaluate e1 to a value call it v1.
if it’s true, evaluate e2 and that result is the whole expression’s result.
else, evaluate e3 and that result is the whole expression’s result.


## The REPL
If want to use the same file, c-d to end the REPL, and c-c c-s restart.

in ML  -5 is written as  ~5.

use / for real number, but use div for int.
3 div 5.

## shadowing
Shadowing is when you add a variable to an environment when before you added it, that variable was already in the environment.
```
(* Programming Languages, Dan Grossman *)
(* Section 1: Examples to Demonstrate Shadowing *)

val a = 10

val b = a * 2

val a = 5

val c = b

val d = a

val a = a + 1

(* next line does not type-check, f not in environment *)
(* val g = f - 3  *)

val f = a * 2

 
```

## Functions Informally

```
(* Programming Languages, Dan Grossman *)
(* Section 1: simple functions *)

(* this function correct only for y >= 0 *)
fun pow (x:int, y:int) = 
    if y=0
    then 1
    else x * pow(x,y-1)

fun cube (x:int) =
    pow(x,3)

val sixtyfour = cube(4)

val fortytwo = pow(2,2+2) + pow(4,2) + cube(2) + 2
```

```
val x=(2,3)
val ans = pow x
```
is right.

## Functions Formally

syntax:
```
fun x0 (x1:t1, ... , xn:tn)=e
```

a function is a value.

## Pairs and Other Tuples
` (e1,e2) `
a pair of values is value

`#1 e` the first part of e pair

## tuples
`(e1,e2,…en)`

## Introducing Lists

`e1::e2` e2 is a list, it will add e1 in front of e2

`null e` evaluates to true is e is empty

`hd e` head 
`tl e`list without head

[] can be any type


```
(* Programming Languages, Dan Grossman *)
(* Section 1: List Functions *)

(* Functions taking or producing lists *)

fun sum_list (xs : int list) =
    if null xs
    then 0
    else hd(xs) + sum_list(tl(xs))

fun countdown (x : int) =
    if x=0
    then []
    else x :: countdown(x-1)

fun append (xs : int list, ys : int list) = (* part of the course logo :) *)
    if null xs
    then ys
    else hd(xs) :: append(tl(xs), ys)

(* More functions over lists, here lists of pairs of ints *)

fun sum_pair_list (xs : (int * int) list) =
    if null xs
    then 0
    else #1 (hd(xs)) + #2 (hd(xs)) + sum_pair_list(tl(xs))

fun firsts (xs : (int * int) list) =
    if null xs
    then []
    else (#1 (hd xs))::(firsts(tl xs))

fun seconds (xs : (int * int) list) =
    if null xs
    then []
    else (#2 (hd xs))::(seconds(tl xs))

fun sum_pair_list2 (xs : (int * int) list) =
    (sum_list (firsts xs)) + (sum_list (seconds xs))


```

## List Functions
```
(* Programming Languages, Dan Grossman *)
(* Section 1: List Functions *)

(* Functions taking or producing lists *)

fun sum_list (xs : int list) =
    if null xs
    then 0
    else hd(xs) + sum_list(tl(xs))

fun countdown (x : int) =
    if x=0
    then []
    else x :: countdown(x-1)

fun append (xs : int list, ys : int list) = (* part of the course logo :) *)
    if null xs
    then ys
    else hd(xs) :: append(tl(xs), ys)

(* More functions over lists, here lists of pairs of ints *)

fun sum_pair_list (xs : (int * int) list) =
    if null xs
    then 0
    else #1 (hd(xs)) + #2 (hd(xs)) + sum_pair_list(tl(xs))

fun firsts (xs : (int * int) list) =
    if null xs
    then []
    else (#1 (hd xs))::(firsts(tl xs))

fun seconds (xs : (int * int) list) =
    if null xs
    then []
    else (#2 (hd xs))::(seconds(tl xs))

fun sum_pair_list2 (xs : (int * int) list) =
    (sum_list (firsts xs)) + (sum_list (seconds xs))

```


## Let Expressions
provide local scope

```
(* Programming Languages, Dan Grossman *)
(* Section 1: Let Expressions *)

fun silly1 (z : int) =
    let val x = if z > 0 then z else 34
	val y = x+z+9
    in
	if x > y then x*2 else y*y
    end

fun silly2 () =
    let val x = 1 
    in 
	(let val x = 2 in x+1 end) + (let val y = x+2 in y+1 end)
    end


```

## Nested Functions
```
(* Programming Languages, Dan Grossman *)
(* Section 1: Nested Functions *)

fun countup_from1 (x : int) =
    let fun count (from:int, to:int) =
	    if from=to
	    then to::[] (* note: can also write [to] *)
	    else from :: count(from+1,to)
    in
	count(1,x)
    end

fun countup_from1_better (x : int) =
    let fun count (from:int) =
	    if from=x
	    then x::[]
	    else from :: count(from+1)
    in
	count 1
    end

```

good style to define helper functions inside the functions they help

## Let and Efficiency

save the complete result as dp
```
(* Programming Languages, Dan Grossman *)
(* Section 1: Let Expressions to Avoid Repeated Computation *)

(* badly named: evaluates to 0 on empty list *)
fun bad_max (xs : int list) =
    if null xs
    then 0
    else if null (tl xs)
    then hd xs
    else if hd xs > bad_max(tl xs)
    then hd xs
    else bad_max(tl xs)

(* badly named: evaluates to 0 on empty list *)
fun good_max (xs : int list) =
    if null xs
    then 0
    else if null (tl xs)
    then hd xs
    else
	(* for style, could also use a let-binding for (hd xs) *)
	let val tl_ans = good_max(tl xs)
	in
	    if hd xs > tl_ans
	    then hd xs
	    else tl_ans
	end

fun countup(from : int, to : int) =
    if from=to
    then to::[]
    else from :: countup(from+1,to)

fun countdown(from : int, to : int) =
    if from=to
    then to::[]
    else from :: countdown(from-1,to)


```

## Options

t option is a type for any type t

building:
NONE has type ‘a option 
SOME e has type t option if e has type t

Accessing:
isSome has type ‘a option -> bool
valOf has type ‘a option -> ‘a (exception if given NONE)
```
(* Programming Languages, Dan Grossman *)
(* Section 1: Options *)

(* badly named: evaluates to 0 on empty list *)
fun old_max (xs : int list) =
    if null xs
    then 0
    else if null (tl xs)
    then hd xs
    else
	let val tl_ans = old_max(tl xs)
	in
	    if hd xs > tl_ans
	    then hd xs
	    else tl_ans
	end

(* better: returns an int option *)
fun max1 (xs : int list) =
    if null xs
    then NONE
    else 
	let val tl_ans = max1(tl xs)
	in if isSome tl_ans andalso valOf tl_ans > hd xs
	   then tl_ans
	   else SOME (hd xs)
	end

(* looks the same as max1 to clients; 
   implementation avoids valOf *)
fun max2 (xs : int list) =
    if null xs
    then NONE
    else let (* fine to assume argument nonempty because it is local *)
	fun max_nonempty (xs : int list) =
		if null (tl xs) (* xs better not be [] *)
		then hd xs
		else let val tl_ans = max_nonempty(tl xs)
		     in
			 if hd xs > tl_ans
			 then hd xs
			 else tl_ans
		     end
	in
	    SOME (max_nonempty xs)
	end

```

## Booleans and Comparison Operations

boolean:
`e1 andalso e2`
`e1 orelse e2`
`not e1`
e1 e2 must be bool 

= <> > < >= <=

 > < >= <= can be used with real
= <> can be used with any equality type but not with real

## Benefits of No Mutation
a valuable non-feature : no mutation
no assignment
avoid the aliases problem

## Optional: Java Mutation
## Pieces of a Language
five things
* syntax
* semantics
* idioms
* libraries
* tools

