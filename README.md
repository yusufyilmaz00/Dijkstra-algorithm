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
    - Enter connected node pairs only once.. This means input= {A, B, cost} and input= {B, A, cost} is same thing.
    - ![node_numbers](https://i.hizliresim.com/bjo1374.png)
- **findPath()**
    - initialize integer matrix called **_valueParent[][3]_**
        - valueParent[node_index][0] = total path value
        - valueParent[node_index][1] = node Parent
        - valueParent[node_index][2] = exploration status (is node explored? 0: False 1: True)
    - fill with this numbers for each node
        - **_INFINITE_** : The large or infinite number that we defined at the beginning of the source code (defined as 999.999 at this file)
        - **_-1_** : flag for the starting node and we use this value on the printPath() function after the process is finished. After the finding path process, each cell filled with Parent_id except the starting node.
        - **_0_** : Each cell filled with 0 for exploration_status: False. 
        ```
        valueParent[i][0]= INFINITE;
        valueParent[i][1]= -1;
        valueParent[i][2]= 0;
        ```
    - Process:
        - determine minimum value (at the first iteration this is starting node) and node index
        - minValue has to be the biggest value. We use **INFINITE** for this (INFINITE: defined number at the beginning of the source code as 999.999)
        ```
        minValue = INFINITE;
        for(i=0;i<count;i++){
            if( valueParent[i][0] < minValue && valueParent[i][2] ==0){
                index = i;
                minValue = valueParent[i][0];
            }
        }
        ```

        - compare the every edge values (index: main_node_id , j: sub_node_id (edge) )
        - **_costs_** : contains edge costs
        - newCost = [ node value]  + [edge cost ]  (edge cost: cost between the connected 2 points / nodes)
        - According to Dijkstra_algorithm, new total cost must be smaller than **old node value** ( valueParent[index][0] ) for the best path.
        - if newCost statement is true, update the values
        ```
            //If node has a connection with other nodes cost has to be different from zero
            if(costs[index][j] != 0){
                
                newCost = valueParent[index][0] + costs[index][j];

                if( newCost < valueParent[j][0] ){
                    printf("update value and parent\n");
                    valueParent[j][0]= newCost;
                    valueParent[j][1]= index; 
                }
            }
        ```
        - After scanning sub nodes, update current main node exploration status (as 1 = Explored)
- **_printPath()_**
    - this function works as a recursion function
    - if nesx parent_id is -1 that means we find starting node and function stopped.
    - Function print path from starting_node to ending_node

- **_showTable()_**
    - This functions is optinol because we use only print table and iterations.
    - This functions make it easy for us to follow the process steps
    - You can delete these functions or change them as you wish. 

- **In Conculision**
    - The important point is to understand and use the algorithm .
    - Also an important part of my code, _**the process part of the findPath() function**_.

## Simple Example
Below is an example of Dijkstra's algorithm. Starting Node: A --> Finishing Node: C

![image](https://i.hizliresim.com/jffzyjd.png)
![solution](https://i.hizliresim.com/t7dwdto.png)

## Contributing
If you find any issues with the code or have suggestions for improvement, feel free to open an issue or submit a pull request. Your contributions are welcome!

# Acknowledgments
Special thanks to [Salih Can Tekin](https://github.com/salihcantekin) [(@TechBuddyTR)](https://www.youtube.com/@TechBuddyTR) on YouTube for the informative [Dijkstra's algorithm tutorial](https://www.youtube.com/watch?v=MeiKA0uai0c) that inspired this implementation.

