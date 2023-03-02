# Apptainer container to run the ROS/naoqi bridge 

Aldebaran has stopped maintaining the ROS/naoqi bridge and the latest available versions only support ROS melodic / python 2.7 on Ubuntu 18.04.

This repository provides a container definition file for [Apptainer](https://apptainer.org/) that allows to run this code on newer systems.

## Building the container

1. Install Apptainer 1.1.6 (or any newer version) if not already done

1. Run

	apptainer build melodic-naoqi.sif melodic-naoqi.def

## Running the bridge

1. start a ROS master on your machine 

1. in the container set the `ROS_MASTER_URI` and `NAO_IP` environment variables to the values corresponding to your ROS master node and robot IP address.

1. run :

    export NAO_IP=<robot_ip>
	export MYIP=<workstation ip>
	export MYINTERFACE=<workstation interface>
	./melodic-naoqi.sif

  to run the naoqi driver

## Interacting with the container 

To launch a [tmux](https://github.com/tmux/tmux/wiki) environment in the container run:

	apptainer exec melodic-naoqi.sif tmux

The  ROS workspace in located in `/pepper` in the container. Some sample commands: 

	source /pepper/devel/setup.bash
	rosrun pepper_utils scripts/start.py



	
