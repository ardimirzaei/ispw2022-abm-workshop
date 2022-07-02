---
title: "Instructor Notes"
---

# Why is an ABM useful for Emergent Phenomna

**Text from the paper by Bonabeau. [https://www.ncbi.nlm.nih.gov/pmc/articles/PMC128598/](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC128598/)** 
Bonabeau, E. (2002). Agent-based modeling: Methods and techniques for simulating human systems. *Proceedings of the national academy of sciences*, 99(suppl_3), 7280-7287.

One may want to use ABM when there is potential for emergent phenomena, i.e., when:
- Individual behavior is nonlinear and can be characterized by thresholds, if-then rules, or nonlinear coupling. Describing discontinuity in individual behavior is difficult with differential equations.
- Individual behavior exhibits memory, path-dependence, and hysteresis, non-markovian behavior, or temporal correlations, including learning and adaptation.
- Agent interactions are heterogeneous and can generate network effects. Aggregate flow equations usually assume global homogeneous mixing, but the topology of the interaction network can lead to significant deviations from predicted aggregate behavior.
- Averages will not work. Aggregate differential equations tend to smooth out fluctuations, not ABM, which is important because under certain conditions, fluctuations can be amplified: the system is linearly stable but unstable to larger perturbations.

# Introduction to ABM


## Building Blocks of an ABM 

**Text from the paper by Hammond. [https://www.ncbi.nlm.nih.gov/books/NBK305917/](https://www.ncbi.nlm.nih.gov/books/NBK305917/)** 
Hammond, R. A. (2015). Considerations and best practices in agent-based modeling to inform policy. In *Assessing the use of agent-based models for tobacco regulation*. National Academies Press (US).

***Properties*** are characteristics of individual agents (such as sex, age, disease state, wealth, and body mass index). An agent property can be:

- *Mutable or immutable over time* (within the simulation). This is a design choice: a model focusing on a single school year might treat age as immutable, whereas allowing age to change within the simulation might be central to models considering the lifecourse or overlapping generations (Axtell et al., 2002).
- *Observable, partially observable, or unobservable to other agents.* A simulation of farm behavior might treat size in acres as observable to other farms, but income as only partially observable (Brown et al., 2005a; Brown et al., 2005b; Happe et al., 2006; Magliocca et al., 2014; Sun et al., 2014). In a model of tobacco use, agents may be able to observe numerous cues that suggest whether another agent is a current smoker or not, but previous smoking history is likely harder to observe.
- *Stored in a variety of data structures, from simple booleans to complex lists or arrays.* A dichotomous variable can be easily stored in a simple data structure. Storing the mapping between food types and associated reward values (Hammond et al., 2012) or agents’ preferences for other types of choices (Kollman et al., 1992, 1997; Maroulis et al., 2014) might require a more complex data structure, such as a hash table or vector.

Not all types of agents represented in a model need to have all properties; for example, the property “market capitalization” is relevant for agents that represent firms but not for agents that represent employees of the firms. All properties must have well-defined conditions for initialization and for change through time. Initialization can involve draws from predefined distributions or from data and may be conditional on values assigned to other properties. By representing each individual actor as a separate software object, ABM allows enormous flexibility to capture heterogeneity across agents in their properties (see section 1.2).

***Actions*** define the repertoire of specific behaviors that agents can perform within the simulation, such as moving around the environment, eating food, smoking tobacco, communicating information to a neighbor, forming a friendship tie, or buying a product. Agent actions can:

- *Change an agent’s own Properties*. For example, taking the action “eat” may affect the property “body mass index” over time (Hammond and Ornstein, 2014); taking the action “buy cigarettes” will immediately affect the property “inventory of cigarettes” (Luke et al., 2014).
- *Change the Properties of other agents*. For example, models of cooperation and reciprocity often contain an action “donate (to agent x)” which increases a wealth or wellbeing property of agent x while decreasing the same property for the actor (Axelrod et al., 2004; Hammond and Axelrod, 2006a; Hammond and Axelrod, 2006b; Nowak, 2006).
- *Change the Environment*. In models of land use and commons, for example, exploitation of a resource by one agent may reduce the amount of resource available at that location in the environment (temporarily or permanently) to other agents.
- *Change an agent’s own Rules,* for example through learning.

For every action included for any agent in an ABM, the modeler must define conditions under which the action is triggered or may be performed. Each action must also have defined consequences (which may include one or more of the changes above); actions that have no consequences do not affect simulation dynamics and do not belong in the model.

***Rules*** are the central drivers of model dynamics, defining how agents choose an action, update properties, and interact with each other and their environment. Rules in an ABM can:

- *Take as an input the current or past value of Properties (*an agent’s own, those of others, or those of the environment); for example, “if age > 18, purchase tobacco.”
- *Be dependent in some way on Time*, and may involve learning or adaptation—for example, image scoring in reputation models, or the process of preference formation (Hammond et al., 2012; Nowak, 2006).
- *Vary enormously in complexity* from simple heuristics (for example, “when reaching any four-way intersection, always turn left”) to detailed internal models or calculations (for example, agents who collect data about the simulated world and optimize over some objective function).
- *Cause not only modification of agents but creation or removal of agents*, for example, creation of offspring in a demographic model or killing of other agents in a model of genocide (Bhavnani and Miodownik, 2009; Epstein, 2002).
- *Involve stochastic probability*, for example, “when reaching any four-way intersection, turn left with probability 50 percent.”

***Time*** is central to a dynamic simulation model. Agent-based models (and other related simulation models) generally have a single, lowest-level fundamental unit of time that represents one pass by the computer through the set of instructions that embody the simulation. This is sometimes referred to as an “iteration,” a “tick,” or a “round.” Time in an ABM:

- *Can remain abstract or can be calibrated to real-world time* with additional design work. Such calibration may be easier for some models than for others, depending in part on whether behaviors in the model occur on known time scales. A model in which an agent’s age in years changes every 12 iterations or in which agents travel back and forth between home and office every other iteration is relatively easy to calibrate to calendar time (Luke et al., 2014). A model of chronic disease incidence driven by smoking or a model of opinion-change dynamics may require more work to calibrate (Garcia and Jager, 2011).
- *Can involve multiple distinct “speeds” at which change occurs*, for example, the speed with which a virus spreads through social contact versus the speed with which the virus itself evolves.
- *Is the unit in which rules, action, and changes in agent properties or environment are defined.*
- *May also shape the simulation results through decisions about the order in which instructions are followed by the computer.* For example, some types of diffusion models start with a single agent that deviates from the population and calculate the likelihood that the deviation will spread through the population. The choice between two implementations of diffusion—one in which the early adopter influences others before being influenced by its own neighbors and one in which the two directions of influence are evaluated in the reverse order—can result in very different outcomes, such as whether the deviation persists or dies out. A deterministic agent activation order could mistakenly lock the model into one of those outcomes (see section 4.3).

***Environment*** provides the context for agents and their interactions in the model. The flexibility to represent many different types of environment effectively is a major strength of ABM (see section 1.2). The Environment in an ABM can:

- *Range from simple and relatively abstract geometries* (e.g., a lattice, ring, or torus) *to highly complex ones* (often empirically informed) such as a GIS shape file or a network structure.
- *Contain “agent types” itself, with their own properties, actions, and rules.* For example, a model of subsistence agriculture may contain rules for crop regeneration at any particular environmental location that are dependent on farming and harvest practices as well as intrinsic soil and water conditions (see Axtell et al., 2002).
- *Can change over time, endogenously* (as a result of such agent actions as crop rotation) or *exogenously* (for example, as a result of a policy change or external shock).


> ## References from the paper by Hammond
> - Axtell RL, Epstein JM, Dean JS, Gumerman GJ, Swedlund AC, Harburger J, Chakravarty S, Hammond R, Parker J, Parker M. Population growth and collapse in a multiagent model of the Kayenta Anasazi in Long House Valley. Proceedings of the National Academy of Sciences of the United States of America. 2002;99(Suppl 3):7275–7279.
> - Brown DG, Riolo R, Robinson DT, North M, Rand W. Spatial process and data models: Toward integration of agent-based models and GIS. Journal of Geographical Systems. 2005b;7(1):25–47.
> - Happe K, Kellermann K, Balmann A. Agent-based analysis of agricultural policies: An illustration of the agricultural policy simulator Agripolis, its adaptation and behavior. Ecology and Society. 2006;11(1):49.
> - Magliocca NR, Brown DG, Ellis EC. Cross-site comparison of land-use decision-making and its consequences across land systems with a generalized agent-based model. PLoS ONE. 2014;9(1):e86179.
> - Sun S, Parker DC, Huang Q, Filatova T, Robinson DT, Riolo RL, Hutchins M, Brown DG. Market impacts on land-use change: An agent-based experiment. Annals of the Association of American Geographers. 2014;104(3):460–484.
> - Hammond RA, Ornstein JT, Fellows LK, Dube L, Levitan R, Dagher A. A model of food reward learning with dynamic reward exposure. Frontiers in Computational Neuroscience. 2012;6(82):1–8.
> - Kollman K, Miller JH, Page SE. Adaptive parties in spatial elections. American Political Science Review. 1992;86(4):929–937.
> - Kollman K, Miller JH, Page SE. Political institutions and sorting in a Tiebout model. The American Economic Review. 1997;87:977–992.
> - Maroulis S, Bakshy E, Gomez L, Wilensky U. Modeling the transition to public school choice. Journal of Artificial Societies and Social Simulation. 2014;17(2):3.
> - Hammond RA, Ornstein JT. A model of social influence on body mass index. Annals of the New York Academy of Sciences. 2014;1331:34–42.
> - Luke DA, Sorg AA, Mack-Crane A, Hammond RA, Kasman ME, Ribisl KM, Henriksen L. “Tobacco Town: Modeling the effects of tobacco retail reduction.”. State and Community Tobacco Control Initiative, National Cancer Institute; Chicago, IL: 2014. (Poster presentation at Annual Investigators Meeting).
> - Axelrod R, Hammond RA, Grafen A. Altruism via kin-selection strategies that rely on arbitrary tags with which they coevolve. Evolution. 2004;58(8):1833–1838.
> - Hammond RA, Axelrod R. Evolution of contingent altruism when cooperation is expensive. Theoretical Population Biology. 2006a;69(3):333–338.
> - Hammond RA, Axelrod R. The evolution of ethnocentrism. Journal of Conflict Resolution. 2006b;50(6):926–936.
> - Nowak MA. Five rules for the evolution of cooperation. Science. 2006;314(5805):1560–1563. 
> - Bhavnani R, Miodownik D. Ethnic polarization, ethnic salience, and civil war. Journal of Conflict Resolution. 2009;53(1):30–49.
> - Epstein JM. Modeling civil violence: An agent-based computational approach. Proceedings of the National Academy of Sciences of the United States of America. 2002;99(Suppl 3):7243–7250.
> - Luke DA, Sorg AA, Mack-Crane A, Hammond RA, Kasman ME, Ribisl KM, Henriksen L. “Tobacco Town: Modeling the effects of tobacco retail reduction.”. State and Community Tobacco Control Initiative, National Cancer Institute; Chicago, IL: 2014. (Poster presentation at Annual Investigators Meeting).
> - Garcia R, Jager W. From the special issue editors: Agent-based modeling of innovation diffusion. Journal of Product Innovation Management. 2011;28(2):148–151.
{: .solution}


## Architecture of an ABM

**Text from the paper by Zhang et al. [https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9527397&tag=1](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9527397&tag=1)** 
Zhang, W., Valencia, A., & Chang, N. B. (2021). Synergistic integration between machine learning and agent-based modeling: A multidisciplinary review. *IEEE Transactions on Neural Networks and Learning Systems*.

The microlevel ABM consists of a number of agents. The top-level exhibits the emergence (aggregated behavior characteristics) as the macrolevel in this context. The overall macrolevel system is also sometimes identified as a multiple-agent-system (MAS) since it is comprised of multiple microlevel agents. For example, Le et al. [47] used a land-use dynamic simulator—a MAS model, to assess the socioecological consequences of possible land-use policies based on an ABM approach. Su et al. [48] on the other hand, demonstrated the effectiveness of a selftriggered mechanism for saturated system controller design in a state feedback system for achieving consensus for a MAS, which can be treated like the ABM in the control domain. Even though the term MAS is sometimes used as a synonym for ABM in these research papers, it is more frequently used in the computing domain, such as in computer science and engineering correlated areas. When studying the emergence behavior characteristics of agents, the terms ABM and IBM are more common. 

# Case Study 1 - Hotelling's Law

**Text from the NetLogo Model Library on Hoetlling's Law: [https://ccl.northwestern.edu/netlogo/models/Hotelling'sLaw](https://ccl.northwestern.edu/netlogo/models/Hotelling'sLaw)**


**WHAT IS IT?**
This model is a representation of Hotelling's law (1929), which examines the optimal placement of stores and pricing of their goods in order to maximize profit. In Hotelling's original paper, the stores were confined to a single dimension. This model replicates and extends Hotelling's law, by allowing the stores to move freely on a plane.

In this model, several stores attempt to maximize their profits by moving and changing their prices. Each consumer chooses their store of preference based on the distance to the store and the price of the goods it offers.

**HOW IT WORKS**
Each consumer adds up the price and distance from each store, and then chooses to go to the store that offers the lowest sum. In the event of a tie, the consumer chooses randomly. The stores can either be constrained to one dimension, in which case all stores operate on a line, or they can be placed on a plane. Under the normal rule, each store tries to move randomly in the four cardinal directions to see if it can gain a larger market share; if not, it does not move. Then each store checks if it can earn a greater profit by increasing or decreasing the price of their goods; if not, it does not change the price. This decision is made without any knowledge of their competitors' strategies. There are two other conditions under which one can run this model: stores can either only change prices, or only move their location.

**HOW TO USE IT**
Press SETUP to create the stores and a visualization of their starting market share areas. Press GO to have the model run continuously. Press GO-ONCE to have the model run once. The NUMBER-OF-STORES slider decides how many stores are in the world.

If the LAYOUT chooser is on LINE, then the stores will operate only on one dimension. If it is on PLANE, then the stores will operate in a two dimensional space.

If the RULES chooser is on PRICING-ONLY, then stores can only change their price. If it is on MOVING-ONLY, then the stores can only move. If it is on NORMAL, all stores can change their prices and move.

**THINGS TO NOTICE**
On the default settings, notice that the two stores end up in very close contact and with minimal prices. This is because each store tries to cut into their competitor's fringe consumers by moving closer and reducing their prices.

Also notice how the shapes of the boundaries end up as perpendicular bisectors or hyperbolic arcs. The distance between the stores and their difference in prices determines the eccentricity of these arcs.

Try increasing the store number to three or more, and notice how the store with the most area is not necessarily the most profitable.

Plots show the prices, areas, and revenues of all stores.

# Case Study 2 - epiDEM Basic

**Text from the NetLogo Model Library on epiDEM Basic: [https://ccl.northwestern.edu/netlogo/models/epiDEMBasic](https://ccl.northwestern.edu/netlogo/models/epiDEMBasic)**

**WHAT IS IT?**
This model simulates the spread of an infectious disease in a closed population. It is an introductory model in the curricular unit called epiDEM (Epidemiology: Understanding Disease Dynamics and Emergence through Modeling). This particular model is formulated based on a mathematical model that describes the systemic dynamics of a phenomenon that emerges when one infected person is introduced in a wholly susceptible population. This basic model, in mathematical epidemiology, is known as the Kermack-McKendrick model.

The Kermack-McKendrick model assumes a closed population, meaning there are no births, deaths, or travel into or out of the population. It also assumes that there is homogeneous mixing, in that each person in the world has the same chance of interacting with any other person within the world. In terms of the virus, the model assumes that there are no latent or dormant periods, nor a chance of viral mutation.

Because this model is so simplistic in nature, it facilitates mathematical analyses and also the calculation of the threshold at which an epidemic is expected to occur. We call this the reproduction number, and denote it as R_0. Simply, R_0 stands for the number of secondary infections that arise as a result of introducing one infected person in a wholly susceptible population, over the course of the infected person's contagious period (i.e. while the person is infective, which, in this model, is from the beginning of infection until recovery).

This model incorporates all of the above assumptions, but each individual has a 5% chance of being initialized as infected. This model shows the disease spread as a phenomenon with an element of stochasticity. Small perturbations in the parameters included here can in fact lead to different final outcomes.

Overall, this model helps users 1) engage in a new way of viewing/modeling epidemics that is more personable and relatable 2) understand how the reproduction number, R_0, represents the threshold for an epidemic 3) think about different ways to calculate R_0, and the strengths and weaknesses in each approach 4) understand the relationship between derivatives and integrals, represented simply as rates and cumulative number of cases, and 5) provide opportunities to extend or change the model to include some properties of a disease that interest users the most.

