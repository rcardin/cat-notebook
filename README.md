# Category Theory Notebook

The following is a not-exhaustive list of notes that I took while I was reading multiple articles and posts and books on Category Theory. At the end of this notebook, you will find the references, from which I took the notes.

Happy reading!

## Why should I learn Category Theory as a programmer / developer

The basic idea behind category theory is composition. The composition is the concept behind every programming paradigm. We compose procedures, objects or functions. We need to compose because we need to decompose difficult structures to manage complexity.

In functional programming, we compose functions, but also "concurrency", which means we can treat the concurrency execution of programs as an object that can be composed. This is a _killer feature_, because of the multicore hardware revolution.

## Introduction: Arrows and Objects
A category is a set of objects and arrows that go between them. Arrows compose: If there is an arrow between objects `A` and `B`, then there must be an arrow between objects `A` and `C`. This last arrow is called the _composition_ of the previous two. 

Arrows are also called _morphisms_. Morphisms can be thought of as functions. Their composition is denoted by a small circle between functions: `g∘f`. Functions compose right to left. You should read the formula `g∘f` as "_apply g after f_", precisely in the same way you read the function `g(f(a))`.

Different programming languages support function composition, using a dedicated syntax.

Haskell provides the following syntax. Given the functions `f :: A -> B` and `g :: B -> C`, their composition is achieved through the function `g . f` (or `g ∘ f`, for the _hardcore_ developers).

In Scala, the composition has two dedicated methods, despite of you want to compose f with g or viceversa. Using the `compose` function, you can achieve the same semantics of the mathematical composition `g∘f`. 
```scala
val fComposeG = g _ compose f _
``` 
is equal to `g(f(x)`. Whereas, `andThen` has the opposite semantics. 
```scala
val gAndThenF = g _ andThen f _
``` 
is equal to `f(g(x)`.

### Arrows composition properties

The composition of "arrows", or _morphisms_, must satisfy some propeties. In details, the composition must be associative and it must have a _unit of composition_.

Being associative means that no matter what is the order you compose three composable morphisms, they must always return the same result. In other words, it means the following.

```
(g ∘ f) ∘ h = g ∘ (f ∘ h) = g ∘ f ∘ h
```

The unit of composition is an arrow that simply starts and ends in the same category object. In the case of functions, the identity function just returns its argument. In Haskell is defined as the following.

```haskell
id :: a -> a
id x = x
```

Such morphim, when composed with any other morphism, returns the latter.

## References
- [Category Theory for Programmers](https://bartoszmilewski.com/2014/10/28/category-theory-for-programmers-the-preface/)
- [Learn You a Haskell for Great Good](http://learnyouahaskell.com/)
- [Pattern Matching and Functional Composition](https://twitter.github.io/scala_school/pattern-matching-and-functional-composition.html)
