# Depth-First Search (DFS) Algorithm

## Introduction
Depth-First Search (DFS) is an algorithm used for traversing or searching tree or graph data structures. The algorithm starts at the root node and explores as far as possible along each branch before backtracking.

## How DFS Works
1. Start from the root (or any arbitrary node in case of a graph).
2. Visit the node and mark it as visited.
3. Recursively visit all the unvisited adjacent nodes.
4. If a dead-end is reached, backtrack to the last visited node and continue.

## DFS Implementation in JavaScript
Below is the JavaScript implementation of DFS for a graph using an adjacency list representation.

```javascript
class Graph {
    constructor() {
        this.adjacencyList = {};
    }

    addVertex(vertex) {
        if (!this.adjacencyList[vertex]) {
            this.adjacencyList[vertex] = [];
        }
    }

    addEdge(vertex1, vertex2) {
        this.adjacencyList[vertex1].push(vertex2);
        this.adjacencyList[vertex2].push(vertex1);
    }

    dfs(start, visited = new Set()) {
        if (!this.adjacencyList[start]) return;
        
        console.log(start);
        visited.add(start);
        
        for (let neighbor of this.adjacencyList[start]) {
            if (!visited.has(neighbor)) {
                this.dfs(neighbor, visited);
            }
        }
    }
}

// Example Usage:
const graph = new Graph();
graph.addVertex('A');
graph.addVertex('B');
graph.addVertex('C');
graph.addVertex('D');
graph.addVertex('E');

graph.addEdge('A', 'B');
graph.addEdge('A', 'C');
graph.addEdge('B', 'D');
graph.addEdge('C', 'E');
graph.addEdge('D', 'E');

graph.dfs('A');
```

## Complexity Analysis
- **Time Complexity**: \(O(V + E)\), where V is the number of vertices and E is the number of edges.
- **Space Complexity**: \(O(V)\) due to the recursion stack and visited set.

## Applications of DFS
- Finding connected components in a graph.
- Solving mazes and puzzles.
- Topological sorting in a Directed Acyclic Graph (DAG).
- Detecting cycles in a graph.

## Conclusion
DFS is a fundamental graph traversal algorithm used in various applications, including AI, networking, and pathfinding. The above JavaScript implementation provides a simple yet effective way to explore graphs using DFS.

