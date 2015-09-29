#Specification for C♭ v1.0

##Description and Motivation

C♭ is a correctness-oriented dialect of C♯. For the most part, it is a subset of C♯, or rather it can be realized using a C♯ compiler. The motive for specifying this language is similar to the one that led to the creation of design patterns: To enable better communication between programmers. So, instead of stating something like “you should mark all of your fields `readonly`” or “avoid code reuse through inheritance”,  We can now simply argue for using C♭ when you can and C♯ when you must, and hopefully avoid religious arguments over “style”.

###About the name

C♭ tends to use the [monad](https://en.wikipedia.org/wiki/Monad_(functional_programming)) pattern explicity (through LINQ by implementing [`SelectMany`](http://stackoverflow.com/questions/19321868/linq-selectmany-is-bind)) or implicitly. Thus, the name is a play on words as mondad is also about “flattening”.

##Features

* C♯ and C♭ occupy the performance/correctness dichotomy. Programmers are already accustomed to using multiple general-purpose languages to address the different concerns of a project. C♯ and C♭ are close enough that there should be lower cognitive overhead in switching between the two, but this probably needs rigorous study to validate, and it is conceded that it may be better to have two very dissimilar languages when working at the extremes of a particular dichotomy.

* C♭ forces programs to be simple because it eschews Turing equivalence and is, in fact, biased for creating state machines which are much easier to reason about.


##Specification

###Normative

1.	All classes must be either sealed or abstract.
2.	All fields must be read only.
3.	All errors and warnings in C♯ must be errors in C♭.
4.	All public functions of a class must have the same variance.
5.	Public functions must not return void.
6.	Use of `goto` is an error.

###Non-normative

1.	In C♭, you *apply functions* rather than *call methods*. Methods are a purely abstract concept (this is also true in C♯ and Java despite what the specifications say).
2.	Classes should model the state space of an application.
3.	Class names should represent completed actions (e.g. *Tokenized* rather than *Tokenizer*).
4.	Most public properties and functions should return `IEnumerable<T>` (or a class that implements `SelectMany`) rather than `T`.
5.	Most work should be in the constructors.
6.	Classes should have one public function but may have many public properties.
7.	Public functions should have exactly one formal parameter. If such functions require multiple paramters, they should do so by specifying that a single formal parameter must implement an interface.
8.	Unlike C♯, C♭ makes a disctinction between the concepts of class and type. A class is the same thing in both C♯ and C♭, which is grouping of objects and functions (methods). In C♯ “type” is usually synonomous with the same concept as descibed by a set in mathematics, but this is redundant with respect to the definition of a class. Conversely, in C♭ a type is an invariant relatonship among classes. 
    
    For instance, an `abstract` class, Foo, with two or more subclasses, Bar1, Bar2, ... describes a logical disjunction where Foo is either a Bar1, **or** a Bar2, **or**, ... 

    Similarly, we can model logical conjunctions using interfaces. This if Foo implements interfaces for IBar and IBaz then is at once a IBar and a IBaz.
	


