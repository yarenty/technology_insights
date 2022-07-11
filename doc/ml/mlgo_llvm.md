# MLGO

A Machine Learning Framework for Compiler Optimization


https://ai.googleblog.com/2022/07/mlgo-machine-learning-framework-for.html



The question of how to compile faster and smaller code arose together with the birth of modem computers. Better code optimization can significantly reduce the operational cost of large datacenter applications. The size of compiled code matters the most to mobile and embedded systems or software deployed on secure boot partitions, where the compiled binary must fit in tight code size budgets. With advances in the field, the headroom has been heavily squeezed with increasingly complicated heuristics, impeding maintenance and further improvements.

Recent research has shown that machine learning (ML) can unlock more opportunities in compiler optimization by replacing complicated heuristics with ML policies. However, adopting ML in general-purpose, industry-strength compilers remains a challenge.

To address this, we introduce “MLGO: a Machine Learning Guided Compiler Optimizations Framework”, the first industrial-grade general framework for integrating ML techniques systematically in LLVM (an open-source industrial compiler infrastructure that is ubiquitous for building mission-critical, high-performance software). MLGO uses reinforcement learning (RL) to train neural networks to make decisions that can replace heuristics in LLVM. We describe two MLGO optimizations for LLVM: 1) reducing code size with inlining; and 2) improving code performance with register allocation (regalloc). Both optimizations are available in the LLVM repository, and have been deployed in production.


Try it Yourself
Check out the open-sourced end-to-end data collection and training solution on github and a demo that uses policy gradient to train an inlining-for-size policy.

https://github.com/google/ml-compiler-opt

https://github.com/google/ml-compiler-opt/blob/main/docs/demo/demo.md