**HOW IT WORKS**
Individuals wander around the world in random motion. Upon coming into contact with an infected person, by being in any of the eight surrounding neighbors of the infected person or in the same location, an uninfected individual has a chance of contracting the illness. The user sets the number of people in the world, as well as the probability of contracting the disease.

An infected person has a probability of recovering after reaching their recovery time period, which is also set by the user. The recovery time of each individual is determined by pulling from an approximately normal distribution with a mean of the average recovery time set by the user.

The colors of the individuals indicate the state of their health. Three colors are used: white individuals are uninfected, red individuals are infected, green individuals are recovered. Once recovered, the individual is permanently immune to the virus.

The graph INFECTION AND RECOVERY RATES shows the rate of change of the cumulative infected and recovered in the population. It tracks the average number of secondary infections and recoveries per tick. The reproduction number is calculated under different assumptions than those of the Kermack McKendrick model, as we allow for more than one infected individual in the population, and introduce aforementioned variables.

At the end of the simulation, the R_0 reflects the estimate of the reproduction number, the final size relation that indicates whether there will be (or there was, in the model sense) an epidemic. This again closely follows the mathematical derivation that R_0 = beta*S(0)/ gamma = N*ln(S(0) / S(t)) / (N - S(t)), where N is the total population, S(0) is the initial number of susceptibles, and S(t) is the total number of susceptibles at time t. In this model, the R_0 estimate is the number of secondary infections that arise for an average infected individual over the course of the person's infected period.

