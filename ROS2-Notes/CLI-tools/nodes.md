# ROS graph
The ROS graph is a network of ROS 2 elements processing data together at the same time. 
It encompasses(包含) all executables and the connections between them if you were to map them all out and visualize them.

# Nodes in ROS 2
Each node in ROS should be responsible for **a single, modular purpose**, 
e.g. controlling the wheel motors or publishing the sensor data from a laser range-finder.   
Each node can **send** and **receive** data from other nodes via **topics, services, actions,** or **parameters**.
