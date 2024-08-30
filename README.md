# tb3-auto-slam-mapping-view-path

## Installation
- Create a Workspace using below command:
    ```bash
    mkdir your_ws
    ```
- Download the git repo and rename it as src.
- Copy or Cut this src folder to the created workspace.
- To build packages return to the your_ws and run the below command:
    ```bash
    catkin_make
    ```

## Making Changes in .bashrc

- Copy Paste the below lines to avoid sourcing and exporting model again and again.
    ```bash
    echo "export TURTLEBOT3_MODEL=waffle"
    echo "source ~/your_ws/devel/setup.bash"
    ```


## To Run
### Task1

- launch the file using below command:
    ```bash
    roslaunch turtlebot3_gazebo tb3_view_path.launch
    ```
- You can see Gazebo and Rviz in the Display, buy publishing the given pose to /move_base_simple/goal, we can see the path generated from starting point to end point and we can give a simple goal using rviz and see different path for different Goals.

- For now I used default setting for global planner which uses a_star, we can change and play with different algorithm.

### Task 2

- launch the file using below command:
    ```bash
    roslaunch turtlebot3_slam tb3_auto_mapping.launch
    ```
- You can give a goal using the pink arrow in rviz and map the env.

- To save the map go the the map_folder and run:
    ```bash
    rosrun map_server map_saver -f map_name
    ```
- To view the saved map:
    ```bash
    rosrun map_server map_server map_name.yaml
    ```
- Go to rivz and select the map_topic and we can see the map.

- I have used Gmapping, with using gmapping its like dual test, you map as well as check the odom with gmapping.
- We can use Hector SLAM as well as for simple and faster mapping needs, as it relays only on lidar data.
