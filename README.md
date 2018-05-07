# 3D Motion Planning
![Quad Image](./misc/enroute.png)

![Motion Plan](./misc/result.gif)

This project is a continuation of the Backyard Flyer project where a simple square shaped flight path is executed. In this project, motion planning is executed by both grid and graph approaches.

## Motion Planning
### Grid Planning
In this approach, the map is split into grids. Goal location is defined in terms of longitude and latitude. It is converted x-y position information by using `global_to_local` function. A trajectory is constructed between start and goal positions by `A*` algorithm. This algorithm needs an heuristic function. For this purpose, we use Euclidean function as an heuristic. To decrease the waypoints and smooth the trajectory, we prune the path by checking collinearity of the waypoints.  

### Graph Planning
In this approach, the map is converted into skeleton by `medial_axis` function. Goal location is defined in terms of longitude and latitude. Unlike grid approach, in this case there are nodes instead of grids. Closest nodes are found for both start and goal locations. A trajectory is constructed between start and goal positions by `A*` algorithm.  To decrease the waypoints and smooth the trajectory, we prune the path by checking collinearity of the waypoints.

## To complete this project the local machine, follow these instructions:
### Step 1: Download the Simulator
This is a new simulator environment!  

Download the Motion-Planning simulator for this project that's appropriate for your operating system from the [simulator releases respository](https://github.com/udacity/FCND-Simulator-Releases/releases).

### Step 2: Set up your Python Environment
If you haven't already, set up your Python environment and get all the relevant packages installed using Anaconda following instructions in [this repository](https://github.com/udacity/FCND-Term1-Starter-Kit)

### Step 3: Clone this Repository
```sh
git clone https://github.com/MeRKeZ/FlyingCar_MotionPlanning
```
### Step 4: Test setup
The first task in this project is to test the [solution code](https://github.com/MeRKeZ/FlyingCar_MotionPlanning/blob/master/backyard_flyer_solution.py) for the Backyard Flyer project in this new simulator. Verify that your Backyard Flyer solution code works as expected and your drone can perform the square flight path in the new simulator. To do this, start the simulator and run the [`backyard_flyer_solution.py`](https://github.com/MeRKeZ/FlyingCar_MotionPlanning/blob/master/backyard_flyer_solution.py) script.

```sh
source activate fcnd # if you haven't already sourced your Python environment, do so now.
python backyard_flyer_solution.py
```
The quad should take off, fly a square pattern and land, just as in the previous project. If everything functions as expected then you are ready to start work on this project. 

### Step 5: Determine Goal Location
In this project, Grid and Graphs approaches are utilized to complete the motion planning. In `motion_planning_grid.py` or `motion_planning_graph.py`, goal location variable can be edited easily. 

### Step 6: Execute the Plan

`motion_planning_grid.py` and `motion_planning_graph.py` are basically a modified versions of `backyard_flyer.py` that leverages some extra functions in `planning_utils.py`. It should work right out of the box.  Try running `motion_planning_grid.py` or `motion_planning_graph.py`to see how it reacts. To do this, first start up the simulator, then at the command line:
 
```sh
source activate fcnd # if you haven't already sourced your Python environment, do so now.
python motion_planning_grid.py
```
or

```sh
source activate fcnd # if you haven't already sourced your Python environment, do so now.
python motion_planning_graph.py
```
