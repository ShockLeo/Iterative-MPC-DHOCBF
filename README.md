# Iterative-convex-MPC-with-CBFs
Matlab code for the paper **"Iterative Convex Optimization for Model Predictive Control with Discrete-Time High-Order Control Barrier Functions"**, submitted to IEEE American Control Conference (ACC) 2023, Authors: ***Shuo Liu, Jun Zeng,  Koushil Sreenath and Calin Belta***  

This is the reference implementation of our paper: [PDF](https://arxiv.org/pdf/2210.04361.pdf)  

In this paper, we propose a framework that solves the safety critical MPC problem in an iterative optimization, which is applicable for any relative-degree control barrier functions. In the proposed formulation, the nonlinear system dynamics as well as the safety constraints modeled as discrete-time high order control barrier functions (DHOCBF) are linearized at each time step. Our formulation is generally valid for any control barrier function with an arbitrary relative-degree. The advantages of fast computational performance with safety guarantee are analyzed and validated with numerical results.  
