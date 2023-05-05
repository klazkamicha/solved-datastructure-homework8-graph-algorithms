Download Link: https://assignmentchef.com/product/solved-datastructure-homework8-graph-algorithms
<br>
For this assignment, you will be coding various different graph algorithms. This homework has quite a few files in it, so you should make sure to read ALL of the documentation given to you before asking a question.

<h2>Graph Search (Depth First Search)</h2>

Depth-First Search is a search algorithm that visits vertices in a depth based order. It depends on a Stack based data structure to work, which for your implementation will be recursion. It searches along one path of vertices from the start vertex and backtracks once it hits a dead end or a visited vertex until it finds another path to continue along. <strong>Your implementation of DFS must be recursive.</strong>

<h2>Single-Source Shortest Path (Dijkstra’s Algorithm)</h2>

The next algorithm is Dijkstra’s Algorithm. This algorithm finds the shortest path from one vertex to all of the other vertices in the graph. This algorithm only works for non-negative edge weights, so you may assume all edge weights for this algorithm will be non-negative.

There are two main variants of Dijkstra’s Algorithm related to the termination condition of the algorithm. The classic variant is the version where you maintain both a PriorityQueue and a visited set to terminate early once you’ve visited all the vertices. The other variant is where you depend purely on the PriorityQueue to determine when to terminate the algorithm. You should implement the classic variant for this assignment.

<h2>Minimal Spanning Trees (MST – Kruskal’s Algorithm)</h2>

An MST has two components. By definition, it is a tree, which means that it is a graph that is acyclic and connected. A spanning tree is a tree that connects the entire graph. It must also be minimal, meaning the sum of edge weights of the graph must be the smallest possible while still being a spanning tree.

By the properties of a spanning tree, any valid MST must have |<em>V </em>| − 1 edges in it. However, since all undirected edges are specified as two directional edges, a valid MST for your implementation will have 2(|<em>V </em>| − 1) edges in it.

Kruskal’s algorithm takes in all of the edges of the graph and continually adds the cheapest to the MST as long as that edge does not form a cycle. To handle cycle detection, you will be using a disjointset/union-find data structure that we have provided for you.

<h3>Disjoint Set Data Structure (Union-Find)</h3>

For Kruskal’s algorithm, you will be using the DisjointSet class implementation that we have provided to maintain which components are connected. This data structure has two primary functions, union and find. The idea here is that each disconnected component is maintained as a tree. If two pieces of data are in the same tree, then they are in the same connected component.

The DisjointSet will begin with all of the data in their own one node trees to begin since nothing is connected originally. As the algorithm progresses, the nodes that are connected in the graph will be linked into the same tree in the DisjointSet.

To see whether or not the two data are in the same tree, it suffices to see if their roots are the same since the root is unique. The find method finds the root of the component’s tree.

If you add an edge to the MST in Kruskal’s, then it will cause two previously disconnected components to become a single component. The union method does this for you, merging the two trees representing the two components into a single tree.

<h2>Self-Loops and Parallel Edges</h2>

In this framework, self-loops and parallel edges work as you would expect. These cases are valid test cases, and you should expect them to be tested. However, most implementations of these algorithms handle these cases automatically, so you shouldn’t have to worry too much about them when implementing the algorithms.