#Graph #Algorithm #data-structure 

Adjacency list is a technique used to represent a [[graph]]. The graph is represented using an array of [[linked list]], where each index of the array represents an [[vertices]]/node and each element of the [[linked list]] represents the adjacent [[vertices]].

However, adjacency list can be easily implemented using Array of [[vector in c++|vectors]] from [[standard template library(STL)]] in [[c++]]

### Example: Undirected unweighted graph using adjacency list

![[IMG_0705.jpeg]]

```
0-> 1 -> 4
1-> 0 -> 4 -> 3
2-> 1 -> 3
3-> 4 -> 1 -> 2
4-> 0 -> 1 -> 3
```
**Adjacency list representation using array of vectors: (undirected unweighted graph)**
```cpp
#include<iostream>
#include<vector>
using namespace std;


void addEdge(vector<int> graph[],int u, int v){
        graph[u].push_back(v);
        graph[v].push_back(u);//not applicable for directed graph
}

void printGraph(vector<int> graph[], int n){ //Print the adjacent vertices of a graph
        for(int i=0;i<n;i++){
                cout<<"Adjacency list of node"<<i<<":";
                for(int j=0;j<graph[i].size();j++){
                cout<<"->";
                cout<< graph[i][j];

                }
                cout <<endl;
        }
}
int main(){
  int v=5;
  vector<int>adj[v];
  addEdge(adj, 0, 1);
  addEdge(adj, 0, 4);
  addEdge(adj, 1, 2);
  addEdge(adj, 1, 3);
  addEdge(adj, 1, 4);
  addEdge(adj, 2, 3);
  addEdge(adj, 2, 4);
  addEdge(adj, 3, 4);

  printGraph(adj, v);

  return 0;
}
```


