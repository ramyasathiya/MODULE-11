## Ex.No:2
## Ex.Name: Minimum Cost to Connect All Houses (MST Approach)
## Date: 3/11/25
## Aim:
To write a C++ program for Given a weighted, undirected and connected graph of V vertices and E edges. The task is to find the sum of weights of the edges of the Minimum Spanning Tree. Write the Prim's function to find the MST edges.


<img width="765" height="619" alt="image" src="https://github.com/user-attachments/assets/6107508d-4da4-4082-847e-3e067ce6a5a0" />

## Algorithm
Start the program.

Define a Graph class with:

V: number of vertices
adj: adjacency list storing (vertex, weight) pairs
In primMST():

Create a priority queue (min-heap) pq to pick the next edge with the minimum weight.
Choose source vertex src = 0 and initialize sum = 0 (total MST cost).
Create:
key[V]: store minimum edge weight for each vertex, initialized as INF
parent[V]: store the parent of each vertex in MST, initialized as -1
inMST[V]: boolean array to track vertices already in MST, initialized as false
Set key[src] = 0 and push (0, src) into the priority queue.
While the priority queue is not empty:

Extract the vertex u with the smallest key from the queue.
If u is already in MST (inMST[u] == true), skip it.
Mark u as included: inMST[u] = true.
Add key[u] to sum (this is the cost of including vertex u).
For every adjacent vertex v of u with edge weight w:
If v is not yet in MST and w < key[v]:
Update key[v] = w
Push (key[v], v) into the priority queue
Set parent[v] = u
After the loop:

Use parent[] to print the MST edges: (parent[i], i) for all i = 1 to V-1.
Print the total MST cost stored in sum.
## Program:
```
void Graph::primMST()
{
	// Create a priority queue to store vertices that
	// are being primMST. This is weird syntax in C++.
	// Refer below link for details of this syntax
	// http://geeksquiz.com/implement-min-heap-using-stl/
	priority_queue< iPair, vector <iPair> , greater<iPair> > pq;
    
	int src = 0,sum=0; // Taking vertex 0 as source

	// Create a vector for keys and initialize all
	// keys as infinite (INF)
	vector<int> key(V, INF);

	// To store parent array which in turn store MST
	vector<int> parent(V, -1);

	// To keep track of vertices included in MST
	vector<bool> inMST(V, false);

	// Insert source itself in priority queue and initialize
	// its key as 0.
	pq.push(make_pair(0, src));
	key[src] = 0;

	/* Looping till priority queue becomes empty */
	while (!pq.empty())
	{
		// The first vertex in pair is the minimum key
		// vertex, extract it from priority queue.
		// vertex label is stored in second of pair (it
		// has to be done this way to keep the vertices
		// sorted key (key must be first item
		// in pair)
		int u = pq.top().second;
		pq.pop();
		
		//Different key values for same vertex may exist in the priority queue.
		//The one with the least key value is always processed first.
		//Therefore, ignore the rest.
		if(inMST[u] == true){
		    
			continue;
			
		}
	
		inMST[u] = true; // Include vertex in MST
        if (inMST[u] == true)
        sum=sum+key[u];
		// 'i' is used to get all adjacent vertices of a vertex
		list< pair<int, int> >::iterator i;
		
		for (i = adj[u].begin(); i != adj[u].end(); ++i)
		{
			// Get vertex label and weight of current adjacent
			// of u.
			
			int v = (*i).first;
			int weight = (*i).second;
				
			// If v is not in MST and weight of (u,v) is smaller
			// than current key of v
			if (inMST[v] == false && key[v] > weight)
			{
				// Updating key of v
				key[v] = weight;
				
				pq.push(make_pair(key[v], v));
				parent[v] = u;
			}
		}
		
	}

	// Print edges of MST using parent array
	for (int i = 1; i < V; ++i)
		cout<<"\n"<<parent[i]<<" - "<<i<<"  ";
	cout<<"\nMST cost = "<<sum;
		
}
```
## Output:

<img width="697" height="711" alt="image" src="https://github.com/user-attachments/assets/0e31257e-148c-46da-8ec6-5e3283c48fa7" />




## Result:
The Program Executed Successfully.
