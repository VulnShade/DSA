```javascript
class Graph {
    constructor() {
        this.adjacencyList = {};
    }

    addVertex(vertex) {
        if(!this.adjacencyList[vertex]) this.adjacencyList[vertex] = [];
    }

    addEdge(vertex1, vertex2) {
        if(this.adjacencyList[vertex1] && this.adjacencyList[vertex2]) {
            this.adjacencyList[vertex1].push(vertex2);
            this.adjacencyList[vertex2].push(vertex1);
        }
    }

    removeEdge(vertex1, vertex2) {
         if(this.adjacencyList[vertex1] && this.adjacencyList[vertex2]) {
             this.adjacencyList[vertex1] = this.adjacencyList[vertex1].filter(item => item !== vertex2);
             this.adjacencyList[vertex2] = this.adjacencyList[vertex2].filter(item => item !== vertex1);
         }
    }

    removeVertex(vertex) {
        if(this.adjacencyList[vertex]) {
            for (let v of this.adjacencyList[vertex]) {
                this.adjacencyList[v] = this.adjacencyList[v].filter(item => item !== vertex);
            }
            delete this.adjacencyList[vertex]            
        }
    }

    dfsRecursive(vertex) {
        if (!this.adjacencyList[vertex]) return undefined;
        let result = [];
        let visited = {};
        let graph = this.adjacencyList;

        (function dfs(vertex){
            if (!vertex) return;
            visited[vertex] = true;
            result.push(vertex);
            for (let value of graph[vertex]) {
                if (!visited[value]) dfs(value);
            }
        })(vertex)
        
        return result;
    }

    dfsIterative(vertex) {
        let stack = [];
        let result = [];
        let visited = {};
        let currentVertex;
        stack.push(vertex);
        visited[vertex] = true;
        while (stack.length) {
            currentVertex = stack.pop();
            result.push(currentVertex);
            this.adjacencyList[currentVertex].forEach(neighbor => {
                if (!visited[neighbor]) {
                    stack.push(neighbor)
                    visited[neighbor] = true;
                }
            });
        }
        return result;
    }

    bfs(vertex) {
        let queue = [];
        queue.push(vertex);
        let result = [];
        let visited = {};
        visited[vertex] = true;
        let currentVertex;

        while(queue.length) {
            currentVertex = queue.shift();
            result.push(currentVertex);
            this.adjacencyList[currentVertex].forEach(neighbor => {
                if (!visited[neighbor]) {
                    queue.push(neighbor);
                    visited[neighbor] = true;
                }
            });
        }
        return result;       
    }
}

let g = new Graph();
g.addVertex("a");
g.addVertex("b");
g.addVertex("c");
g.addVertex("d");
g.addVertex("e");
g.addVertex("f");
g.addEdge("a", "b");
g.addEdge("a", "c");
g.addEdge("b", "d");
g.addEdge("c", "e");
g.addEdge("d", "e");
g.addEdge("d", "f");
g.addEdge("e", "f");

//            a
//          /   \
//         b     c
//         |     |
//         d --- e
//          \   /
//            f
```