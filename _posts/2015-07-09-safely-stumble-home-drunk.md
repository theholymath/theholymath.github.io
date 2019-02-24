---
layout: post
title: How to Safely Stumble Home Drunk
categories:
- blog
---

What is the safest way to get from point A to point B? A simple question with a not so simple answer. What does it mean to be safe? Is it the feeling of safety or actually being safe? How are of either of these measured? Most importantly, If I've had too much too drink, what is my safest way home?

We begin to answer these abstract questions in a very tangible environment. Classic 1980's arcade games. I love the 80's.

## Ms. Pac-Man

In 1981 Ms. Pac Man was released forever giving people like me a reason to get out of bed in the morning. ![](/assets/images/ms-pacman-board-245x300.jpg){:style="float: left;margin-left: 7px;margin-right: 7px;margin-top: 7px;"} In the figure to the left, the small yellow boxes are pills Ms. Pac Man eats for points, and the 4 super pills allow Ms. Pac Man to eat the ghosts. The 4 tunnels on the left and right edges, "wrap" the board. For example, if Ms. Pac Man enters the tunnel in the top left she will come out on the top right.

Let's suppose that Ms. Pac Man wants to get from the lower left hand corner to the upper right super pill. In this model we assume the four ghosts emanate some sort of danger that Ms. Pac Man must be aware of. Let's make the following assumptions.

1. The ghosts will not actually kill (eat) Ms. Pac Man, they simply are sources of danger.
2. The danger (ghosts) is static; the ghosts do not move.
3. The effect of each ghosts danger at a point (a,b) is related to the distance between the ghost and the point.
4. Ms. Pac Man can only change course at intersections, or places on the map where she can make a choice to change direction at a 90 degree angle.

This simplified version of the game is a basis for a mathematical model. This mimics the problem of a person walking from an intersection A to an intersection B. Assume we have historic crime data we can give a prediction, of sorts, of the amount of danger on a given path. **Solving the Ms. Pac Man problem is the beginning of solving the safe path problem in a real-world city scenario**. The shortest path problem has a long history. Because of computing power we can now apply these algorithms to larger and more complex graphs. An example was tackled in a paper ([here](http://www2.cs.uic.edu/~urbcomp2013/urbcomp2014/papers/Galbrun_Safe%20Navigation.pdf)) and my application to Ms. Pac Man is yet another variation.

# The Model

We can model the Ms. Pac Man board as a graph. A graph, denoted by $$G$$, is a collection of vertices or nodes, denoted with a $$V$$, and a collection of edges that connect the nodes denoted by $$E$$. We use the notation $$G=(V,E)$$. Every intersection cited in bullet point 4 above is a vertex and every path between intersections is an edge.

Using the schematic described above we can label the vertices as the ordered pair (a,b). The intersection at the lower left is then vertex (1,1). We impose a 26x26 grid that corresponds with the pills on the board and in doing so we now have a and b are both integers. Using this model we have the following network representation of the board.


![](/assets/images/MsPac_Board-620x629.png)

## Solving the Problem: Dijkstra's Algorithm

Now that we have our model we want to solve the graph. We have many nodes and many edges and so computing the graph by hand becomes laborious. We enlist our friend Python to do the heavy lifting. An algorithm exists that will solve the graph. But first we need to decide how we measure the danger from the ghosts.

### A Kernel Density Estimate for the Distribution of Danger

Let $$x=(a,b)$$ be the point where Ms. Pac Man is located and let $$g_i=(a_i,b_i), i=1,2,3,4$$ be fixed coordinates for each ghost. The danger at the point $$x$$, denoted as $$d(x)$$, is

$$ d(x) = C\sum_{i=0}^{4}f\left(||x - g_i||\right)$$

where $$C$$ is a constant and $$f$$ is a function.

For reasons beyond the scope of this discussion we choose the constant $$C$$ and the function $$f$$ so that

$$ d(x) = \frac{1}{4h^2}\sum_{i=1}^{4}\frac{1}{\sqrt{2\pi}}e^{-||x - g_i||^2/2h^2}$$

The value $$h$$ is the bandwidth of the distribution. The bandwidth helps control the "reach" of the danger.

This function (1) is called a Kernel Density Estimate (KDE) and is essentially a continuous version of a histogram. In order to define the danger on any given edge $$e$$ we simply take the sum of $$d(x)$$ for $$x\in e$$. To normalize the probability we introduce the risk along an edge $$r(e)$$ and define it,

$$ r(e) = \frac{d(e)}{\sum_{e'\in E} d(e')}$$

where E is the set of all edges.

At this point we have assigned a weight - the risk - to each edge. We have a weighted bidirectional graph. We can now apply algorithms from network analysis to answer the question "what is the safest path from A to B?"

## Dijkstra's Algorithm

Given a graph with weighted edges how can we algorithmically find the (superlative) path? We could be looking for the shortest, longest, safest, fastest or cheapest path depending on the context. Here we will use Dijkstra's Algorithm. The figure below, from WikiCommons, tries to visually explain how the algorithm works.

![](/assets/images/Dijkstra_Animation.gif)

Essentially, you keep taking the (short, long, safe, fast or cheap)-est route and, as you move along the path, update the previous paths if a (short, long, safe, fast or cheap)-er path exists.

## Using Python to Solve Ms. Pac-Man's Problem

The networkX package has built in solvers that include Dikjstra's algorithm. Once we have defined the graph it takes but a few lines of code to solve the problem. One realization is the following graph,

![](/assets/images/MsPac_Large.png)

In the graph the <span style="color:red">red path</span> is the <span style="color:red">safest path</span> and the <span style="color:blue">blue path</span> is the <span style="color:blue">shortest </span>. The <span style="color:purple">purple path</span> is where the shortest and safest overlap.![](/assets/images/Ghost_Danger_0.png){:style="float: right;margin-right: 7px;margin-right: 7px;margin-top: 7px;"} The <span style="color:green">green dots</span> represent the ghosts and the two yellow dots are the starting and ending points. The plot to the right is a density map of the ghost danger. The green area represents the least amount of danger while the brown represents the highest source of danger. As we will see in the next two examples, the safest path was chosen to stay away from the ghost. The next two pictures are included with the corresponding ghost danger density alongside.

![](/assets/images/2nd_Boards.png){:height="360px" width="720px"}
![](/assets/images/Density_Ghosts_22.png)

### What's next?

I have applied this model to a subset of the city of Denver, Colorado. I will present those results in a later blog post. Along with a colleague I hope to develop an application that could be useful for the adventurous walker.

Whomever thinks about how useful this is needs to consider the difference between what is probable and what is possible. Safety is never guaranteed.

There are other similar applications of Dijkstra's algorithms: What is the most "satisfying" path home? Which way home burns the most calories? Which way home has the most bars? Then once you leave the bar you need to decide the safest way ... oh wait ... 🙂
