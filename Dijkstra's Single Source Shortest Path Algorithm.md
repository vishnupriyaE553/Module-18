# Ex. No: 18C - Dijkstra's Single Source Shortest Path Algorithm

## AIM:
To write a Python program for **Dijkstra's single source shortest path algorithm**.

## ALGORITHM:

**Step 1**: Initialize a `distance[]` array with infinity for all vertices except the source, which is set to `0`.  
Create a `sptSet[]` array (shortest path tree set) to keep track of vertices whose shortest distance from the source is finalized.

**Step 2**: Pick the vertex `u` with the minimum distance value from the set of vertices not yet processed.

**Step 3**: For every adjacent vertex `v` of the picked vertex `u`, if the current distance to `v` is greater than the distance to `u` plus the edge weight `(u, v)`, then update the distance of `v`.

**Step 4**: Mark the vertex `u` as processed in `sptSet`.

**Step 5**: Repeat Steps 2–4 until all vertices are processed.

**Step 6**: Print the shortest distances from the source to all other vertices.

## PYTHON PROGRAM

```
name: vishnu priya E
reg.no: 212223060305

import sys

class Graph():

	def __init__(self, vertices):
		self.V = vertices
		self.graph = [[0 for column in range(vertices)]
					for row in range(vertices)]

	def printSolution(self, dist):
		print("Vertex   Distance from Source")
		for node in range(self.V):
			print(node, "           ", dist[node])

	# A utility function to find the vertex with
	# minimum distance value, from the set of vertices
	# not yet included in shortest path tree
	def minDistance(self, dist, sptSet):

		# Initialize minimum distance for next node
		min = sys.maxsize

		# Search not nearest vertex not in the
		# shortest path tree
		for u in range(self.V):
			if dist[u] < min and sptSet[u] == False:
				min = dist[u]
				min_index = u

		return min_index

	# Function that implements Dijkstra's single source
	# shortest path algorithm for a graph represented
	# using adjacency matrix representation
	def dijkstra(self, src):

		dist = [sys.maxsize] * self.V
		dist[src] = 0
		sptSet = [False] * self.V
		for count in range(self.V):
		    x=self.minDistance(dist,sptSet)
		    sptSet[x]=True
		    for y in range(self.V):
		        if self.graph[x][y]>0 and sptSet[y]==False and dist[y]>dist[x]+self.graph[x][y]:
		            dist[y]=dist[x]+self.graph[x][y]

		self.printSolution(dist)

# Driver program
g = Graph(9)
g.graph = [[0, 4, 0, 0, 0, 0, 0, 8, 0],
		[4, 0, 8, 0, 0, 0, 0, 11, 0],
		[0, 8, 0, 7, 0, 4, 0, 0, 2],
		[0, 0, 7, 0, 6, 14, 0, 0, 0],
		[0, 0, 0, 6, 0, 5, 0, 0, 0],
		[0, 0, 4, 14, 5, 0, 2, 0, 0],
		[0, 0, 0, 0, 0, 2, 0, 1, 6],
		[8, 11, 0, 0, 0, 0, 1, 0, 7],
		[0, 0, 2, 0, 0, 0, 6, 7, 0]
		];

g.dijkstra(0);
```

## OUTPUT
<img width="611" height="348" alt="image" src="https://github.com/user-attachments/assets/8263032d-1880-4f2c-a2a8-6a34df4ddc31" />

## RESULT
thus the Python program for **Dijkstra's single source shortest path algorithm** is implemented successfully.
