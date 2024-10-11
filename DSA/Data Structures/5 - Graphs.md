Here's a comprehensive guide to understanding graphs in C++ as part of Data Structures and Algorithms (DSA). This guide covers the definition, types, properties, representations, operations, traversal algorithms, and applications of graphs.

---

# **Guide to Graphs in C++ DSA**

## **1. Introduction to Graphs**
A **graph** is a collection of nodes (or vertices) connected by edges. It is a versatile data structure used to represent relationships between entities. Graphs can model various real-world scenarios, such as social networks, transportation systems, and web page linking.

### **Basic Definitions**
- **Vertex (Node):** A fundamental part of a graph that represents an entity.
- **Edge:** A connection between two vertices.
- **Directed Graph:** A graph in which edges have a direction (from one vertex to another).
- **Undirected Graph:** A graph in which edges have no direction (the connection is bidirectional).
- **Weighted Graph:** A graph in which edges have weights (costs, distances).
- **Unweighted Graph:** A graph where all edges are considered equal.
- **Degree:** The number of edges connected to a vertex.

## **2. Types of Graphs**
Graphs can be classified based on various criteria:

1. **Directed vs. Undirected Graphs:**
   - Directed Graph (Digraph): Each edge has a direction.
   - Undirected Graph: Each edge is bidirectional.

2. **Weighted vs. Unweighted Graphs:**
   - Weighted Graph: Edges have weights or costs associated.
   - Unweighted Graph: All edges have equal weight.

3. **Simple Graph vs. Multigraph:**
   - Simple Graph: No loops or multiple edges between the same vertices.
   - Multigraph: Multiple edges between the same pair of vertices are allowed.

4. **Cyclic vs. Acyclic Graphs:**
   - Cyclic Graph: Contains at least one cycle.
   - Acyclic Graph: Does not contain any cycles.

5. **Connected vs. Disconnected Graphs:**
   - Connected Graph: There is a path between every pair of vertices.
   - Disconnected Graph: At least one pair of vertices does not have a path connecting them.

## **3. Graph Representation in C++**
Graphs can be represented in various ways, the most common being:

### **1. Adjacency Matrix**
An adjacency matrix is a 2D array where the element at the \(i^{th}\) row and \(j^{th}\) column indicates the presence (and weight) of an edge between vertex \(i\) and vertex \(j\).

#### **Adjacency Matrix Implementation**
```cpp
#include <iostream>
#include <vector>
using namespace std;

class Graph {
private:
    vector<vector<int>> adjMatrix;
    int numVertices;

public:
    Graph(int vertices) {
        numVertices = vertices;
        adjMatrix.resize(vertices, vector<int>(vertices, 0)); // Initialize matrix with 0s
    }

    void addEdge(int src, int dest, int weight = 1) {
        adjMatrix[src][dest] = weight; // For directed graphs
        adjMatrix[dest][src] = weight; // Uncomment this for undirected graphs
    }

    void display() {
        for (int i = 0; i < numVertices; i++) {
            for (int j = 0; j < numVertices; j++) {
                cout << adjMatrix[i][j] << " ";
            }
            cout << endl;
        }
    }
};

int main() {
    Graph g(5);
    g.addEdge(0, 1, 1);
    g.addEdge(0, 4, 1);
    g.addEdge(1, 4, 1);
    g.addEdge(1, 3, 1);
    g.addEdge(3, 4, 1);
    
    cout << "Adjacency Matrix:\n";
    g.display();

    return 0;
}
```

### **2. Adjacency List**
An adjacency list is an array of lists. Each index in the array represents a vertex, and each element in the list represents the vertices adjacent to it.

#### **Adjacency List Implementation**
```cpp
#include <iostream>
#include <list>
using namespace std;

class Graph {
private:
    int numVertices;
    list<int>* adjList; // Array of lists

public:
    Graph(int vertices) {
        numVertices = vertices;
        adjList = new list<int>[vertices]; // Create an array of lists
    }

    void addEdge(int src, int dest) {
        adjList[src].push_back(dest); // Add edge to the list
        adjList[dest].push_back(src); // Uncomment this for undirected graphs
    }

    void display() {
        for (int i = 0; i < numVertices; i++) {
            cout << i << " -> ";
            for (auto& vertex : adjList[i]) {
                cout << vertex << " ";
            }
            cout << endl;
        }
    }

    ~Graph() {
        delete[] adjList; // Clean up
    }
};

int main() {
    Graph g(5);
    g.addEdge(0, 1);
    g.addEdge(0, 4);
    g.addEdge(1, 4);
    g.addEdge(1, 3);
    g.addEdge(3, 4);

    cout << "Adjacency List:\n";
    g.display();

    return 0;
}
```

## **4. Graph Traversal Algorithms**
Two primary graph traversal algorithms are commonly used:

### **1. Depth-First Search (DFS)**
DFS explores as far as possible along each branch before backtracking. It can be implemented using recursion or a stack.

#### **DFS Implementation**
```cpp
#include <iostream>
#include <list>
#include <vector>
using namespace std;

class Graph {
private:
    int numVertices;
    list<int>* adjList;

public:
    Graph(int vertices) {
        numVertices = vertices;
        adjList = new list<int>[vertices];
    }

    void addEdge(int src, int dest) {
        adjList[src].push_back(dest);
        adjList[dest].push_back(src);
    }

    void DFSUtil(int vertex, vector<bool>& visited) {
        visited[vertex] = true; // Mark the vertex as visited
        cout << vertex << " ";

        for (int neighbor : adjList[vertex]) {
            if (!visited[neighbor]) {
                DFSUtil(neighbor, visited); // Recur for unvisited neighbors
            }
        }
    }

    void DFS(int startVertex) {
        vector<bool> visited(numVertices, false); // Track visited vertices
        DFSUtil(startVertex, visited);
        cout << endl;
    }

    ~Graph() {
        delete[] adjList;
    }
};

int main() {
    Graph g(5);
    g.addEdge(0, 1);
    g.addEdge(0, 4);
    g.addEdge(1, 4);
    g.addEdge(1, 3);
    g.addEdge(3, 4);

    cout << "DFS starting from vertex 0:\n";
    g.DFS(0); // Output: 0 1 4 3

    return 0;
}
```

