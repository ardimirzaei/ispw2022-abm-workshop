---
title: "Introduction to Agent-Based Modelling"
teaching: 10
exercises: 0
questions:
- "What are agent-based models?"
objectives:
- "Describe the features of an agent-based model"
keypoints:
- "ABM's have been used in a wide variety of disciplines, yet their are limited applications in Pharmacy."
- "Design principle: Start simple and build to complexity"
---

# Agent-Based Modelling

> An agent-based model (ABM) is a computational model for simulating the actions and interactions of autonomous agents (both individual or collective entities such as organizations or groups) in order to understand the behavior of a system and what governs its outcomes. 
> <cite>[Agent-based Model - Wikipedia](https://en.wikipedia.org/wiki/Agent-based_model)</cite>

To model a complex system we can use a method known as agent-based modelling. 
<figure>
  <!-- <img src="{{ page.root }}/fig/sayama_complex_system.png" style="margin:10px;width:600px"/> -->
  <img src="{{ page.root }}/fig/ABMArchitecture.png" style="margin:10px;width:600px"/>
  <figcaption> Simple architecture of a multi-agent system. This image was used from the review by <a href="https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9527397">Zhang et al. </a></figcaption>
</figure><br>





# Why use an agent-based model

| Pros | Cons |
| ----------- | ----------- | 
| Captures emergent phenomena | Randomness is random | 
| Provides a natural description of a system | Models need serve a purpose | 
| Flexible | Large interactions can be computationally intensive | 
| Low cost and time saving approach |  | 

<cite>Bazghandi</cite>

# Applications of ABM

- Flows
- Markets
- Organisations
- Diffusion

**Disciplines:**

- Computer Science
- Economics
- Engineering
- Art
- Biology
- Chemistry
- Physics
- Games
- Earth Science
- Ecology
- Psychology
- Social Science
- Epidimiology 
- Philosophy

***... But no pharmacy?***

<br>

# Development of an agent-based model


<figure>
  <!-- <img src="{{ page.root }}/fig/sayama_complex_system.png" style="margin:10px;width:600px"/> -->
  <img src="https://www.researchgate.net/profile/Mauricio-Salgado/publication/259335210/figure/fig1/AS:297057723142144@1447835488456/Main-steps-and-stages-to-build-an-agent-based-model.png" style="margin:10px;width:600px"/>
  <figcaption> Steps involved in building and agent-based model. This image is from the chapter on <a href="https://link.springer.com/chapter/10.1007/978-94-6209-404-8_12">Agent-Based Modelling </a> and was sourced from the authors <a href="https://www.researchgate.net/profile/Mauricio-Salgado">Research Gate Profile</a>.</figcaption>
</figure><br>


1. Hypothesis Specification
2. Model Development
3. Model Validation

## 1. Hypothesis Specification

When designing the ABM we consider the different types of modelling styles.
Two major styles:
- Phenomena-based modelling
- Exploratory modelling

> ## Phenomena-based modelling
> We have the phenomena in mind that we want to model. Then build characeteristics into our agents and define interactions that explain the model pattern. This creates an explanantory model where we see how adjustments of our input parameters can affect the outcome of our model  
> 
{: .solution}



> ## Exploratory modelling
> 
> We create the agents and define what behaivours they are to take. Then, we run the model and observe the patterns that emerge. These patterns can be then compared to real-world phenomenon and refined to acheive model patterns that are similar. Further iterations of adjustments and comparisons with our real-world phenomenon lead to a model an explanatory model that explains the phenomenon. 
> 
{: .solution}

<br>

Considering these two styles, it is important to precisely define the hypothesis and the question the your model tries to address. A good approach is to embed the model in existing theories. 

<br>

## 2. Model Development

### Stages in designing ABM



1. Formulate a question
  - Clearly defined question which model addresses
2. Choosing your agents and their properties
  - These can be 'individuals' in your model. Alternatively, agent's can be another construct that has a behaviour to be modelled. 
  - Their properties can their characteristics. 
3. Environment characteristics and stationary agents
  - This could be the building/institution/intervention that interacts/influences your agents. 
4. Agent behaviour
  - How they move and act. 
5. Designing the Time Step
  - What happens in each unit of 'time'. Each step of the model actions take place. 
6. Choosing parameters of the model
  - What input parameters can you adjust? Are they for the agent or for the environment?
7. Choosing your measures
  - These are your outputs. What do you want your model to report?

***How to get started building?***

Start simple and add components to address your research question. (Top down) <br>
or <br>
Start simple and build up identifying interesting questions along the way (bottom up).

<br>

## 3. Model Validation

- Statistical analysis of the results
- Evaluation the results and connection with the driving question/hypothesis
- Verification and validation


# Other Methods for Modelling a Complex System

- System Dynamics
- Markov Modelling


# References
- Bazghandi, A. (2012). Techniques, advantages and problems of agent based modeling for traffic simulation. International Journal of Computer Science Issues (IJCSI), 9(1), 115.
- Zhang, W., Valencia, A., & Chang, N. B. (2021). Synergistic integration between machine learning and agent-based modeling: A multidisciplinary review. IEEE Transactions on Neural Networks and Learning Systems.
- Salgado, M., & Gilbert, N. (2013). Agent based modelling. In Handbook of quantitative methods for educational research (pp. 247-265). Brill.