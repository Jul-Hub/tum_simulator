This is a branch from the yet modified package in https://github.com/angelsantamaria/tum_simulator
The simulator has been tested under ros kinetic and the instructions here are bounded for that distro

## ACS
In order to simulate the parrot arDrone in the lab environment follow the next instructions:

### Install catkin tools

    wget http://packages.ros.org/ros.key -O - | sudo apt-key add -
    sudo apt-get install python-catkin-tools

### Install vcstool

    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
    sudo apt-key adv --keyserver hkp://pool.sks-keyservers.net --recv-key 0xAB17C654
    sudo apt-get update
    sudo apt-get install python3-vcstool

### Ros packages (Maybe not complete)
Install ros packages

    sudo apt-get install ros-kinetic-hector-* ros-kinetic-robot-state-publisher 


### Get the repos:

Get the vcs repo file that will download the proper ardrone_autonomy and tum_simulator packages:

    wget https://raw.githubusercontent.com/Jul-Hub/tum_simulator/tr-11Lab/project_cfg/vcsFiles/ardrone_simulator.repos

Import the repos

    vcs import < ardrone_simulator.repos

### Compile everything

Inside the workspace folder run:

    rosdep install --from-paths src -i
    catkin build
