---
layout: single
title: Multi-Robot Navigation With Convex Programming
permalink: /projects/optimization-nav/
---

From MASc. Course: `ECE 602 – Introduction to Optimization`

![gif](/Wesley-Fisher/pages/projects/optimization-nav/corridor.gif)

# Overview

A classmate and I implemented methods from the paper “Multi-robot navigation in formation via sequential convex programming,” written by Javier Alonso-Mora, Stuart Baker and Daniela Rus in IROS 2015.

This paper makes use of convex optimization to determine collision-free areas for robots to move within, and optimizes the formations of these robots. We implement and demonstrate the methods presented in a simulated environment.

This project focused on making use of existing optimization code and libraries, and we made use of pre-existing code for the core optimization calculations.

# Description

The algorithm attempts to find a convex region in space, which contains the robots’ current positions and their immediate goal positions. The original paper, and our work, use the IRIS algorithm by R. Deits and R. Tedrake, which computes the largest collision-free polytope from a given starting point.

The algorithm we (re-)implement extends this: we attempt to grow a polytope from a goal position. If the polytope contains all current robot positions, each robot can move freely towards their goals without encountering obstacles. If it does not, the starting point is moved closer to the robot formation, and the process repeats. If no valid areas are found, several fall-back options are used in succession, each with fewer guarantees of performance.

The result is that, ideally, there is a collision-free path from all current robot positions, to their goal positions, allowing each robot to navigate freely.

Our algorithm also allows switching and scaling the robot formation, for an additional cost to the optimization.

We currently do not deal with individual navigation for each robot in our demonstration, as we focused on the convex-optimization methods introduced in the paper.

# Demonstration Details

The animation provides a main view in the XY plane and secondary views in the XZ and YZ planes.

Seen in the animation is:

* Annotated time
* Blue X: current robot positions
* Red X: robot goal positions in current goal formation
* Green Dot: growth point of final $P_fog$ (term from paper)
* Blue Dot: current goal point (we use multiple to navigate a large map)

![gif](/Wesley-Fisher/pages/projects/optimization-nav/corridor.gif)


# Further Technical Details

Implemented in MATLAB, using IRIS and MOSEK. Animations shown were part of a class project presentation.
