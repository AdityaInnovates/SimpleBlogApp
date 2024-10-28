# Adjacency List

An adjacency list represents a graph as an array of linked lists. The index of the array represents a vertex and each element in its linked list represents the other vertices that form an edge with the vertex.

For example, we have a graph below.

![App Screenshot](https://github.com/user-attachments/assets/d4eea4ca-96d0-4092-9e4a-f7410d8889da)

We can represent this graph in the form of a linked list on a computer as shown below.

![adjacency-list-representation](https://github.com/user-attachments/assets/b91e878a-b5c3-4b6c-be5d-2702d3feea41)

Here, 0, 1, 2, 3 are the vertices and each of them forms a linked list with all of its adjacent vertices. For instance, vertex 1 has two adjacent vertices 0 and 2. Therefore, 1 is linked with 0 and 2 in the figure above.

###

# Pros of Adjacency List
* An adjacency list is efficient in terms of storage because we only need to store the values for the edges. For a sparse graph with millions of vertices and edges, this can mean a lot of saved space.
* It also helps to find all the vertices adjacent to a vertex easily.

###

# Cons of Adjacency List
* Finding the adjacent list is not quicker than the adjacency matrix because all the connected nodes must be first explored to find them.

### 

# Adjacency List Structure
The simplest adjacency list needs a node data structure to store a vertex and a graph data structure to organize the nodes.

We stay close to the basic definition of a graph - a collection of vertices and edges {V, E}. For simplicity, we use an unlabeled graph as opposed to a labeled one i.e. the vertices are identified by their indices 0,1,2,3.

Let's dig into the data structures at play here.

~~~
struct node{
    int vertex;
    struct node* next;
};

struct Graph{
    int numVertices;
    struct node** adjLists;
};
~~~

Don't let the struct node** adjLists overwhelm you.

All we are saying is we want to store a pointer to struct node*. This is because we don't know how many vertices the graph will have and so we cannot create an array of Linked Lists at compile time.

###

# Adjacency List Python
There is a reason Python gets so much love. A simple dictionary of vertices and its edges is a sufficient representation of a graph. You can make the vertex itself as complex as you want.

~~~python
graph = {'A': set(['B', 'C']),
         'B': set(['A', 'D', 'E']),
         'C': set(['A', 'F']),
         'D': set(['B']),
         'E': set(['B', 'F']),
         'F': set(['C', 'E'])}
~~~

###

# Adjacency List Code in Python

~~~python
# Adjascency List representation in Python


class AdjNode:
    def __init__(self, value):
        self.vertex = value
        self.next = None


class Graph:
    def __init__(self, num):
        self.V = num
        self.graph = [None] * self.V

    # Add edges
    def add_edge(self, s, d):
        node = AdjNode(d)
        node.next = self.graph[s]
        self.graph[s] = node

        node = AdjNode(s)
        node.next = self.graph[d]
        self.graph[d] = node

    # Print the graph
    def print_agraph(self):
        for i in range(self.V):
            print("Vertex " + str(i) + ":", end="")
            temp = self.graph[i]
            while temp:
                print(" -> {}".format(temp.vertex), end="")
                temp = temp.next
            print(" \n")


if __name__ == "__main__":
    V = 5

    # Create graph and edges
    graph = Graph(V)
    graph.add_edge(0, 1)
    graph.add_edge(0, 2)
    graph.add_edge(0, 3)
    graph.add_edge(1, 2)

    graph.print_agraph()
~~~

# Applications of Adjacency List
* It is faster to use adjacency lists for graphs having less number of edges.

###