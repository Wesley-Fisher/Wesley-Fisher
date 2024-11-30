---
layout: single
title: Autonomous Car Educational Platform
permalink: /projects/rc-car-platform/
---

(Unlike other projects on this site, I've left this as it was originally written)

![RC Car Platform](/pages/projects/rc-car-platform/car_cropped.png)

Working with the UW IDEAS Clinic and another MASc student, I helped to modify an RC car into an educational platform for future students.


# Project Goals

The goal of this project, like many of the IDEAS Clinic, is to provide a chance for students to gain some familiarity with real-world problems and technologies. Through this project, we hope that they will gain some experience with parts of the car itself, technologies and algorithms used to make cars autonomous, and development/testing and deployment of software.

When finished as an educational tool, this car should provide opportunities for many of the engineering programs to play around with the area of cars, and autonomous navigation, including:

* Mechanical design of the chassis
* Interfacing with electronic components
* Software algorithms
* Testing and deployment
* Use of IoT

# The Platform

The car that we’re using comes from an RC car. We’re making use of the base chassis, existing motors, speed controller, and steering servo. Beyond this, we’ve laser-cut a board to mount our own components, including:

* NVidia Jetson Nano board
* Orbec Astra depth camera
* RPlidar lidar
* Other electrical and connection components

![RC Car Platform](/pages/projects/rc-car-platform/car_cropped.png)

While we’ve used this platform to focus on integrating with sensors and creating proof-of-concept demos/algorithms, other students with the IDEAS Clinic have been developing a separate chassis and selecting a set of custom motors and controllers.

![RC Car Platform](/pages/projects/rc-car-platform/new_chassis.png)

# Software

My work has mainly been on the software development side. We’ve used ROS to communicate with the sensors and actuators on the car. I’ve then made a Python API that students can use to access sensor readings and send commands. This way, the students don’t need to worry about how the interface with the sensors themselves, and can focus on their core projects.

In addition, we’ve created a simulated version of the car to help with our own initial development, and later to provide simulated testing for students.

![Simulation World](/pages/projects/rc-car-platform/sim_world.png){: width="350"}

![Sensor Outputs](/pages/projects/rc-car-platform/sensor_demo.png){: width="350"}


# Future Work

While my time at UW is coming to an end, we plan on working in two major directions to close off this phase of the project:

1. Creating a more life-like simulation
2. Creating/improving some base line-following algorithms
3. Using cloud services for testing and deployment
4. Creating a cloud-based service to view feedback from the car
5. Finally coming up with a name for the project

![Car on tape-based road](/pages/projects/rc-car-platform/IMG_2613.png)


# UW IDEAS Clinic

The UW Engineering IDEAS Clinic develops activities to supplement student learning. More information can be found [here](https://uwaterloo.ca/engineering-ideas-clinic/).

In addition to this car project, I’ve been able to work with and guide co-op students on a number of clinic projects, from the creation of the custom car chassis, to an industrial automation project.
