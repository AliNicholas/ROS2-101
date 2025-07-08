### Open VScode
```
cd ~
cd /opt/ros/humble
code .
```

### Run turtlesim
ros2 run turtlesim turtlesim_node
ros2 run turtlesim turtle_teleop_key
ros2 topic echo /turtle1/cmd_vel

## ROS Topics
topics link two nodes together, for example pub node and sub node connected using topics
- view topic info -> ros2 topic info <topic_name>

## ROS Services
Server-Client relationship

- ros2 service list
- see service type -> ros2 service list -t
- find service -> ros2 service find <service_type>
- ros2 service call /clear std_srvs/srv/Empty

## ROS Parameters
passing data to node using parameters

Parameters are values you can change inside a node.

3. See list of parameters
   ros2 param list
4. Get Parameter Value
   ros2 param get <node_name> <param_name>
   ros2 param get /turtlesim background_g
5. Set parameter value
   ros2 param set <node_name> <param_name> <values>
   ros2 param set /turtlesim background_g 255
6. View all param for a node
   ros2 param dump <node_name>
   ros2 param dump /turtlesim
7. Store param in yaml file
   ros2 param dump /turtlesim > turtlesim.yaml
8. Load param from yaml file
   ros2 param load /turtlesim turtlesim.yaml
9. Load param on startup
   ros2 run turtlesim turtlesim_node --ros-args --params-file <file_name>
