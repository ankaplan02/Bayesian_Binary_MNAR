# Bayesian_Binary_MNAR
This repository consists of two functions for an easy to use and intuitive approach to address MNAR Binary Outcomes without Adjusting for covariates 

Conjugate_Beta_Binomial: consists of a fast conjugate prior method that analyzes the aggregate data of missing outcome rates and outcome success rates when the outcome is binary. 
This method uses the Beta-Binomial structure to directly sample from the posterior distributions by incorporating the strictly prior information on the response rate bias, 
namely, the interval limits (d0m, d0M) and (d1m, d1M) for treatment groups 0 and 1, respectively. These limits set the bounds on what a researcher/principal investigator
would expect the response rate bias to be, instead of using just one number for it. The results are aggregated over the prior values drawn for d0 and d1 (from these 
intervals, respectively). You may copy this R function into the R console and store the function to use in an analysis or you may use the "source("...")" call from within
R if you have saved this file in your computer. The easier way would probably be the former and then save the function in a new R script file in a location you want. 

VNP_PMM_within_R: consists of a vague-normal prior pattern mixture model that is fit in the Just Another Gibbs sampler (JAGS) program within R/R studio. You have to 
already have the package 'rjags' installed in your R app. If you don't know how to do this in R, the following code will help: 

- install.packages("rjags")

You may need to install RJAGS from its original website: 
https://sourceforge.net/projects/mcmc-jags/files/rjags/
before using it in R, too. 

This program facilitates Bayesian model estimation/fit in a quicker way than drawing up all of the posterior expressions. In the code we provide, you can see that first 
you specify the likelihood of the data in a for loop (iterating over study subject) where the linear model is assumed (or in this case logistic model), and then underneath
that you specify the prior distribution assumptions on the effects in that linear model. Following that you can have the sampler compute functions of parameters 
like we have and collect posterior samples of them from the function call within R. 

The input for VNP_PMM_within_R is exactly the same as Conjugate_Beta_Binomial. 

SimulationExample: contains the extended VNP_PMM_within_R file that now includes the Conjugate_Beta_Binomial model as well, and they analyze the same simulated data set 
with detailed comments for each of the specifications of the simulation and model fit. 
