

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


`linfa` aims to provide a comprehensive toolkit to build Machine Learning applications with Rust.

Kin in spirit to Python's `scikit-learn`, it focuses on common preprocessing tasks and classical ML algorithms for your everyday ML tasks.

**[Website](https://rust-ml.github.io/linfa/) | [Community chat](https://rust-ml.zulipchat.com/)**

[Current state](https://github.com/rust-ml/linfa#current-state)

Where does `linfa` stand right now? [Are we learning yet?](http://www.arewelearningyet.com/)

`linfa` currently provides sub-packages with the following algorithms:


[clustering](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-clustering)
Clustering of unlabeled data; contains K-Means, Gaussian-Mixture-Model, DBSCAN and OPTICS

[kernel](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-kernel)
Maps feature vector into higher-dimensional space

[linear](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-linear)
Contains Ordinary Least Squares (OLS), Generalized Linear Models (GLM)

[elasticnet](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-elasticnet)
Linear regression with elastic net constraints

[logistic](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-logistic)
Builds two-class logistic regression models

[reduction](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-reduction)
Diffusion mapping and Principal Component Analysis (PCA)

[trees](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-trees)
Linear decision trees

[svm](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-svm)
Classification or regression analysis of labeled datasets

[hierarchical](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-hierarchical)
Agglomerative hierarchical clustering
Cluster and build hierarchy of clusters

[bayes](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-bayes)
Naive Bayes
Contains Gaussian Naive Bayes

[ica](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-ica)
Independent component analysis
Contains FastICA implementation

[pls](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-pls)
Partial Least Squares
Contains PLS estimators for dimensionality reduction and regression

[tsne](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-tsne)
Dimensionality reduction
Contains exact solution and Barnes-Hut approximation t-SNE

[preprocessing](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-preprocessing)
Normalization & Vectorization
Contains data normalization/whitening and count vectorization/tf-idf

[nn](https://github.com/rust-ml/linfa/blob/master/algorithms/linfa-nn)
Nearest Neighbours & Distances
Spatial index structures and distance functions


If this strikes a chord with you, please take a look at the [roadmap](https://github.com/rust-ml/linfa/issues/7) and get involved!



More about rust:  [[core]]


## Liquid ML

https://crates.io/crates/liquid-ml

LiquidML is a platform for distributed, scalable data analysis for data sets too large to fit into memory on a single machine. It aims to be easy and simple to use, allowing users to easily create their own map and filter operations, leaving everything else to liquid_ml. It ships with many example uses, including the decision tree and random forest machine learning algorithms built in, showing the power and ease of use of the platform.

LiquidML is written in Rust for both performance and safety reasons, allowing many optimizations to be made more easily without the risk of a memory safety bug. This helps guarantee security around our clients' data, as many memory safety bugs can be exploited by malicious hackers.

LiquidML is currently in the state of an MVP. Tools on top of LiquidML can built and several examples are included in this crate to demonstrate various use cases.


## Easy ML



https://github.com/Skeletonxf/easy-ml

This is a pure Rust library which makes heavy use of passing closures, iterators, generic types, and other rust idioms that machine learning libraries which wrap around another language backend could never provide easily. This library tries to provide adequate documentation to explain what the functions compute, what the computations mean, and examples of tasks you might want to do with this library:

Linear Regression
k-means Clustering
Logistic Regression
Naïve Bayes
Feedforward neural networks
Backprop with Automatic Differentiation
using a custom numeric type such as num_bigint::BigInt
Handwritten digit recognition in the browser
This library is not designed for deep learning. The implementations of everything are more or less textbook mathematical definitions, and do not feature extensive optimisation. You might find that you need to use a faster library once you've explored your problem, or that you need something that's not implemented here and have to switch. I hope that being able to at least start here may be of use.




## Util ML


https://github.com/radialHuman/rust/tree/master/util/util_ml

https://crates.io/crates/simple_ml

@TODO: This really need proper refactoring. 
one file libraries ...
looks like it should work ...