### **2. Breadth-First Search (BFS)**
BFS explores all neighbors at the present depth prior to moving on to nodes at the next depth level. It uses a queue for implementation.

#### **BFS Implementation**
```cpp
#include <iostream>
#include <list>
#include <queue>
#include <vector>
using namespace std;

class Graph {
private:
    int numVertices;
    list<int>* adjList;

public:
    Graph(int vertices) {
        numVertices = vertices;
        adjList = new list<int>[vertices];
    }

    void addEdge(int src, int dest) {
        adjList[src].push_back(dest);
        adjList[dest].push_back(src);
    }

    void BFS(int startVertex) {
        vector<bool> visited(numVertices, false); // Track visited vertices
        queue<int> q;

        visited[startVertex] = true; // Mark the start vertex as visited
        q.push(startVertex); // Enqueue start vertex

        while (!q.empty()) {
            int vertex = q.front();
            q.pop();
            cout << vertex << " "; // Visit the vertex

            for (int neighbor : adjList[vertex]) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true; // Mark neighbor as visited
                    q.push(neighbor); // Enqueue the neighbor
                }
            }
        }
        cout << endl;
    }

    ~Graph() {
        delete[] adjList;
    }
};

int main() {
    Graph g(5);
    g.addEdge(0, 1);
    g.addEdge(0, 4);
    g.addEdge(1, 4);
    g.addEdge(1, 3);
    g.addEdge(3, 4);

    cout << "BFS starting from vertex 0:\n";
    g.BFS(0); // Output: 0 1 4 3

    return 0;
}
```

## **5. Graph Algorithms**
Several key algorithms operate on graphs:

1. **Dijkstra’s Algorithm:** Finds the shortest path from a source vertex to all other vertices in a weighted graph.
2. **Bellman-Ford Algorithm:** Computes shortest paths from a single source vertex to all other vertices, accommodating negative weights.
3. **Floyd-Warshall Algorithm:** Computes shortest paths between all pairs of vertices.
4. **Kruskal’s Algorithm:** Finds the minimum spanning tree of a graph.


5. **Prim’s Algorithm:** Another approach to finding the minimum spanning tree.
6. **Topological Sorting:** Linear ordering of vertices for directed acyclic graphs (DAGs).

### **Example of Dijkstra's Algorithm Implementation**
```cpp
#include <iostream>
#include <vector>
#include <set>
#include <climits>

using namespace std;

class Graph {
private:
    int numVertices;
    vector<pair<int, int>>* adjList; // pair<destination, weight>

public:
    Graph(int vertices) {
        numVertices = vertices;
        adjList = new vector<pair<int, int>>[vertices];
    }

    void addEdge(int src, int dest, int weight) {
        adjList[src].emplace_back(dest, weight); // Add directed edge with weight
        adjList[dest].emplace_back(src, weight); // Uncomment for undirected graphs
    }

    void dijkstra(int startVertex) {
        vector<int> distances(numVertices, INT_MAX); // Initialize distances
        distances[startVertex] = 0;

        set<pair<int, int>> minHeap; // Min-heap to select the vertex with the smallest distance
        minHeap.insert({0, startVertex}); // (distance, vertex)

        while (!minHeap.empty()) {
            int vertex = minHeap.begin()->second; // Get the vertex with the smallest distance
            minHeap.erase(minHeap.begin()); // Remove it from the set

            for (const auto& edge : adjList[vertex]) {
                int neighbor = edge.first;
                int weight = edge.second;

                // Relaxation step
                if (distances[vertex] + weight < distances[neighbor]) {
                    minHeap.erase({distances[neighbor], neighbor}); // Remove the neighbor from the heap
                    distances[neighbor] = distances[vertex] + weight; // Update distance
                    minHeap.insert({distances[neighbor], neighbor}); // Insert updated distance
                }
            }
        }

        // Print distances from the source vertex
        cout << "Vertex Distance from Source (" << startVertex << "):\n";
        for (int i = 0; i < numVertices; i++) {
            cout << "Vertex " << i << ": " << distances[i] << endl;
        }
    }

    ~Graph() {
        delete[] adjList;
    }
};

int main() {
    Graph g(5);
    g.addEdge(0, 1, 10);
    g.addEdge(0, 4, 5);
    g.addEdge(1, 2, 1);
    g.addEdge(2, 3, 4);
    g.addEdge(4, 1, 3);
    g.addEdge(4, 2, 9);
    g.addEdge(4, 3, 2);
    g.addEdge(3, 2, 6);

    g.dijkstra(0); // Output distances from vertex 0

    return 0;
}
```

## **6. Applications of Graphs**
Graphs are widely used in various applications:
- **Social Networks:** Represent users as vertices and connections as edges.
- **Web Page Ranking:** Used in algorithms like PageRank.
- **Network Routing:** Determine optimal paths in communication networks.
- **Recommendation Systems:** Suggest items based on user preferences.
- **Game Development:** Manage connections between game objects and map structures.

## **7. Conclusion**
Graphs are a vital data structure in computer science and play a crucial role in various applications. Understanding graph representations, traversal algorithms, and common algorithms like Dijkstra's and Kruskal's is essential for solving complex problems efficiently. This guide provides a solid foundation for working with graphs in C++.
