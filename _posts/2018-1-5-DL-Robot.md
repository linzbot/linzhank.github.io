---
layout: post
title: A Virtual Skilltree for a Robot
published: false
data: 2018-01-05 15:42:00
---

# Big Picture
* *Initialize: Build a simulation environment with an inverted pendulum in gazebo*
  - [x] Create inverted pendulum model using URDF, and visualize the model in rviz
  - [x] Spawn the inverted pendulum in gazebo
  - [x] Move the inverted pendulum using ROS
  - [ ] Generate reinforcement learning friendly environment with ROS+Gazebo combination
    - [x] Read joint states from model
    - [ ] Enables reset environemnt function \(current major problem\)
    - [ ] Feedback with reward for each state
  - [ ] Implement deep reinforcement learning to control the inverted pendulum
* *Build simulation environment with model of the robot in gazebo*
  - [ ] Create Kuka's model using URDF \(partly available at [kuka_experiment](https://github.com/ros-industrial/kuka_experimental/tree/indigo-devel/kuka_kr10_support)\)
* *Simulated robot learns to catch with real human data feed*
* *Ultimate goal: The robot catches the ball thrown by human*