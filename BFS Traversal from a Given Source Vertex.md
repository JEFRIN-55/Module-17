# Ex. No: 17B - BFS Traversal from a Given Source Vertex

## AIM:
To write a Python program to **print BFS traversal** from a given source vertex.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Create a graph using **adjacency list representation**.

**Step 3**: Add edges between vertices using the `addEdge()` method.

**Step 4**: Implement the `BFS()` function:
- Initialize all vertices as **not visited**.
- Use a **queue** to track vertices for traversal.
- Mark the **starting vertex** as visited and enqueue it.
- Dequeue a vertex, process it, and enqueue all its **adjacent unvisited vertices** while marking them as visited.

**Step 5**: Input the **starting vertex** and perform BFS traversal from it.

**Step 6**: Print the vertices in **BFS order**.

**Step 7**: End the program.

---
## PYTHON PROGRAM

```python
# Reg.No- 212223060104
# Name- JEFRIN INOLA J 


from collections import defaultdict

class Graph:
	def __init__(self):
		self.graph = defaultdict(list)

	def addEdge(self,u,v):
		self.graph[u].append(v)

	def BFS(self, s):

		visited = [False] * (max(self.graph) + 1)

		queue = []

		queue.append(s)
		visited[s] = True

		while queue:
		    
		    s=queue.pop(0)
		    print(s,end=" ")
		    
		    for i in self.graph[s]:
		        if visited[i]==False:
		            queue.append(i)
		            visited[i]=True

n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print ("Following is Breadth First Traversal"
				" (starting from vertex {})".format(n))
g.BFS(n)

```

## OUTPUT
![image](https://github.com/user-attachments/assets/f39b2841-dd78-4a1f-b66f-d1cc821c4e47)


## RESULT
Thus, the Python program to print BFS traversal from a given source vertex is verified and executed successfully.
