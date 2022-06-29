---
title: "Instructor Notes"
---
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
