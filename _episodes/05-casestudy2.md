---
title: "Bonus Case: Modelling an epidemic"
teaching: 5
exercises: 15
questions:
- "Can we model the effects of a epidemic?"
objectives:
- "Conduct a simple experiment using an ABM"
keypoints:
- "Dask builds on numpy and pandas APIs but operates in a parallel manner"
- "Computations are by default lazy and must be triggered - this reduces unneccessary computation time"
---

# EpiDEM

This model simulates the spread of an infectious disease in a closed population. This particular model is formulated based on a mathematical model that describes the systemic dynamics of a phenomenon that emerges when one infected person is introduced in a wholly susceptible population. This basic model, in mathematical epidemiology, is known as the Kermack-McKendrick model.

The Kermack-McKendrick model assumes a closed population, meaning there are no births, deaths, or travel into or out of the population. It also assumes that there is homogeneous mixing, in that each person in the world has the same chance of interacting with any other person within the world. In terms of the virus, the model assumes that there are no latent or dormant periods, nor a chance of viral mutation.

Because this model is so simplistic in nature, it facilitates mathematical analyses and also the calculation of the threshold at which an epidemic is expected to occur. We call this the reproduction number, and denote it as R0. Simply, R0 stands for the number of secondary infections that arise as a result of introducing one infected person in a wholly susceptible population, over the course of the infected person's contagious period (i.e. while the person is infective, which, in this model, is from the beginning of infection until recovery).

This model incorporates all of the above assumptions, but each individual has a 5% chance of being initialized as infected. This model shows the disease spread as a phenomenon with an element of stochasticity. Small perturbations in the parameters included here can in fact lead to different final outcomes.

Overall, this model helps users:
1) engage in a new way of viewing/modeling epidemics that is more personable and relatable 
2) understand how the reproduction number, R0, represents the threshold for an epidemic 
3) think about different ways to calculate R0, and the strengths and weaknesses in each approach 
4) understand the relationship between derivatives and integrals, represented simply as rates and cumulative number of cases, and 
5) provide opportunities to extend or change the model to include some properties of a disease that interest users the most.

# Applications to Pharmacy

- model disease spread
- 


# NetLogo Model


[Run application on the Web](http://www.netlogoweb.org/launch#http://www.netlogoweb.org/assets/modelslib/Curricular%20Models/epiDEM/epiDEM%20Basic.nlogo)
*Alternative, if you are still in the web appilication, search for the model:* ***epiDEM Basic*** *in Model Library*


## Activities

>
>
>
>
{: .discussion}
