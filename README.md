### DIRECTED GRAPHS
To develop a function that receives a directed graph and returns a set of strongly connected directed graphs, we will follow the steps described below. Additionally, an explanation of what happens if the input graph is not directed will be provided.

**Definition of Strongly Connected Subgraph**: A strongly connected subgraph of a directed graph is one in which there is a directed path between any pair of nodes.

**Algorithm to Find Strongly Connected Subgraphs**: We will use Kosaraju's Algorithm, which is efficient and based on two depth-first searches:
- Perform an initial depth-first search to fill a stack with vertices ordered by their finishing times.
- Transpose (reverse the directions of all edges) the graph.
- Perform a second depth-first search on the transposed graph, processing vertices in the order given by the stack to identify the strongly connected subgraphs.

**Implementation Description**:
- **Node Class**:
  - Represents a node in the graph.
- **Graph Class**:
  - Represents the directed graph and contains methods to add nodes and edges.
  - Contains methods to perform a depth-first search, transpose the graph, and find strongly connected subgraphs using Kosaraju's Algorithm.
  - `initializeGraph()`: Initializes an empty graph.
  - `addNode()`: Adds a node to the graph.
  - `addEdge()`: Adds a directed edge between two nodes.
  - `findSubgraph()`: Executes Kosaraju's Algorithm to find and return the strongly connected subgraphs of the graph.
  - `printGraph()`: Prints the graph.

**Explanation of the Steps**:
1. **Graph Initialization**:
   a. Create a Graph object with nodes and edges.
   b. Nodes are stored in a dictionary, where the keys are the node identifiers and the values are the Node objects.
2. **Adding Nodes and Edges**:
   a. Use the `addNode` and `addEdge` methods to build the graph.
   b. In `addEdge`, add adjacent nodes to the adjacency list of the source node.
3. **Kosaraju's Algorithm**:
   a. Perform an initial depth-first search on the original graph, filling a stack based on each node's finishing time.
   b. Transpose the graph by reversing the edges.
   c. Perform a second depth-first search on the transposed graph, using the stack to process nodes in decreasing order of finishing time.
4. **Result Construction**:
   a. Create a new graph for each strongly connected subgraph found and return them as a set of strongly connected graphs.
