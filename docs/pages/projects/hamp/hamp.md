---
layout: single
title: Human Aware Motion Planning using Augmented PRM
permalink: /projects/hamp/
---

This project came from a research project worked on mainly by another graduate student in my lab. This was around 2019-2020.

![PRM map and results](/pages/projects/hamp/prm_astar_results.png)

The motivation of this project was to improve the human experience in collaborative/close-proximity tasks by using a human-aware motion planner. The 'human aware' aspects, when considered, would ideally lead to robot motion planning and execution that would be easier for a collaborating human to work with.

The other student I worked with handled the majority of this project, while I investigated other possibilities. I started with the PoC PRM that I discuss below. I later implemented some of this in a full robotics context, using the Pinocchio library. Unfortunately, these later implementations weren't able to run fast enough to be useable in a real-time framework, and the investigation didn't go any further than this.

I think the PoC stage of this still serves as a nice experiment with implementing a PRM and search algorithms, and in demonstrating the effect of different cost functions.

# General Approach

My general high-level approach to this PoC problem was:

1. Implement the generation of a PRM in a 2D grid as a toy example
2. Augment a standard distance-based cost to edges and nodes with further information, which could be expanded in a robotics context to include kinematic and dynamic information
3. Use this new information to create different cost functions 
4. Run an A* search algorithm on the PRM with subsets of cost functions added, and observe the behavior

# Implementation

The 2D PRM I created It contains:

* An obstacle (black square)
* Higher-cost regions (grey), which I added as an analogue to having a higher likelihood of a collision/obstacle (most planners did not have this information)
* Nodes (blue dots)
* Edges (green lines)

The planning problem was to plan a path from the upper-left of the image to the bottom-right.

I ran an A* planning on this PRM with different costs applied, shown as different colored lines:

* Red: standard A*
* Pink: cost for being above the (top-left to bottom-right) downward diagonal (right-shifted)
* Brown: cost for being high up in the world
* Grey: cost for moving directly towards the black object
* Blue: cost for moving into high-cost nodes (this was the only planner with this information)

![PRM map and results](/pages/projects/hamp/prm_astar_results.png)

I've implemented planning algorithms in other courses, but the ones that I can remember used fairly standard cost functions; usually/likely euclidean or joint-space distance between nodes. It was interesting to see the difference that adding these non-standard cost functions could introduce. In particular, the behavior of the Blue path to avoid the higher-cost regions, while the Grey planner spent significant time in one region to avoid approaching the black obstacle.

# Extensions to Human-Robot Work

I investigated using Kinematic and Dynamic information on a robot arm to motion planners, using the Pinocchio robotics library. Unfortunately, I couldn't get the implementation running fast enough to be feasible for use in the project further.

It's still interesting to consider how aspects of this PoC could have been applied:

* A detected human as a known obstacle (black shape)
* Areas commonly or likely to be occupied by the human might have higher risks of collision or interrupt work (grey regions)
* We might want a robot to avoid moving directly towards a person, face, etc (Grey planner line)

And the possible extensions to a full human-robot application:

* Costs based on momentum, or momentum directed to the human
* Being within line-of-sight (I believe this was implemented by the fellow student)
* Anticipating the next motions of the human and how to avoid them (grey regions)
