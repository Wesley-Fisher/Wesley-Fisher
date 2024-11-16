---
layout: single
title: Human Aware Motion Planning using Augmented PRM
permalink: /projects/hamp/
---

This project is in the proposal/proof-of-concept stage in my lab. Our goal is to improve the human experience in collaborative/close-proximity tasks by using a human-aware motion planner.

My approach to this is two-fold:

    Generate a PRM, augmented with information to make human-aware calculations cheaper, such as:
        Collision probabilities
        Values needed for kinematic and dynamic calculations
    Find paths in the graph, using a modified A* search, but calculating human-aware costs, such as:
        Probability of collision
        Proximity to human
        Rapid motions towards human
# Demonstration PRM

As the initial proof-of-concept (and easy-to-debug example), I’ve created a 2D world, with:

    An obstacle (black square)
    high-probability collision regions (grey)

There are several attempts at planing from the upper-left to lower-right corners:

    Red: standard A*
    Pink: cost for being above the downward diagonal (right-shifted)
    Brown: cost for being high up in the world
    Grey: cost for moving directly towards the black object
    Blue: cost for moving into high-probability-collision nodes (only planner with this knowledge)

Upcoming Work

    Extension to robot arm planning
    Improvements to PRM generation
    Investigating properly adapting A* search to these additional cos