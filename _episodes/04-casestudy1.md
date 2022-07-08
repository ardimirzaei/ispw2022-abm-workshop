---
title: "Case Study 1: Hotelling’s Law for Pharmacy Location and Pricing Strategy"
teaching: 5
exercises: 15
questions:
- "How does preventing pharmacy movement affect price?"
objectives:
- "Conduct a simple experiment using an ABM keypoints"
keypoints:
- "Multi-agent behaviour in pharmacy is a complex system which may be modelled using ABM"
- "How multiple pharmacies interact within a market can be modelled as a complex system"
- "Adjustable inputs are geographic location and pricing strategy"
---

# Hotelling’s Law

Hotelling’s Law is an economic obersvation that producers in a market will make their products or services similar to other producers. That is, there is minimum differention between to producers. This observation is the opposite of product differentiation. Product differentiation is a common marketing process to distinguish a product or service from your competitiors. 

> ## Example of Hotelling's Law
> The common example of Hotelling's Law is two stores on the same street competing for consumers. Let's look at the example of fast food restaurants such as in [this article](https://mindyourdecisions.com/blog/2012/10/23/why-are-mcdonalds-and-burger-king-usually-located-near-each-other-fast-food-location-game-theory/) by [Presh Talwakar](https://mindyourdecisions.com/blog/).
> 
> Thinks of two fast food restaurants in an area on the same street. They are placed at the end of street, one on the northend and the other on the southend. Theoretically, the area they are accessible to is up until the middle of the street. Assuming consumers are going to go the restaurant closest and their is an even distribution, both restaurants cover half the market at this point. However, if one restaurant move closer to the middle of the street, then they will cover more of the market as they are closer to more customers. In doing so, the other restaurant will move closer to the middle, as as they can enusre that the opposing restaurant doesn't take from their market share. In doing so, both restaurants end up in the middle. Socially, it is better to be positioned in an accessible location for all consumers to have access to a product. However, in market competition, it is more favourable to go where the majority of consumers are and which is not always the socially equitable position. 
> 
> Another example is [ice cream vendors](https://www.planetizen.com/node/65765).
{: .solution}

# Applications to Pharmacy

- Consider marketing in pharmacy
- Different pharmcies have a different look and feel
- Hotelling's law is that in a economic market segment that often it pays to look very similar. 


<figure>
  <img src="{{ page.root }}/fig/pharmacy_brands_aus.png" style="margin:10px;width:600px"/>
</figure><br>
<figure>
  <img src="{{ page.root }}/fig/pharmacy_brands_uk.png" style="margin:10px;width:600px"/>
</figure><br>
<figure>
  <img src="{{ page.root }}/fig/pharmacy_brands_us.jpg" style="margin:10px;width:600px"/>
  <figcaption> Pharmacy Brands. Images sourced from Google Images.</figcaption>
</figure><br>

# NetLogo Model

Each consumer adds up the price and distance from each store, and then chooses to go to the store that offers the lowest sum. In the event of a tie, the consumer chooses randomly. The stores can either be constrained to one dimension, in which case all stores operate on a line, or they can be placed on a plane. Under the normal rule, each store tries to move randomly in the four cardinal directions to see if it can gain a larger market share; if not, it does not move. Then each store checks if it can earn a greater profit by increasing or decreasing the price of their goods; if not, it does not change the price. This decision is made without any knowledge of their competitors' strategies. There are two other conditions under which one can run this model: stores can either only change prices, or only move their location.


[Run application on the Web](http://www.netlogoweb.org/launch#http://ccl.northwestern.edu/netlogo/models/models/Sample%20Models/Social%20Science/Economics/Hotelling's%20Law.nlogo)

*Alternative, if you are still in the web appilication, search for the model:* ***Hotelling's Law*** *in Model Library*

> ## Activities
> 
> - Play around and adjust the input paramaters. 
>	- Set initial conditions of the number of stores
>	- Modify the strategy
>	- Change the plane
>	- Look at the outputs
>	- *What do you notice?*
> - When comfortable explore the scenario questions
>
> > ## Scenarios
> > 
> > **Scenario 1:** We cannot change the price of a prescription (Regulated prescription pricing)
> >
> > **Scenario 2:** We cannot move our pharmacy from its current location (Australian pharmacy location rules)
> >
> {: .solution}
> 
 
{: .challenge}

> ## Group discussion
> - For these scenarios how is revenue affected?
>
> - Speculate what would happen if they were free to move and free to set their prices.
>
{: .discussion}


# Further reading

- [CVS and Walgreens](https://www.startribune.com/nation-s-biggest-pharmacies-sidle-right-up-to-each-other/176188911/)