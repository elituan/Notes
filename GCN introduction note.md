# GCN Introduction

Source: https://towardsdatascience.com/how-to-do-deep-learning-on-graphs-with-graph-convolutional-networks-7d2250723780

## What is Graph Convolutional Network
*	A graph convolutional network is a neuron network that operate on graphs.
*	Summary of graph theory (notebook)
*	Given a graph G=(V,E), a GCN takes a input
    * An input feature matrix X = N x F^0 where N is the number of nodes and F^0 is the number of input features for each node 
    * Square matrix N x N represent the graph structure as the adjacency matrix
*	A Hidden layer in GCN can be written as Hⁱ = f(Hⁱ⁻¹, A))  whre H⁰ = X and f is a propagation. 
* Each layer H^i correspond to an N × Fⁱ feature matrix where each row is a feature representation of a node and was formed by propagation rule from last layer

## A simple propagation rule
Simplest propagation rule: f(Hⁱ, A) = σ(AHⁱWⁱ). Where
* Wⁱ is the weight matrix for layer i.  
* σ is the non-linear activatio function like RELU function
* Weight matrix has dimention Fⁱ × Fⁱ⁺¹. In other words the size of second dimension determines the number of features in next layer. it is similar to the filtering operation in CNN because the funcion is shared accross noses.
* Adding indentity matrix to adjacency matrix to attach the self-loop for each node. In other words the propagation rule will add themself for next layer
* Normalizing the feature representation by multiplying adjency matrix A with inverse degree matrix D. In other words the new propagation rule is f(X, A) = D⁻¹AX

## Spectral Graph convolutions - Thomas Kips
spetrac propagation rule: 
