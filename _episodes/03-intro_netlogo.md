---
title: "Introduction to NetLogo "
teaching: 5
exercises: 5
questions:
- "What are the different tools used to build ABMs"
objectives:
- "Increased awareness of the tools used to build ABMs "

keypoints:
- "NetLogo is simple to use, well supported, and a great starting point  for agent-based modelling"
- "NetLogo simulations need to be 'setup', then they 'go'"
- "Ticks can be an arbitary unit of time"
- "Plots, graphs, numbers can be used to output the results of your model"
- "Can run multiple simulations using the NetLogo BehaviourSpace feature"

---

# NetLogo

<figure>
  <img src="{{ page.root }}/fig/Netlogo-ui.png" style="margin:10px;width:600px"/>
  <figcaption> Example View of the Netlogo Application</figcaption>
</figure><br>


# Why NetLogo?

- Simple to use
- Great to start creating models
- Community of help (*Google is your best friend*)
  - [Help Page](https://ccl.northwestern.edu/netlogo/help.shtml)
  - [Google Group](https://groups.google.com/g/netlogo-users?pli=1)
  - [Stack Overflow](https://stackoverflow.com/questions/tagged/netlogo)
- Cross-platform
- Large Model Library

<br>

> ## Let's go through the wolf and sheep example
> 
> [Sheep and Wolf Predation](http://www.netlogoweb.org/launch#http://ccl.northwestern.edu/netlogo/models/models/Sample%20Models/Biology/Wolf%20Sheep%20Predation.nlogo)
>
> - What do the sliders do
> - Setup model and go
> - Adjust the speed of the model using the model speed (What are ticks?)
> - Use the sliders to set conditions, the number of agents, their behaviour, their interactions, their external environment. 
> - Thought experiment: what type of conditions do we want to set (drought conditions, fertile fields... )
> - See how they interact and they change, but how do we express the output. 
> - Run model with 3 agents (change model-version to *sheep-wolves-grass*)
{: .challenge}


<br>

# Programming Languages

- NetLogo (based on Scala)
- Python
- Java
- C
- R

<br>

>## What software might help you?
>
>
>| Platform | Primary Domain | Supporting Organization | Operating System | GIS Capabilities | 3D Capabilities | User Support | License | Programming Language | 
>| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | 
>| Adaptive Modeler | Building agent-based market simulation models for price forecasting of real-world stocks and other securities | Altreva; Utrecht, Netherlands | Windows | Unknown | Yes Up to 3 agent properties can be visualized in real-time using 2D graphics and color | FAQ, documentation, tutorial, examples, forum, email support | Proprietary; free evaluation version available for research and experimentation (some limitations but no expiration) | No programming skills required. An adaptive form of genetic programming is used to create trading rules. Users can select functions to be used in the genetic programming engine. | 
>| AnyLogic | Agent-based general purpose; also supports discrete event and system dynamics simulations. | The AnyLogic Company; Oakbrook Terrace, Illinois, USA | Linux, macOS, Windows | Yes: supports both tile maps from free online providers and shapefile-based maps | Yes | Demos; training; online community; ask a question; online help; tutorials; consulting services | Proprietary; Free Personal Learning Edition available | Java | 
>| Cougaar | Multi-agent systems; highly distributed, scalable, reliable, survivable applications; Domain independent; large scale distributed, complex, data intensive (can be configured for small-scaled embedded applications) | Cougaar Software Inc.; Vienna, Virginia, USA]. | Linux, macOS, Windows | Yes Integrated with OpenMap | No | FAQ; tutorials; slide shows; documentation; selected references; email support; public forums; mailing lists | Cougaar Open Source License (COSL) is a modified version of the OSI approved BSD License | Java | 
>| Framsticks | 2D/3D simulations of (evolving) multi-agent systems and artificial life | Poznan University of Technology, Poznan, Poland | Cross-platform | Yes | Yes | Email developer; tutorials; manual; FAQ; forums; API; documentation; selected publications; examples | Depends on module: GPL/LGPL/Propertiary | FramScript (similar to JavaScript) | 
>| GAMA Platform | Modeling and simulation development environment for building spatially explicit agent-based simulations. | IRD/SU international research unit UMMISCO, France | Windows; Linux; *nix; Mac OS X | Yes | Yes | tutorials; manual; FAQ; forums; documentation; selected publications; examples | GPL v3.0 | GAML (GAma Modeling Language) for simulations, Java for extensions | 
>| JADE | Distributed applications composed of autonomous entities | Telecom Italia; Torino & Parma, Italy | Cross-platform | Unknown | Unknown | FAQ; mailing list; defect list; tutorials; API; documentation | LGPL version 2 | Java | 
>| MASON | General purpose; social complexity, physical modeling, abstract modeling, AI/machine learning | George Mason University, Fairfax, Virginia, USA | Cross-platform | Yes | Yes | Mailing list; documentation; Tutorials; third party extensions; reference papers; API | Academic Free License (open source) | Java | 
>| NetLogo | Social and natural sciences; Help beginning users get started authoring models | Northwestern University, Evanston, Illinois, USA | Cross-platform | Yes | Yes | Documentation; FAQ; selected references; tutorials; third party extensions; defect list; mailing lists | GPL | NetLogo | 
>| Repast | Social sciences | Argonne National Laboratory, University of Chicago; Lemont, Illinois, USA | Cross-platform | Yes | Yes | Documentation; mailing list; defect list; reference papers; external tools; tutorials; FAQ; examples | BSD | Java (RepastS, RepastJ); Python (RepastPy); Visual Basic, .Net, C++, J#, C# (Repast.net) | 
>| SARL | Distributed applications composed of autonomous entities | Stéphane Galland, Burgundy Franche-Comté University, France; Nicolas Gaud, Burgundy Franche-Comté University, France, Sebastian Rodriguez, Advanced Informatics Technology Research Group, Tucuman, Argentina | Cross-platform | Yes By using Java extension libraries, e.g. AFC. | Yes By using Java extension libraries, e.g. Java 3D. | FAQ; mailing list; bug tracker; tutorials; API; documentation | Apache version 2 | SARL, Java | 
>| Soar | General purpose AI; human performance modeling; learning (including explanation-based learning) | John E. Laird, Clare Bates Congdon, Mazin Assanie, Nate Derbinsky and Joseph Xu; Division of Computer Science and Engineering, University of Michigan, Ann Arbor, Michigan, USA | Cross-platform | Unknown | Unknown | Documentation; FAQ; selected publications; defect list; third party extensions; mailing list; contact authors; tutorial; examples; wiki | BSD | Soar 1 to 5 in Lisp; Soar 6 in C; Java, C++, TCL | 
>| StarLogo | Social and natural sciences; Educators; for students to model the behavior of decentralized systems; user friendly for K–12 students | Mitchel Resnick, Eric Klopfer, and others at MIT Media Lab and The MIT Scheller Teacher Education Program, Massachusetts Institute of Technology; Cambridge, MA, USA | Cross-platform | Unknown | Unknown | Mailing list; tutorials; FAQ; bug list; documentation; developer contacts | Free (closed source) – Clearthought Software License, Version 1.0 | StarLogo (an extension of Logo) | 
>| Swarm | General purpose agent based | Swarm Development Group | Cross-platform | Unknown | Unknown | Wiki; tutorials; examples; documentation; FAQ; selected publications; mailing lists | GPL | Java; Objective-C | 
>
>
>This table was shamelessly adapated from [Wikipedia - Comparison of Agent Based Modeling Software](https://en.wikipedia.org/wiki/Comparison_of_agent-based_modeling_software)
{: .solution}
<br>

# References
1. Tisue, S., & Wilensky, U. (2004, May). [Netlogo: A simple environment for modeling complexity](http://ccl.sesp.northwestern.edu/papers/netlogo-iccs2004.pdf). In International conference on complex systems (Vol. 21, pp. 16-21).
2. Thiele, J. C. (2014). [R marries NetLogo: introduction to the RNetLogo package](https://www.jstatsoft.org/index.php/jss/article/view/v058i02/749). Journal of Statistical Software, 58, 1-41.
3. Wilensky, U. (1999). NetLogo (and NetLogo user manual). Center for connected learning and computer-based modeling, Northwestern University. [http://ccl.northwestern.edu/netlogo/docs](https://ccl.northwestern.edu/netlogo/docs/).