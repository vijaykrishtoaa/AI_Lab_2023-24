# Ex.No: 2  Implementation of Depth First Search
### DATE:                                                                            
### REGISTER NUMBER : 
### AIM: 
To write a python program to implement Depth first Search. 
### Algorithm:
1. Start the program
2. Create the graph by using adjacency list representation
3. Define a function dfs and take the set “visited” is empty 
4. Search start with initial node. Check the node is not visited then print the node.
5. For each neighbor node, recursively invoke the dfs search.
6. Call the dfs function by passing arguments visited, graph and starting node.
7. Stop the program.
### Program:
from collections import deque

def bfs(graph, start):
    visited = set()           # To keep track of visited nodes
    queue = deque([start])    # Initialize queue with the start node

    while queue:
        vertex = queue.popleft()   # Remove from queue
        if vertex not in visited:
            print(vertex, end=" ")  # Process the node (print here)
            visited.add(vertex)

            # Add unvisited neighbors to the queue
            for neighbor in graph[vertex]:
                if neighbor not in visited:
                    queue.append(neighbor)


# Example usage:
graph = {
    'A': ['B', 'C'],
    'B': ['A', 'D', 'E'],
    'C': ['A', 'F'],
    'D': ['B'],
    'E': ['B', 'F'],
    'F': ['C', 'E']
}

print("Breadth-First Search starting from node A:")
bfs(graph, 'A')











### Output:
Breadth-First Search starting from node A:
A B C D E F


### Result:
Thus the depth first search order was found sucessfully.
