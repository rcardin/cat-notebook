# Category Theory Notebook

The following is a not-exhaustive list of notes that I took while I was reading multiple articles and posts and books on Category Theory. At the end of this notebook, you will find the references, from which I took the notes.

Happy reading!

## Why should I learn Category Theory as a programmer / developer

The basic idea behind category theory is composition. The composition is the concept behind every programming paradigm. We compose procedures, objects or functions. We need to compose because we need to decompose difficult structures to manage complexity.

In functional programming, we compose functions, but also "concurrency", which means we can treat the concurrency execution of programs as an object that can be composed. This is a _killer feature_, because of the multicore hardware revolution.

## Introduction: Arrows and Objects
A category is a set of objects and arrows that go between them. Arrows compose: If there is an arrow between objects `A` and `B`, then there must be an arrow between objects `A` and `C`. This last arrow is called the _composition_ of the previous two. 

Arrows are also called _morphisms_. Morphisms can be thought of as functions. Their composition is denoted by a small circle between functions: `g∘f`. Functions compose right to left. You should read the formula `g∘f` as "_apply g after f", precisely in the same way you read the function `g(f(a))`.

Different programming languages support function composition, using a dedicated syntax.

Haskell provides the following syntax. Given the functions `f :: A -> B` and `g :: B -> C`, their composition is achieved through the function `g . f` (or `g ∘ f`, for the _hardcore_ developers).

## References
- [Category Theory for Programmers](https://bartoszmilewski.com/2014/10/28/category-theory-for-programmers-the-preface/)
- [Learn You a Haskell for Great Good](http://learnyouahaskell.com/)
