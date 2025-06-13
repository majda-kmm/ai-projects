# Reproducing Results from "Dropout as a Bayesian Approximation"

This repository contains code and results reproducing three figures from the paper:

**Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning**  
Yarin Gal & Zoubin Ghahramani – ICML 2016  
[Link to paper](https://arxiv.org/pdf/1506.02142)

## Overview

This work aims to reproduce the following key experiments from the original paper:

- **Figure 2** – Bayesian regression with model uncertainty
- **Figure 4** – Classification uncertainty on rotated MNIST digits
- **Figure 6** – Thompson sampling using dropout in contextual bandits

Each experiment was carefully implemented according to the descriptions provided in the paper.

## Figure 2 – Synthetic Regression

We train a 1D regression model with dropout at both training and test time. Model uncertainty is estimated using Monte Carlo sampling over multiple forward passes. The output displays both predictive mean and uncertainty envelopes.

The results show how dropout approximates Bayesian inference, capturing epistemic uncertainty especially in regions without training data.

## Figure 4 – Classification with Uncertainty on MNIST

We train a LeNet convolutional neural network on the full MNIST dataset, using dropout before the final fully connected layer (dropout probability = 0.5). The model is evaluated on 12 rotated versions of the digit "1".

Two visualizations are reproduced:

- (a) Distribution of softmax input values (logits) over 100 stochastic forward passes
- (b) Distribution of softmax output probabilities for the top-3 predicted classes

This demonstrates how uncertainty in classification can be estimated with dropout and how prediction confidence varies under input perturbation.

## Figure 6 – Contextual Bandits with Dropout

We replicate the contextual bandit experiment using a Bayesian neural network trained with dropout. The agent performs Thompson sampling via stochastic forward passes at each timestep.

Performance is compared to ε-greedy baselines. Results confirm that MC dropout provides effective exploration in reinforcement learning settings.