**HOW TO USE IT**
The SETUP button creates individuals according to the parameter values chosen by the user. Each individual has a 5% chance of being initialized as infected. Once the model has been setup, push the GO button to run the model. GO starts the model and runs it continuously until GO is pushed again.

Note that in this model each time-step can be considered to be in hours, although any suitable time unit will do.

What follows is a summary of the sliders in the model.

INITIAL-PEOPLE (initialized to vary between 50 - 400): The total number of individuals in the simulation, determined by the user. INFECTION-CHANCE (10 - 100): Probability of disease transmission from one individual to another. RECOVERY-CHANCE (10 - 100): Probability of an infected individual to recover once the infection has lasted longer than the person's recovery time. AVERAGE-RECOVERY-TIME (50 - 300): The time it takes for an individual to recover on average. The actual individual's recovery time is pulled from a normal distribution centered around the AVERAGE-RECOVERY-TIME at its mean, with a standard deviation of a quarter of the AVERAGE-RECOVERY-TIME. Each time-step can be considered to be in hours, although any suitable time unit will do.

A number of graphs are also plotted in this model.

CUMULATIVE INFECTED AND RECOVERED: This plots the total percentage of infected and recovered individuals over the course of the disease spread. POPULATIONS: This plots the total number of people with or without the flu over time. INFECTION AND RECOVERY RATES: This plots the estimated rates at which the disease is spreading. BetaN is the rate at which the cumulative infected changes, and Gamma rate at which the cumulative recovered changes. R_0: This is an estimate of the reproduction number, only comparable to the Kermack McKendrick's definition if the initial number of infected were 1.

**THINGS TO NOTICE**
As with many epidemiological models, the number of people becoming infected over time, in the event of an epidemic, traces out an "S-curve." It is called an S-curve because it is shaped like a sideways S. By changing the values of the parameters using the slider, try to see what kinds of changes make the S curve stretch or shrink.

Whenever there's a spread of the disease that reaches most of the population, we say that there was an epidemic. As mentioned before, the reproduction number indicates the number of secondary infections that arise as a result of introducing one infected person in a totally susceptible population, over the course of the infected person's contagious period (i.e. while the person is infected). If it is greater than 1, an epidemic occurs. If it is less than 1, then it is likely that the disease spread will stop short, and we call this an endemic.


{% include links.md %}
