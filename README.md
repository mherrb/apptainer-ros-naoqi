# Apptainer container to run the ROS/naoqi bridge 

Aldebaran has stopped maintaining the ROS/naoqi bridge and the latest available versions only support ROS melodic / python 2.7 on Ubuntu 18.04.

This repository provides a container definition file for [Apptainer](https://apptainer.org/) that allows to run this code on newer systems.

## Building the container

1. Install Apptainer 1.1.6 (or any newer version) if not already done

1. Run

	apptainer build melodic-naoqi.sif melodic-naoqi.def
	
## Using the container 

Run 

	./melodic-naoqi.sif tmux
	
To launch a [tmux](https://github.com/tmux/tmux/wiki) environment in the container. 

## Building the ROS naoqi bridge

Follow those [instructions](https://github.com/RIS-WITH/ris_with_documentation/blob/master/robots/pepper_install.md) (only the Pepper software section) inside the container

## Running the bridge

1. start a ROS master on your machine 

1. in the container set the `ROS_MASTER_URI` and `NAO_IP` environment variables to the values corresponding to your ROS master node and robot IP address.

1. run

	apptainer exec ./melodic-naoqui.siff roslaunch XXX Fill me
	




	
