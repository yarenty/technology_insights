

## AI kit

https://lib.rs/crates/ai_kit

AI_Kit aims to be a single dependency for various classic AI algorithms.

Core project goals are:

convenient and ergonomic interfaces to various algorithms by building around traits.
only build what you need through the use of feature flags
performance
easy to understand implementations
All of the algorithms (documented below) operate on several core traits, BindingsValue, Unify, Operation.

ai_kit provides optional data structures that implement these traits, allowing all algorithms to be usable out of the box - see Datum and Rule. Quick examples are provided before, followed by more in-depth documentation.




## Big brain


https://lib.rs/crates/big-brain


big-brain is a Utility AI library for games, built for the Bevy Game Engine

It lets you define complex, intricate AI behaviors for your entities based on their perception of the world. Definitions are heavily data-driven, using plain Rust, and you only need to program Scorers (entities that look at your game world and come up with a Score), and Actions (entities that perform actual behaviors upon the world). No other code is needed for actual AI behavior.

See the documentation for more details.

Features
Highly concurrent/parallelizable evaluation.
Integrates smoothly with Bevy.
Easy AI definition using idiomatic Rust builders. You don't have to be some genius to define behavior that feels realistic to players.
High performance--supports hundreds of thousands of concurrent AIs.
Graceful degradation--can be configured such that the less frame time is available, the slower an AI might "seem", without dragging down framerates, by simply processing fewer events per tick.
Proven game AI model.
Low code overhead--you only define two types of application-dependent things, and everything else is building blocks!
Highly composable and reusable.
State machine-style continuous actions/behaviors.
Action cancellation.
Example
As a developer, you write application-dependent code to define Scorers and Actions, and then put it all together like building blocks, using Thinkers that will define the actual behavior.


## kMeans

https://github.com/rust-ml/book/blob/master/src/3_kmeans.md



## Linfa 

https://github.com/rust-ml/linfa



More about rust:  [[core]]

