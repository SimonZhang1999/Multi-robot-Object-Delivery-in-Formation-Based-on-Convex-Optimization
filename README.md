## Multi-robot Object Delivery in Formation Based on Convex Optimization

### Project Description
This project is divided into the following tasks:
1.  Select a valid point in the map of randomly generated obstacles and generates the corresponding convex obstruction-free region.

2.  Global path planning and trajectory optimization.

3. Multi-robot task allocation.

4. Cooperative object handling and formation holding.

### Code Requirements and Dependencies
1. MATLAB2017b or later

2. Matlab built-in Toolbox: `Parallel Computing`, `Optimization`, `PID Tuner`.

3. [MOSEK/9.0](https://github.com/star2dust/MOSEK-MATLAB)

4. [Robotics Toolbox](https://github.com/star2dust/Robotics-Toolbox)

### Running the Code
Before running the code, add the subfunction and data files to the working path: right-click `data`, `sub_function_draw`, `sub_function_gp`, `sub_function_mc`, `sub_function_ta`, `sub_function_ts`, `test` folder and select "Add to Path" and then select "Selected Folders and Subfolders ".

- Modify the following different iteration conditions (comment out one of the two lines of code for  `Global_planning.m` in the `sub_function_gp` folder) to the first feasible or globally optimal trajectory, and the corresponding optimized trajectory:

```matlab
while isempty(noderoute)
while length(find(cell_dis_total==-Inf)) < size(cell_x,1)*size(cell_x,2)*0.9
```

run `global_planning_test.m` in the test folder to visualize the optimized trajectory.
This may take some time to complete, depending on the performance of the computer. It takes several minutes to find the globally optimal path.

- run `Computing_LargeConvexRegions.m` in the test folder to show the process of convex region generation and output the hyperparameters of the separated hyperplane in the command window.

- run `motion_plannning_ta_test.m` in the test folder to visualizes the process of multi-robot task allocation and formation.

- run `motion_planning_fh_test.m` in the test folder to display animation: Multiple robots maintain formation and follow a global path to move objects.

- run `Project_Presentation.m` in the test folder to show multi-robot task scheduling, 3 robots form formation, hold formation, and work together.
