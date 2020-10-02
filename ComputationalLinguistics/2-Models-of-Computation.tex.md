## How does language work?
## How is it represented in the mind?
## How is it processed?
## These are the top priorities of the field of study we call #linguistics, also referred to as #generative-linguistics.
## People like Kurt Gödel, Alan Turing, and Alonzo Church were very influential here.
## These people were tinkering with basic models of computation, such as Turing Machines, General Recursive Functions, and The Lambda Calculus.
## Originally, they (the models) were purposed with, aiding in the formalization of #mathematical-computation, the process of writing theorems.
## It was soon realized that The Lambda Calculus and Turing Machines, were equivalent in some sense, and thusly it was stated that #Turing-complete formalisms, represented the boundary of that which could be reliably, or effectively computed. (This is known as the Church-Turing Thesis). 
## Additionally, it was noted that specific machines in either formalism, were capable of universal computation: they could be programmed to complete the task of any given machine.
## Elsewhere Claude Shannon was contemplating the inner workings of the transmission of information, when there was uncertainty in play, giving rise to Information Theory.

## The λ-Calculus and LISP

The λ-Calculus was given to us by Alonzo Church, and was turned into the programming language Lisp, based on list data structures. Lisp was one of the first languages to be considered *functional*, a paradigm that is often considered easier to reason about than it's sister paradigm, OO.

# Functions, Expressions (Eval)uations.

The premiere process in the λ-calculus, is *function application*, and is done with prefix notation in Lisp.

```clojure
(+ 1 3)
```

This is an *expression*, which means any piece of code with correct syntax, that can be *evaluated*. The result of the evaluation is the *value* of the expression.

# Types

In lisp, there is a type attached to every value and expression.

This type is responsible for notifying the interpreter of what it should do with a give expression. The previous expression `(+ 1 3)`, is of the list type, and contains *sub-expressions*, chiefly the (primitive) addition function, and it's two operands/arguments, which are *constants* of the *integer* type.
* LISP is a *homoiconic* language, which means that the programs written in the language, are (analogous to) data structures that exist in the programming language.
Each type has an evaluation rule, that instructs the interpreter on what to do for any given type.

## Creating λ/anonymous functions.

The general form of this function in Clojure is different, naturally, taking the form:
`(fn [<parameters>] <body>). This expression has three parts, which are the function operator, the formal parameters, and the body, which describe what the function does to the parameters. The value of such an expression is a function.

One can apply the function as follows: `((fn [x y] (+ x y)) 1 2)`.

While it may seem weird, the function itself simply plays the role of the 
addition operator, though more specifically, it's placement at the beginning of this
expression, which results in a function value, allows it to be immediately called,
hence the (seemingly unusual) application.

Clojure provides `def` as a way to store values and procedures in variables.

`def` binds a value to a variable name, which results in an expression of the type `symbol`. The interpreter thusly looks for values (or processes) associated with symbols in order to carry them out.

```clojure
(def my-add (fn [x y] (+x y)))
``` 

In Clojure, binding values or procedures to names is no different to the interpreter, because functions are first class citizens.

While `def` works, we can use `defn` to define procedures specifically.

Clojure is lexically scoped, meaning that the value of a variable is dependent upon
the environment it was written in, not the one it was called in.


## Basic Types

Expressions such as bare integers, are atomic, and simply evaluate to themselves.
