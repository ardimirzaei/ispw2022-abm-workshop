---
title: "Instructor Notes"
---

# Why is an ABM useful for Emergent Phenomna

One may want to use ABM when there is potential for emergent phenomena, i.e., when:
- Individual behavior is nonlinear and can be characterized by thresholds, if-then rules, or nonlinear coupling. Describing discontinuity in individual behavior is difficult with differential equations.
- Individual behavior exhibits memory, path-dependence, and hysteresis, non-markovian behavior, or temporal correlations, including learning and adaptation.
- Agent interactions are heterogeneous and can generate network effects. Aggregate flow equations usually assume global homogeneous mixing, but the topology of the interaction network can lead to significant deviations from predicted aggregate behavior.
- Averages will not work. Aggregate differential equations tend to smooth out fluctuations, not ABM, which is important because under certain conditions, fluctuations can be amplified: the system is linearly stable but unstable to larger perturbations.

# Episode 2


## Building Blocks of an ABM

Properties are characteristics of individual agents (such as sex, age, disease state, wealth, and body mass index). An agent property can be:

Mutable or immutable over time (within the simulation). This is a design choice: a model focusing on a single school year might treat age as immutable, whereas allowing age to change within the simulation might be central to models considering the lifecourse or overlapping generations (Axtell et al., 2002).
Observable, partially observable, or unobservable to other agents. A simulation of farm behavior might treat size in acres as observable to other farms, but income as only partially observable (Brown et al., 2005a; Brown et al., 2005b; Happe et al., 2006; Magliocca et al., 2014; Sun et al., 2014). In a model of tobacco use, agents may be able to observe numerous cues that suggest whether another agent is a current smoker or not, but previous smoking history is likely harder to observe.
Stored in a variety of data structures, from simple booleans to complex lists or arrays. A dichotomous variable can be easily stored in a simple data structure. Storing the mapping between food types and associated reward values (Hammond et al., 2012) or agents’ preferences for other types of choices (Kollman et al., 1992, 1997; Maroulis et al., 2014) might require a more complex data structure, such as a hash table or vector.
Not all types of agents represented in a model need to have all properties; for example, the property “market capitalization” is relevant for agents that represent firms but not for agents that represent employees of the firms. All properties must have well-defined conditions for initialization and for change through time. Initialization can involve draws from predefined distributions or from data and may be conditional on values assigned to other properties. By representing each individual actor as a separate software object, ABM allows enormous flexibility to capture heterogeneity across agents in their properties (see section 1.2).

Actions define the repertoire of specific behaviors that agents can perform within the simulation, such as moving around the environment, eating food, smoking tobacco, communicating information to a neighbor, forming a friendship tie, or buying a product. Agent actions can:

Change an agent’s own Properties. For example, taking the action “eat” may affect the property “body mass index” over time (Hammond and Ornstein, 2014); taking the action “buy cigarettes” will immediately affect the property “inventory of cigarettes” (Luke et al., 2014).
Change the Properties of other agents. For example, models of cooperation and reciprocity often contain an action “donate (to agent x)” which increases a wealth or wellbeing property of agent x while decreasing the same property for the actor (Axelrod et al., 2004; Hammond and Axelrod, 2006a; Hammond and Axelrod, 2006b; Nowak, 2006).
Change the Environment. In models of land use and commons, for example, exploitation of a resource by one agent may reduce the amount of resource available at that location in the environment (temporarily or permanently) to other agents.
Change an agent’s own Rules, for example through learning.
For every action included for any agent in an ABM, the modeler must define conditions under which the action is triggered or may be performed. Each action must also have defined consequences (which may include one or more of the changes above); actions that have no consequences do not affect simulation dynamics and do not belong in the model.

Rules are the central drivers of model dynamics, defining how agents choose an action, update properties, and interact with each other and their environment. Rules in an ABM can:

Take as an input the current or past value of Properties (an agent’s own, those of others, or those of the environment); for example, “if age > 18, purchase tobacco.”
Be dependent in some way on Time, and may involve learning or adaptation—for example, image scoring in reputation models, or the process of preference formation (Hammond et al., 2012; Nowak, 2006).
Vary enormously in complexity from simple heuristics (for example, “when reaching any four-way intersection, always turn left”) to detailed internal models or calculations (for example, agents who collect data about the simulated world and optimize over some objective function).
Cause not only modification of agents but creation or removal of agents, for example, creation of offspring in a demographic model or killing of other agents in a model of genocide (Bhavnani and Miodownik, 2009; Epstein, 2002).
Involve stochastic probability, for example, “when reaching any four-way intersection, turn left with probability 50 percent.”
Time is central to a dynamic simulation model. Agent-based models (and other related simulation models) generally have a single, lowest-level fundamental unit of time that represents one pass by the computer through the set of instructions that embody the simulation. This is sometimes referred to as an “iteration,” a “tick,” or a “round.” Time in an ABM:

