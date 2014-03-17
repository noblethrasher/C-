#Specification for C♭ v1.0

##Description and Motivation

C♭ is a correctness-oriented dialect of C#. For the most part, it is a subset of C#, or rather it can be realized using a C# compiler. The motive for specifying this language is similar to the one that led to the creation of design patterns: to enable better communication between programmers. So, instead of saying something like “you should mark all of your fields `readonly`” or “avoid code reuse through inheritance”,  I can now simply argue for using C♭ when you can and C# when you must, and hopefully avoid religious arguments over style guides.

###Normative

1.	All classes must be either sealed or abstract.
2.	All fields must be read only.
3.	All errors and warnings in C# must be errors in C♭.
4.	All public functions of a class must have the same variance.
5.	Public functions must not return void.
6.	Use of goto is an error.

###Non-normative

1.	In C♭, you call functions not methods. Methods are a purely abstract concept (this is also true in C# and Java despite what the specifications say).
2.	Classes should model the state space of an application.
3.	Class names should be perfective aspect verbs that represent completed actions (e.g. Tokenized rather than Tokenizer).
4.	Most properties and functions should return IEnumerable<T> rather than T.
5.	Most work should be in the constructors.
6.	Classes should have one public function but may have many public properties.
7.	Public functions should have exactly one formal parameter.
