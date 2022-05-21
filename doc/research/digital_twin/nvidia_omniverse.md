Building Scientifically Accurate Digital Twins Using Modulus with Omniverse and AI
By Bhoomi Gadhia
Discuss (0)
Share

+2
Like
Tags: Computational Fluid Dynamics (CFD), digital twin, featured, HPC / Supercomputing, Modulus, News, Omniverse, physics, Visualization

From physics-informed neural networks (PINNs) to neural operators, developers have long sought after the ability to build real-time digital twins with true-to-form rendering, robust visualizations, and synchronization with the physical system in the real world by streaming live sensor data. The latest release of Modulus brings us closer to this reality.

Modulus 22.03, the cutting-edge framework for developing physics-based machine learning models, offers developers key capabilities such as novel physics informed and data-driven AI architectures, and integration into the Omniverse (OV) platform.

This release takes a major step toward building precise simulations and interactive visualization capabilities for engineers and researchers with the Modulus OV extension. This enhancement is bolstered by new AI architectures that can learn from data using neural operators. Additional enhancements to facilitate precise modeling of problems such as turbulence have been added in this latest version of Modulus, as well as features to improve training convergence.

For a closer look at these new capabilities, see the Modulus 22.03 notes.

Omniverse integration
With the OV integration, training and inference workflows are Python API-based and the resulting trained model outputs are brought in as scenarios into OV using this extension.

This extension can import outputs of the Modulus-trained model into a visualization pipeline for common scenarios such as streamlines and iso-surfaces. It also provides an interface that enables interactive exploration of design variables and parameters to infer new system behavior. ​By leveraging this extension in Omniverse, you can visualize the simulation behavior in the context of the digital twin.​

New network architectures
Modulus now supports neural operators such as FNO, AFNO PINO, and DeepONet architectures. This enables data-driven physics machine learning models for use cases where there is considerable ground truth data available to train from.

FNO: Physics-inspired neural network model that uses global convolutions in spectral space as an inductive bias for training neural network models of physical systems. It incorporates important spatial and temporal correlations, which strongly govern the dynamics of many physical systems that can be described by partial differential equations (PDE). FNO tutorial.
AFNO: The AFNO transformer aims to operate on high-resolution inputs and effectively capture long-range spatial dependencies that are challenging for the FNO. The AFNO offers continuous global convolutions as an alternative to the computationally complex self-attention mechanism. It is based on principled modifications of the FNO to improve expressivity and robustness. These include sparsification of channel and token mixing as well as weight-sharing regularization. The connection to operator learning allows the AFNO transformer to be resolution invariant and to take advantage of large-scale pre-training for improved generalization. AFNO tutorial.
PINO: PINO is the explicitly physics-informed version of the FNO. PINO combines the operating-learning and function-optimization frameworks. In the operator-learning phase, PINO learns the solution operator over multiple instances of the parametric PDE family. In the test-time optimization phase, PINO optimizes the pretrained operator ansatz for the querying instance of the PDE. Learn more in this PINO tutorial.
DeepONet: DeepONet architecture consists of two subnetworks, one for encoding the input function and another for encoding the locations and then merged to compute the output. DeepONets are shown to reduce the generalization error, by employing inductive bias, compared to the fully connected networks. Learn more in this DeepONet Tutorial.
Modulus supports these different architectures to enable our ecosystem of users to pick the right approach that is appropriate for their use case.

More key enhancements
NVIDIA Modulus is available now as a free download through the NVIDIA Developer Zone.

Two-equation (2-eqn.) Turbulence models
Support for 2-equation turbulence (k-e and k-w) models for simulating fully developed turbulent flow. Reference applications for channel case (1D and 2D) using wall functions is included in the documentation. Which showcases two types of wall functions (standard and Launder-Spalding). Learn more in this 2-eqn tutorial.

New algorithms for loss balancing
To help improve the convergence, three new loss balancing algorithms, namely Grad Norm, Relative Loss Balancing with Random Lookback (ReLoBRaLo), and Soft Adapt have been introduced. These algorithms dynamically tune the loss weights based on the relative training rates of different losses.

In addition, Neural Tangent Kernel (NTK) analysis has been incorporated. NTK is a neural network analysis tool that indicates the convergent speed of each component. It provides an explainable choice for the weights for different loss terms. Grouping the mean-squared error of the loss enables the computation of NTK on the fly.

Support for new optimizers
Modulus now supports over 30 optimizers including the built-in PyTorch optimizers and the optimizers in the torch-optimizer library. It includes support for AdaHessian, a second-order stochastic optimizer that approximates an exponential moving average of the Hessian diagonal for adaptive preconditioning of the gradient vector.

NVIDIA Modulus is available now as a free download through the NVIDIA Developer Zone or on the NVIDIA NGC portal.

About the Authors

About Bhoomi Gadhia
Bhoomi Gadhia is a senior product marketing manager at NVIDIA, focused on NVIDIA Modulus, an AI framework for developing physics-informed machine learning neural network models. She has over 10 years of experience in computer-aided engineering applications, working in technical and product marketing roles at Hexagon MSC Software and Ansys. Bhoomi resides in California and holds a master’s in mechanical engineering.
View all posts by Bhoomi Gadhia 