Can remain abstract or can be calibrated to real-world time with additional design work. Such calibration may be easier for some models than for others, depending in part on whether behaviors in the model occur on known time scales. A model in which an agent’s age in years changes every 12 iterations or in which agents travel back and forth between home and office every other iteration is relatively easy to calibrate to calendar time (Luke et al., 2014). A model of chronic disease incidence driven by smoking or a model of opinion-change dynamics may require more work to calibrate (Garcia and Jager, 2011).
Can involve multiple distinct “speeds” at which change occurs, for example, the speed with which a virus spreads through social contact versus the speed with which the virus itself evolves.
Is the unit in which rules, action, and changes in agent properties or environment are defined.
May also shape the simulation results through decisions about the order in which instructions are followed by the computer. For example, some types of diffusion models start with a single agent that deviates from the population and calculate the likelihood that the deviation will spread through the population. The choice between two implementations of diffusion—one in which the early adopter influences others before being influenced by its own neighbors and one in which the two directions of influence are evaluated in the reverse order—can result in very different outcomes, such as whether the deviation persists or dies out. A deterministic agent activation order could mistakenly lock the model into one of those outcomes (see section 4.3).
Environment provides the context for agents and their interactions in the model. The flexibility to represent many different types of environment effectively is a major strength of ABM (see section 1.2). The Environment in an ABM can:

Range from simple and relatively abstract geometries (e.g., a lattice, ring, or torus) to highly complex ones (often empirically informed) such as a GIS shape file or a network structure.
Contain “agent types” itself, with their own properties, actions, and rules. For example, a model of subsistence agriculture may contain rules for crop regeneration at any particular environmental location that are dependent on farming and harvest practices as well as intrinsic soil and water conditions (see Axtell et al., 2002).
Can change over time, endogenously (as a result of such agent actions as crop rotation) or exogenously (for example, as a result of a policy change or external shock).

## Architecture of an ABM



# Hotelling's Law

## WHAT IS IT?
This model is a representation of Hotelling's law (1929), which examines the optimal placement of stores and pricing of their goods in order to maximize profit. In Hotelling's original paper, the stores were confined to a single dimension. This model replicates and extends Hotelling's law, by allowing the stores to move freely on a plane.

In this model, several stores attempt to maximize their profits by moving and changing their prices. Each consumer chooses their store of preference based on the distance to the store and the price of the goods it offers.

## HOW IT WORKS
Each consumer adds up the price and distance from each store, and then chooses to go to the store that offers the lowest sum. In the event of a tie, the consumer chooses randomly. The stores can either be constrained to one dimension, in which case all stores operate on a line, or they can be placed on a plane. Under the normal rule, each store tries to move randomly in the four cardinal directions to see if it can gain a larger market share; if not, it does not move. Then each store checks if it can earn a greater profit by increasing or decreasing the price of their goods; if not, it does not change the price. This decision is made without any knowledge of their competitors' strategies. There are two other conditions under which one can run this model: stores can either only change prices, or only move their location.

## HOW TO USE IT
Press SETUP to create the stores and a visualization of their starting market share areas. Press GO to have the model run continuously. Press GO-ONCE to have the model run once. The NUMBER-OF-STORES slider decides how many stores are in the world.

If the LAYOUT chooser is on LINE, then the stores will operate only on one dimension. If it is on PLANE, then the stores will operate in a two dimensional space.

If the RULES chooser is on PRICING-ONLY, then stores can only change their price. If it is on MOVING-ONLY, then the stores can only move. If it is on NORMAL, all stores can change their prices and move.

## THINGS TO NOTICE
On the default settings, notice that the two stores end up in very close contact and with minimal prices. This is because each store tries to cut into their competitor's fringe consumers by moving closer and reducing their prices.

Also notice how the shapes of the boundaries end up as perpendicular bisectors or hyperbolic arcs. The distance between the stores and their difference in prices determines the eccentricity of these arcs.

Try increasing the store number to three or more, and notice how the store with the most area is not necessarily the most profitable.

Plots show the prices, areas, and revenues of all stores.

{% include links.md %}
