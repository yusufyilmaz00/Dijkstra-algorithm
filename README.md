# Dijkstra's Algorithm Implementation in C
![image](https://i.stechies.com/1200x756/userfiles/images/Dijkstras-algorithm.jpg)
This repository contains a C implementation of Dijkstra's algorithm, a popular algorithm used to find the shortest path between nodes in a weighted graph.

## Introduction
Dijkstra's algorithm is a greedy algorithm that finds the shortest path from a source node to all other nodes in a weighted graph. It guarantees the shortest path for non-negative edge weights, making it suitable for various applications such as network routing and GPS navigation systems.

## Problem Statement
In this implementation, we have used a simple example problem of finding the shortest path between nodes in a city's road network. Each road connecting two nodes has an associated positive weight representing the distance between the two points. Given a starting and finishing node, the algorithm finds the shortest path to the finishing node in the graph.

# Functions and Input Formats
 - First enter the number of nodes and then enter names of nodes.
 - **getEdgeAndCost()**
    - use number instead of names for nodes
    - After entering of all nodes enter '0' to finish the loop
    - Enter the connected node couples at once. This means input= {A, B, cost} and input= {B, A, cost} is same thing.
    - ![node_numbers](https://i.hizliresim.com/bjo1374.png)
- **findPath()**
    - initialize integer matrix called **_valueParent[][3]_**
        - valueParent[node_index][0] = total path value
        - valueParent[node_index][1] = node Parent
        - valueParent[node_index][2] = exploration status (is node explored? 0: False 1: True)
    - fill with this numbers for each node
        - **_INFINITE_**: The large or infinite number we defined at the beginning of the source code (defined as 999.999 at this file)
        - **_-1_**: flag for the starting node and we use this value on the printPath() function after the process is finished. After the finding path process, each cell filled with Parent_id except the starting node.
        - **_0_**: Each cell filled with 0 for exploration_status: False. 
        ```
        valueParent[i][0]= INFINITE;
        valueParent[i][1]= -1;
        valueParent[i][2]= 0;
        ```
    - Process:
        - determine minimum value (at first iteration this is starting node) and node index

## Simple Example
Below is an example of Dijkstra's algorithm.
![image](https://i.hizliresim.com/6wcm9wr.png)

## Contributing
If you find any issues with the code or have suggestions for improvement, feel free to open an issue or submit a pull request. Your contributions are welcome!

# Acknowledgments
Special thanks to [Salih Can Tekin](https://github.com/salihcantekin) [(@TechBuddyTR)](https://www.youtube.com/@TechBuddyTR) on YouTube for the informative [Dijkstra's algorithm tutorial](https://www.youtube.com/watch?v=MeiKA0uai0c) that inspired this implementation.

