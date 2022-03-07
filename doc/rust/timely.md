# Timely Dataflow


https://github.com/frankmcsherry/timely-dataflow


Timely dataflow is a low-latency cyclic dataflow computational model, introduced in the paper Naiad: a timely dataflow system. This project is an extended and more modular implementation of timely dataflow in Rust.

This project is something akin to a distributed data-parallel compute engine, which scales the same program up from a single thread on your laptop to distributed execution across a cluster of computers. The main goals are expressive power and high performance. It is probably strictly more expressive and faster than whatever you are currently using, assuming you aren't yet using timely dataflow.

Be sure to read the documentation for timely dataflow. It is a work in progress, but mostly improving. There is more long-form text in mdbook format with examples tested against the current builds. There is also a series of blog posts (part 1, part 2, part 3) introducing timely dataflow in a different way, though be warned that the examples there may need tweaks to build against the current code.

## An example

To use timely dataflow, add the following to the dependencies section of your project's Cargo.toml file:

```yaml
[dependencies]
timely="*"
This will bring in the timely crate from crates.io, which should allow you to start writing timely dataflow programs like this one (also available in timely/examples/simple.rs):

```

```rust
extern crate timely;

use timely::dataflow::operators::*;

fn main() {
timely::example(|scope| {
(0..10).to_stream(scope)
.inspect(|x| println!("seen: {:?}", x));
});
}
```

You can run this example from the root directory of the timely-dataflow repository by typing
```shell

% cargo run --example simple
Running `target/debug/examples/simple`
seen: 0
seen: 1
seen: 2
seen: 3
seen: 4
seen: 5
seen: 6
seen: 7
seen: 8
seen: 9

```


This is a very simple example (it's in the name), which only just suggests at how you might write dataflow programs.




## Differential Dataflow

An implementation of differential dataflow over timely dataflow on Rust.


https://github.com/TimelyDataflow/differential-dataflow