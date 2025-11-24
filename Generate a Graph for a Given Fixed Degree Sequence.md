# Ex. No: 17A - Generate a Graph for a Given Fixed Degree Sequence

## AIM:
To write a Python program to generate a graph for a given **fixed degree sequence**.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Check if the sum of the degree sequence is even.  
> (A necessary condition for the sequence to be graphical.)

- If not even, print an error message and exit the program.

**Step 3**: Use the **Havel-Hakimi algorithm** to determine whether a simple graph can be constructed from the sequence, and to generate the graph.

**Step 4**: If the graph is successfully created, **visualize it** using a graph drawing function (e.g., `networkx.draw()`).

**Step 5**: End the program.

## PYTHON PROGRAM

```python

# Reg.No- 212223060104
# Name- JEFRIN INOLA J

class AdjNode:
	def __init__(self, data):
		self.vertex = data
		self.next = None

class Graph:
	def __init__(self, vertices):
		self.V = vertices
		self.graph = [None] * self.V

	def add_edge(self, src, dest):
		node = AdjNode(dest)
		node.next = self.graph[src]
		self.graph[src] = node


		node = AdjNode(src)
		node.next = self.graph[dest]
		self.graph[dest] = node

	
	def print_graph(self):
	    for i in range(self.V):
	        print("Adjacency list of vertex {}\n head".format(i),end=" ")
	        temp=self.graph[i]
	        while temp:
	            print("-> {}".format(temp.vertex),end=" ")
	            temp=temp.next
	        print("\n")

if __name__ == "__main__":
	V = 5
	graph = Graph(V)
	graph.add_edge(0, 1)
	graph.add_edge(0, 4)
	graph.add_edge(1, 2)
	graph.add_edge(1, 3)
	graph.add_edge(1, 4)
	graph.add_edge(2, 3)
	graph.add_edge(3, 4)

	graph.print_graph()

```

## OUTPUT
![image](https://github.com/user-attachments/assets/7a7bed5e-e524-44b9-8098-cfb0afb6b782)


## RESULT
Thus, a Python program to demonstrate the adjacency list representation of the given graph is executed successfully.
