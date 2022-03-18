# Links

- WIKI - Incremental Computing

https://en.wikipedia.org/wiki/Incremental_computing



- Adapton

http://adapton.org/

Main page 

Programming language abstractions for Incremental Computation.

http://plum-umd.github.io/adapton/

(also publications and people)



https://github.com/Adapton







- Salsa

https://github.com/nikomatsakis/salsa

Rust 

Generic framework for on-demand incremented computation



- Glimmer

https://github.com/glimmerjs/glimmer-vm

Typescript

Glimmer is a flexible, low-level rendering pipeline for building a "live" DOM from a superset of the [Handlebars](http://handlebarsjs.com/) templating language that can subsequently be updated cheaply when data changes.



- SKIP

http://skiplang.com/

Skip is a general-purpose programming language that tracks side effects to provide caching with reactive invalidation, ergonomic and safe parallelism, and efficient garbage collection. Skip is statically typed and ahead-of-time compiled using LLVM to produce highly optimized executables.

Playground: http://skiplang.com/playground/



- Adaptive - library for incremental computing

https://hackage.haskell.org/package/Adaptive

Haskel [monads]

This is a Haskell (plus some extensions) implementation of a library for incremental computing. It closely follows the implementation in the nice POPL 2002 paper "Adaptive Functional Programming", by Umut Acar, Guy Blelloch and Bob Harper.





- Incremental

https://github.com/janestreet/incremental

Incremental is a library that gives you a way of building complex computations that can update efficiently in response to their inputs changing, inspired by the work of [Umut Acar et. al.](http://www.umut-acar.org/self-adjusting-computation) on self-adjusting computations. Incremental can be useful in a number of applications, including:

BLOG (intro): https://blog.janestreet.com/introducing-incremental/

 

- Reactive - RS

https://github.com/aldanor/reactive-rs

This crate provides the building blocks for functional reactive programming (FRP) in Rust. It is inspired by [carboxyl](https://crates.io/crates/carboxyl), [frappe](https://crates.io/crates/frappe) and [bidule](https://crates.io/crates/bidule) crates, and various [ReactiveX](http://reactivex.io/) implementations.





## Articles

- About Skip

https://news.ycombinator.com/item?id=18077612

Just introduce a syntax to define immutable variables (e.g. like "val" in Scala) and to mark particular functions as pure (easy to implement manually as a decorator in Python, I've been using it a lot) and memoization becomes a seemingly easy task. Why a new language?

By the way it seems very sad to me that the majority of imperative and hybrid (functional×imperative) languages lack syntax for immutable variables: in just so many cases I introduce a variable to store an intermediate result of an operation an don't mean to re-assign it ever after, it's nice of a developer to define this intention explicitly and of a compiler to raise an error when the variable is re-assigned accidentally - this simple feature is among the reasons why Scala programs usually are comparably easy to debug and run as expected as soon as they get compiled successfully.



- Adapton

https://news.ycombinator.com/item?id=18748663

Neat, I didn't know that the new reference implementation was in Rust. It's interesting because the Rust compiler developers are themselves writing a framework for incremental computation, inspired by Adapton, for use in the compiler itself: https://github.com/nikomatsakis/salsa (note: WIP)





## Papers

- Self-adjusting computation

https://www.semanticscholar.org/paper/Self-adjusting-computation%3A-(an-overview)-Acar/a30d1aaab9419f09af35b9f0d16581e47eb280ac



- Reactive Imperative Programming with Dataflow Constraints

https://arxiv.org/pdf/1104.2293.pdf

Dataflow languages provide natural support for specifying constraints between objects in dynamic applications, where programs need to react efficiently to changes of their environment. Re - searchers have long investigated how to take advantage of dataflow constraints by embedding them into procedural languages. Previous mixed imperative/dataflow systems, however, require syntactic extensions or libraries of ad hoc data types for binding the imperative program to the dataflow solver. In this paper we propose a novel approach that smoothly combines the two paradigms without placing undue burden on the programmer



- A theory of changes for higher-order languages — incrementalizing λ-calculi by static differentiation

https://web.archive.org/web/20170628103354/lambda-the-ultimate.org/node/5115

https://www.semanticscholar.org/paper/A-theory-of-changes-for-higher-order-languages%3A-by-Cai-Giarrusso/5ade5a1bafecf4d62c5a77366e995fc3862ea008



- Differential Dataflow

https://www.semanticscholar.org/paper/Differential-Dataflow-McSherry-Murray/f5df61effe8047eb9ea1702cfcc268dbba678567



- Adapton - Composable, Demand-Driven Incremental Computation

http://www.cs.umd.edu/~hammer/adapton/

https://dl.acm.org/doi/10.1145/2666356.2594324







- IceDust - Incremental and eventual computation of derived values in persistent object graphs

https://drops.dagstuhl.de/opus/volltexte/2016/6105/

Derived values are values calculated from base values. They can be expressed in object-oriented languages by means of getters calculating the derived value, and in relational or logic databases by means of (materialized) views. However, switching to a different calculation strategy (for example caching) in object-oriented programming requires invasive code changes, and the databases limit expressiveness by disallowing recursive aggregation. In this paper, we present IceDust, a data modeling language for expressing derived attribute values without committing to a calculation strategy. IceDust provides three strategies for calculating derived values in persistent object graphs: Calculate-on-Read, Calculate-on-Write, and Calculate-Eventually. We have developed a path-based abstract interpretation that provides static dependency analysis to generate code for these strategies. Benchmarks show that different strategies perform better in different scenarios. In addition we have conducted a case study that suggests that derived value calculations of systems used in practice can be expressed in IceDust.



- Incremental computation with Names

https://arxiv.org/abs/1503.07792

Over the past thirty years, there has been significant progress in developing general-purpose, language-based approaches to incremental computation, which aims to efficiently update the result of a computation when an input is changed. A key design challenge in such approaches is how to provide efficient incremental support for a broad range of programs. In this paper, we argue that first-class names are a critical linguistic feature for efficient incremental computation. Names identify computations to be reused across differing runs of a program, and making them first class gives programmers a high level of control over reuse. We demonstrate the benefits of names by presenting NOMINAL ADAPTON, an ML-like language for incremental computation with names. We describe how to use NOMINAL ADAPTON to efficiently incrementalize several standard programming patterns -- including maps, folds, and unfolds -- and show how to build efficient, incremental probabilistic trees and tries. Since NOMINAL ADAPTON's implementation is subtle, we formalize it as a core calculus and prove it is from-scratch consistent, meaning it always produces the same answer as simply re-running the computation. Finally, we demonstrate that NOMINAL ADAPTON can provide large speedups over both from-scratch computation and ADAPTON, a previous state-of-the-art incremental computation system.





- Alphonse - incremental computation as a programming abstractio

https://dl.acm.org/doi/10.1145/143103.143139

Alphonse is a program transformation system that uses dynamic dependency analysis and incremental computation techniques to automatically generate efficient dynamic implementations from simple exhaustive imperative program specifications.





## Books

- Self-adjusting computation with Delta ML

https://link.springer.com/chapter/10.1007%2F978-3-642-04652-0_1







## Videos

- Data driven UIs, incrementaly

https://www.youtube.com/watch?v=R3xX37RGJKE



- Reflex - reactive programming at Facebook

https://www.youtube.com/watch?v=AGkSHE15BSs

















