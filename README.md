# classifier-adversary
This notebook is inspired by the paper: [Decorrelated Jet Substructure Tagging using Adversarial Neural Networks](https://arxiv.org/abs/1703.03507).

We illustrate how to use the Adversarial Neural Network to decouple a classifier response from the values of its input.
In other words, we are interested in making the output of a classifier independent from the value distribution of the input. 
This property is useful to reduce the uncertainty about the effect of one feature on the classifier's output.
Although this approach reduces the discriminative power of the classifier, but it keeps a relatively good performance.

**Problem describtion:**

We have a labeled data describing 6 different types of particles. 


*   **Target variable**: particles type (electron, proton, kion, pion, muon or ghost)
*   **Features**: The responses of LHCs detecors like(particle momentum, energy, track, ... etc)


We want to train a model capable of determining the particle type depending on its features. Our goal is to make predicting the type of the particle independent from the value distribution of its features.

First, we will build a classifier without adversary, to see how the classification output is sensitive to the values of the particle's momentum.

Second, we will use an adversarial network to penalizes the classifier when it makes predictions that distort the momentum spectrum.
