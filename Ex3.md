## Ex.No:3
## Ex.Name: Dijkstra’s Shortest Path Algorithm
## Date: 3/11/25
## Aim:
To write a C++ program to find the shortest distance from source vertex (0 / A) to all other vertices using Dijkstra’s Algorithm.

<img width="669" height="392" alt="481639480-7e378640-796b-45e3-89ab-a7e799e8282c" src="https://github.com/user-attachments/assets/64adf0e7-04b6-4baa-98bb-287108688bae" />





## Algorithm:
Start the program.

Input the number of vertices V and edges E.

Store the graph as an adjacency list with edge weights.

Initialize:
A distance array dist[] with infinity.
Set dist[0] = 0 (source).
A min-priority queue to extract the vertex with minimum distance.

While the queue is not empty:
Pick the vertex u with the smallest dist[u].

For every adjacent vertex v of u, check if:
dist[u] + weight(u, v) < dist[v]

If yes, update dist[v] and push it into the priority queue.

Repeat until all vertices are processed.

Print the shortest distance of each vertex from the source.

Stop the program.

## Program:
```
printf("Vertex Distance from Source\n");
for(int i=0;i<V;i++){
    cout<<char(i+65)<<" "<<dist[i]<<"\n";
}
}
```
## Output:



<img width="426" height="666" alt="481639752-95a979f5-001b-4918-b0e7-f7210c595e1f" src="https://github.com/user-attachments/assets/4709abbe-c589-400f-b7a4-7aa4fcd96869" />




## Result:
The Program Executed Successfully.
