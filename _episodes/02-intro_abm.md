---
title: "Introduction to Agent-Based Modelling"
teaching: 10
exercises: 0
questions:
- "What are agent-based models?"
objectives:
- "Describe the features of an agent-based model"
- "Describe the steps for development of an agent-based model "
keypoints:
- "ABM's have been used in a wide variety of disciplines, yet their are limited applications in Pharmacy."
- "Steps: Hypothesis Specification -> Model Development -> Model Validation"
- "Design principle: Start simple and build to complexity"
---

# Agent-Based Modelling

> An agent-based model (ABM) is a computational model for simulating the actions and interactions of autonomous agents (both individual or collective entities such as organizations or groups) in order to understand the behavior of a system and what governs its outcomes. 
> <cite>[Agent-based Model - Wikipedia](https://en.wikipedia.org/wiki/Agent-based_model)</cite>

To model a complex system we can use a method known as agent-based modelling. 

## Architecture of an ABM

<figure>
  <!-- <img src="{{ page.root }}/fig/sayama_complex_system.png" style="margin:10px;width:600px"/> -->
  <img src="{{ page.root }}/fig/ABMArchitecture.png" style="margin:10px;width:600px"/>
  <figcaption> Simple architecture of a multi-agent system. This image was used from the review by <a href="https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9527397">Zhang et al. </a></figcaption>
</figure><br>

## Building Blocks of an ABM

<figure>
  <!-- <img src="{{ page.root }}/fig/sayama_complex_system.png" style="margin:10px;width:600px"/> -->
  <img src="{{ page.root }}/fig/PARTE_framework.jpg" style="margin:10px;width:800px"/>
  <figcaption> PARTE Framework describing the elements of an agent-based model by <a href="https://www.ncbi.nlm.nih.gov/books/NBK305917/">Hammond </a></figcaption>
</figure><br>




# Why use an agent-based model

| Pros | Cons |
| ----------- | ----------- | 
| Captures emergent phenomena | Randomness is random | 
| Provides a natural description of a system | Models need serve a purpose | 
| Flexible | Large interactions can be computationally intensive | 
| Low cost and time saving approach |  | 


# Applications of ABM

- Flows
- Markets
- Organisations
- Diffusion

**Disciplines:**

| Computer Science | Art | Physics | Ecology | 
| Economics | Biology | Games | Psychology | 
| Engineering | Chemistry | Earth Science | Social Science | 
| Epidimiology  | Philosophy | 


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
Start simple and build up identifying interesting questions along the way (Bottom up).

<br>

## 3. Model Validation

- Statistical analysis of the results
- Evaluation the results and connection with the driving question/hypothesis
- Verification and validation

# Other Resources 

> ## Other Model Development Suggestions
> 
> There many ways to approach the model development process. In the above, we provided a simple suggested approach to get started. While reading the literature on ABM design, many different authors will have suggestion for an approach. Theses are usually based on the industry. As an example, we have inlcuded the table below from a policy development perspective. [Link to table](https://www.ncbi.nlm.nih.gov/books/NBK305917/table/tab_A-1/?report=objectonly). In ecology, for example, is the [ODD protocols](https://ethz.ch/content/dam/ethz/special-interest/usys/ites/ecosystem-management-dam/documents/EducationDOC/EM_DOC/Recommended%20readingDOC/Grimm_2010.pdf), which stands for overview, design concepts, and detail. In their detailed guide, the authors provide substantional information and examples on how to report a model.  
>
> **Key Step** | **Description**
> -------------|---------------
> 1. Definition of question or goal | Thoroughly consider and spell out the goal that the model will be designed to serve or the specific questions that it will try to answer.
> 2. Model scope and conceptual design | Identify key concepts, structures, and relationships from the literature and preliminary studies. Determine clearly defined geographic and temporal contexts that are sufficient to achieve research goals.
> 3. Model specification | Design the model, operationalizing the model “ingredients” identified in the previous step in an implementation-ready way. 
> 4. Model implementation | Translate the specified model into a computationally operational program. Determine initial model parameter values by using estimates from real-world data and engagement with content domain experts.                                                                                             
> 5. Analysis|                                                                                        
>   - Testing and calibration | Test the model against real-world data and, if necessary, iteratively calibrate the model design and parameters. 
>   - Designing experiments and conducting analysis | Create simulated scenarios that use the model to test hypotheses that are central to the research focus, and interpret their results to explore research questions.
>   - Sensitivity analysis | Sweep parameter space to identify key leverage points (i.e., parameter values at which small changes in the system can result in drastic changes in outcomes) and to map the set of assumptions and parameter choices that are inputs into the model onto the set of outcomes that it can produce. 
> 6. Synthesis and reporting | Combine findings from experiments and sensitivity analysis and interpret conceptually. Compile statistical analyses and visualizations of results that clearly depict and document research procedures and findings.                                                                               
> 
{: .solution}



> ## Other Methods for Modelling a Complex System
>
> - System Dynamics
> - Markov Modelling
{: .solution}

# References
1. Bazghandi, A. (2012). Techniques, advantages and problems of agent based modeling for traffic simulation. International Journal of Computer Science Issues (IJCSI), 9(1), 115.
2. Zhang, W., Valencia, A., & Chang, N. B. (2021). Synergistic integration between machine learning and agent-based modeling: A multidisciplinary review. IEEE Transactions on Neural Networks and Learning Systems.
3. Salgado, M., & Gilbert, N. (2013). [Agent based modelling](https://scholar.google.com/scholar_url?url=https://brill.com/downloadpdf/book/edcoll/9789462094048/BP000013.pdf&hl=en&sa=T&oi=gsb&ct=res&cd=0&d=2184768083153287837&ei=jJe7YoyKPMiUywTuz5nQBg&scisig=AAGBfm1jFm4G5rtSttZ0A0jXzNIZNUpahw). In Handbook of quantitative methods for educational research (pp. 247-265). Brill.
4. Wilensky, U., & Rand, W. (2015). An introduction to agent-based modeling: modeling natural, social, and engineered complex systems with NetLogo. Mit Press.
5. Hammond, R. A. (2015). Considerations and best practices in agent-based modeling to inform policy. In Assessing the use of agent-based models for tobacco regulation. National Academies Press (US).