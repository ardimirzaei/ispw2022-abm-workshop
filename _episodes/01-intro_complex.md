---
title: "Introduction to complex systems"
teaching: 10
exercises: 0
questions:
- "What is a complex system?"
- "What are the characteristics of a complex system?"
objectives:
- "Identify characteristics of a complex system"
keypoints:
- "SIH is availble to researchers to help them research!"
- "Many ways to make Python go faster."
---


# What is a Complex System?



Complex systems are networks made of a number of components that interact with each other, typically in a nonlinear fashion. Complex systems may arise and evolve through self-organization, such that they are neither completely regular nor completely random, permitting the development of emergent behavior at macroscopic scales. - Sayama



*A Nonlinear System is subject to irreversibility, such that given some change in the inputs to the system, undoing the change does not necessarily return the system to its start, whereas all linear systems are reversible. Furthermore nonlinear systems can be subject to discontinuous or catastrophic state changes, which is not possible in linear systems.*

<figure>
  <!-- <img src="{{ page.root }}/fig/sayama_complex_system.png" style="margin:10px;width:600px"/> -->
  <img src="https://upload.wikimedia.org/wikipedia/commons/d/de/Complex_systems_organizational_map.jpg" style="margin:10px;width:600px"/>
  <figcaption> Topic clusters that constitute complex systems. This image is available in the <a href="https://open.umn.edu/opentextbooks/textbooks/233">book by Sayama</a> and from <a href="https://en.wikipedia.org/wiki/Complex_system">Wikipedia</a>.  </figcaption>
</figure><br>

**Artemis HPC** itself is a multi-million dollar set of equipment, a 'supercomputer', and is the main piece of equipment supported by SIH. However, we also provide a wide range of research services to aid investigators, such as:

* [Training and workshops](https://sydney.edu.au/research/facilities/sydney-informatics-hub/workshops-and-training.html)
* [Project consulting and assisstance](https://sydney.edu.au/research/facilities/sydney-informatics-hub/project-support.html) with Statistics, Data Science, Research Engineering, Bioinformatics, Modeling/Simulation/Visualisation.
* [Research data management](https://sydney.edu.au/research/facilities/sydney-informatics-hub/digital-research-infrastructure.html) consulting and platform support.

We also aim to cultivate a **data community** at USyd, organising monthly [Hacky Hours](https://sydney.edu.au/research/facilities/sydney-informatics-hub/workshops-and-training/hacky-hour.html), outside training events (eg NVIDIA, Pawsey Center), and data/coding-related events. Look out for everthing happening on our [calander](https://www.sydney.edu.au/research/facilities/sydney-informatics-hub/workshops-and-training/training-calendar.html) or contact us (at sih.info@sydney.edu.au) to get some digital collaboration going.

<br>
# Acceleration, Paralleisation, Vectorising, Threading, make-Python-go-fast 

We will cover a few of the ways that you can potentially speed up Python. As we will learn there are multitudes of methods to make Python code more efficient, and also different implentations of libraries, tools, techniques that can all be utilised depending on how your code and/or data is organised. This is a rich and evolving ecosystem and there is no one perfect way to implement efficiencies.

Some key words that might come up:

* Vectorisation
* MPI message parsing interface
* CPU, core, node, thread, process, worker, job, task
* Parallelisation
* Python decorators and functional programming.


<br>
# Course pre-requisites
You should have some experience with Python. You should be able to connect to a remote computer (i.e. Artemis) via ssh and submit a job to a scheduler.


<br>
# What does *parallel* mean?
Seperate workers or processes acting in an independent or semi-dependent manner. Independent processes ship data, program files and libraries to an isloated ecosystem where computation is performed Communication between workers can be achieved. Contrastingly there are also shared memory set ups where multiple computational resources are pooled together to work on the same data. 

Generally speaking parallel workflows fit different categories, which can make you think about how to write your code and what approaches to take.

### Embarrassingly parallel:
Requires no communication between processors. Utilise shared memory spaces.

* running same algorithm for a range of input parameters
* rendering video frames in computer animation
* Open MP implementations.

### Coarse/Fine-grained parallel:
Requires occasional or frequent communication between processors

* Uses a small number of processes on large data. 
* Fine grain uses a large number of small processes with very little communication. Improves computationally bound problems.
* MPI implementations.
* Some examples are finite difference time-stepping on parallel grid, finite element methods.

Traditional implemententations of paralellism  are done on a low level. However, open source software has ***evolved*** dramatically over the last few years allowing more ***high level implementations and concise 'pythonic' syntax*** that wraps around low level tools. The focus on this course is to use these modern high level implementations for use on Artemis.

Let's get started with some examples....


