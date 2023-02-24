# Iterative-convex-MPC-with-CBFs
Matlab code for the paper **"Iterative Convex Optimization for Model Predictive Control with Discrete-Time High-Order Control Barrier Functions"**, accepted by IEEE American Control Conference (ACC) 2023, Authors: ***Shuo Liu, Jun Zeng,  Koushil Sreenath and Calin Belta***  

This is the reference implementation of our paper: [PDF](https://arxiv.org/pdf/2210.04361.pdf)  

In this paper, we propose a framework that solves the safety critical MPC problem in an iterative optimization, which is applicable for any relative-degree control barrier functions. In the proposed formulation, the nonlinear system dynamics as well as the safety constraints modeled as discrete-time high order control barrier functions (DHOCBF) are linearized at each time step. Our formulation is generally valid for any control barrier function with an arbitrary relative-degree. The advantages of fast computational performance with safety guarantee are analyzed and validated with numerical results.  

**Instruction**:  
There are two folders **"Figure2_3_4"** and **"Table1_2"**. **"Figure2_3_4"** has all information to generate figure 2, 3, 4 in paper and **"Table1_2"** is for table 1,2 in paper.  

Inside **"Figure2_3_4"**, *"Closedloop_Trajectories_Hyperparameters"* includes codes to generate necessary data for figure 2-a and figure 3; *"Iterative_Convergence"* includes codes to generate necessary data for figure 2-b,c,d;   
*"Maximum_Iterations"* includes codes to generate necessary data for figure 4.   
*"NMPCDCBF1"* and *"NMPCDCBF2"* include codes related to NMPC-DHOCBF with mcbf=1 and mcbf=2 respectively and *"FigureGenerate"* includes codes to transfer the data into figures in paper.  
First, run *"Closedloop_Trajectories_Hyperparameters"*, *"Iterative_Convergence"* and *"Maximum_Iterations"* and you will see the data files generated as MATLAB mat files.  
Second, run *"FigureGenerate"* to generate all figures in paper, which will be saved in folder **"figures"**.  

Inside **"Table1_2"**, there are four folders including the codes to generate necessary dada for table 1,2 in paper.   
*"gamma1-4gamma2-4"* includes the codes for iMPC-DHOCBF and NMPC-DHOCBF with decay rate parameters gamma1=0.4, gamma2=0.4 and mcbf=2;    
*"gamma1-4"* includes the codes for iMPC-DHOCBF and NMPC-DHOCBF with decay rate parameters gamma1=0.4 and mcbf=1;  
*"gamma1-6gamma2-6"* includes the codes for iMPC-DHOCBF and NMPC-DHOCBF with decay rate parameters gamma1=0.6, gamma2=0.6 and mcbf=2;  
*"gamma1-6"* includes the codes for iMPC-DHOCBF and NMPC-DHOCBF with decay rate parameters gamma1=0.6 and mcbf=1.  
In each folder, run the file *"test_comprehensive"* and you will see corresponding data files generated as MATLAB mat files *"feasibility_N"* and *"timecom_N"* which 
include the information about infeasible rate and mean/variance of computing time (stored in matrices "nmpcdata" and "impcdata") in paper from generating one time-step trajectories for iMPC-DHOCBF and NMPC-DHOCBF.  

Instead, if you want to run the file for different number of horizon parallelly, in folder **"test_each_horizon"**, there are six files called *"test_N4"*,*"test_N8"*,*"test_N12"*,*"test_N16"*,*"test_N20"*,*"test_N24"* which correspond to the number of horizon 4,8,12,16,20,24 for iMPC-DHOCBF and NMPC-DHOCBF.
You can run these 6 files parallely, in order to generate same MATLAB mat files *"feasibility_N"* and *"timecom_N"* which include the information about infeasible rate and mean/variance of computing time in paper from generating one time-step trajectories for iMPC-DHOCBF and NMPC-DHOCBF. You should run the file *"tabledata"* next and all useful data in table are stored in matrices "nmpcdata" and "impcdata".  

**Performance Comparison between NMPC-DHOCBF and iMPC-DHOCBF:**  
1. For comparison of capability of generating safe optimal trajectories for different numbers of horizon and hyperparameters, please see the figure below:  
![image](https://github.com/ShockLeo/Iterative-convex-MPC-with-CBFs/blob/main/Figure2_3_4/performance2.png)  
2. For comparison of infeasible rate and mean/variance of computing time from generating one time-step trajectories, please see the figure below:  
![image](https://github.com/ShockLeo/Iterative-convex-MPC-with-CBFs/blob/main/Table1_2/performance.png) 
For other figures please refer to the paper.  

**Dependencies:**  
The packages needed for running the code are [Yalmip](https://yalmip.github.io/) and [IPOPT](https://github.com/coin-or/Ipopt) for NMPC-DHOCBF and [OSQP](https://github.com/osqp/osqp) for iMPC-DHOCBF.
