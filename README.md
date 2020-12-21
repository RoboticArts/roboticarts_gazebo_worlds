# roboticarts_gazebo_worlds

This repository contains a database of models and worlds for Gazebo created by Robert Vasquez Zavaleta.

The vast majority of CAD files have been obtained from https://grabcad.com . However all of them were modified with Solidworks to optimize them. Then textures, colors and collisions were added in Gazebo. Finally, the models were created.

Tested on Gazebo 7.0.0 and Gazebo 9.0.0

<img src="utils/images/atom2_house_bedroom.jpg" width="60%">

## 1. Requisites

- Gazebo 7, Gazebo 9 or higher
- ROS Kinetic, ROS Melodic or higher

## 2.  Installation

Clone the database into your local machine:

```
$ git clone https://github.com/RoboticArts/roboticarts_gazebo_worlds
```

### 2.1 Gazebo models

Go to ```roboticarts_gazebo_worlds``` folder and copy the models into Gazebo model directory. By default, the Gazebo models are saved inside a hidden folder in ```/home/username/.gazebo```

```
$ cd roboticarts_gazebo_worlds
$ sudo cp -a ./gazebo_models/. ~/.gazebo/models
```

### 2.2 Gazebo worlds


Go to ```roboticarts_gazebo_worlds``` folder and copy the worlds into Gazebo worlds directory. By default it is found in ```/usr/share/gazebo-9/worlds```
You must replace ```gazebo-9``` with the version you use:

**Gazebo 7.0** 
```
$ cd roboticarts_gazebo_worlds
$ cp -a ./gazebo_worlds/. /usr/share/gazebo-7/worlds/
```
**Gazebo 9.0**
```
$ cd roboticarts_gazebo_worlds
$ cp -a ./gazebo_worlds/. /usr/share/gazebo-9/worlds/
```

## 3. Launch the world!

If you installed start_world package, you can test the worlds. 

```
$ roslaunch gazebo_ros empty_world.launch world_name:=worlds/atom2_house.world
```

<img src="utils/images/atom2_house_overview.jpg" width="60%">


To select another world, use the ```world_name``` parameter. Remember to add the ```worlds/``` prefix. For example:
```
$ world_name:=worlds/mini_atom_zone.world
```

List of current available worlds:

```
- atom2_house
- mini_atom_zone
```

## 4. Additional notes

1. No need to copy the worlds into Gazebo worlds directory. You can choose another directory. Make sure that the ```world_name``` parameter gets the full path to where the world is located.

2. On some graphics cards the orthogonal view in Gazebo causes a Segmentation Fault error when loading a world from gazebo_ros. For this reason, the worlds of this package have been set in perspective view to avoid this problem. 



