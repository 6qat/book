# Generating a Modern Web Application #

> "Nobody really creates perfect code the first time... except
me, but there is only one of me" - Linus Torvalds

## Introduction ##

My first computer was an Apple II (actually, it was a clone of Jobs' first popular personal computer) when I was 10 years old.

Javascript is the Assembly language of the web.

### Static typing versus Dynamic typing ###

In dynamic typed languages, the type is associated with the VALUE. Static typed languages has the type associated with VARIABLES.

## Mixing tons of technologies ##

## HTML and the HTTP protocol ##

I first started creating web sites when I entered in the university for an undergraduate degree in Electrical Engineering. At that time, the commercial Internet was just starting, and I was one of the privileged students who had access to it.  

## Javascript ##

## Scala ##

### Classes and Objects ###

In scala, val definitions inside classes (fields) are really special cases of methods. They can override methods and implement abstract methods in traits. The only difference between methods and fields concerns only initialization. A val object is evaluated when your object is first initialized where a def is evaluated each time it's called/referenced.

Function types relate to classes, as function values relate to objects.

#### Polymorfism ####

There are two fundamental forms of polymorfism:

* Subtyping: instances of a subclass can be used where instances of a superclass are expected (originally implemented in OO languages).
* Generics: instances of a class of function are created by type parametrization (originally implemented in functional languages).

### Methods and functions ###

When it may or may not return a value, use Option[T], which can be either None or Some[T]. It behaves as a collection of just one element.

If the function won't return successfully, the return type is Nothing. Ex. exceptions and exit(1). 

>scala> def kill = exit(1)  
kill: Nothing

Abstracting away from the programmer the need for lower level resource handling:
>def doit(r: Resource, f: (Resource) => Unit): Unit = {
> try { 
    f(r) 
  }
  finally {
    r.dispose()
  }

Tail recursion normally implies defining a function inside the original recursive function, but this time with an extra parameter that passes the calculated cumulative  value from each iteration.

Functions are objects with apply() methods. Ex.: http://d.pr/i/n7M5 , http://d.pr/i/NSH1

Methods are not themselves function values, but when used in a place where a function value is expected,
it is converted automatically to the function value  (http://d.pr/i/pckq). It's also called eta-expansion.

Arrays are specializations of functions in Scala. For this reason, accessing an element of an array is made by () instead of [].

#### Types of method invocation ####

* Call-by-reference: AnyRef
* Call-by-value: AnyVal
* Call-by-name(call-by-need): Scala passes the parameter as a function. It's evaluated only when first used.

Scala, as well as Java and Haskell, has a concept called "type erasure". All type parameters and type arguments are removed before evaluating the program. It's only used by the compiler. Some other languages, on the other hand, keep type parameters around at runtime. C++, C# and F# are examples of this kind of languages.

#### Anonymous functions ####

Given the anonymous function (lambda):

> (x: Int, y: Int) => x + y

We can rewrite it by it's definition followed by a call:

> def f (x: Int, y: Int) = x + y; f

It can be said that anonymous functions are a kind of syntatic sugar.


### Collections ###

The method :::, defined in List, appends the content of one list to another. Despite if this fact, it's a prepend operator:
Ex. xs ::: ys is equivalente of ::: being called on ys and passing xs as a parameter: ys.:::(xs)

The cons operator (::) appends a tail into a head element. 


IMPORTANT: Lists are covariant, but Arrays in Scala are not. Types that accepts mutations of it's elements should not
be variant. Immutable types, on the other hand, can be covariant if some conditions on methods are met.

### Implicits ###

There are 3 kinds of implicits:

* Implicit conversion to an expected type: automatic converting an argument to a method or function from a different type to a correct type (type expected), as long as there is an
implicit conversion function in the scope.
* Converting the receiver: automatic converting the receiver object of a method call into a different type when an absent method is called, as long as there
is an implicit conversion function in the scope.
* Implicit parameters: implicitly apply scope available implicit values into functions or methods which have implicit implicit arguments.

## All together now ##

In this chapter we are going do create a modern web application from scratch, mixing together all the technologies we studied in former chapters.

