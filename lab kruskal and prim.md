```cpp
_________________________________________

Kruskal’s Algorithm
_________________________________________

#include<iostream>
#include<vector>
#include <tuple>
#include<algorithm>

using namespace std;

const int MAX=1e5;
int parent[MAX];

void makeSet(int n){
    int i;
    for(i=0;i<n;i++){
        parent[i]=i;
    }
}

int findSet(int x){
    if(x!=parent[x]){
        parent[x]=findSet(parent[x]);
    }
    return parent[x];
}

void unionSets(int x, int y){
    int rootX=findSet(x), rootY=findSet(y);
    if(rootX!=rootY){
        parent[rootX]=rootY;
    }
}

void kruskal(vector<tuple<int, int, int>>& graph, int n) {
    sort(graph.begin(), graph.end()); // Sort by weight
    makeSet(n);
    cout << "Minimum Spanning Tree:" << endl;

    for(auto& [weight, u, v] : graph) {
        if(findSet(u) != findSet(v)) {
            cout << u << " " << v << endl; // Print edge part of MST
            unionSets(u, v);
        }
    }
}


int main(){
    int n, e, i, u, v, w;;
    cout<<"Enter the number of vertices : ";
    cin>>n;
    cout<<"Enter the number of edges : ";
    cin>>e;

    vector<tuple<int, int, int>> graph;
    cout<<"Enter the value as vertex1 vertex2 weight "<<endl;

    for(i=0;i<e; i++){
        cin>> u >> v >> w;
        graph.emplace_back(w, u,v);
    }

    kruskal(graph, n);

    return 0;
}


_________________________________________

Prim’s Algorithm
_________________________________________

#include<iostream>
#include<vector>
#include <tuple>
#include<algorithm>

using namespace std;

const int MAX=1e5;
int parent[MAX];

void makeSet(int n){
    int i;
    for(i=0;i<n;i++){
        parent[i]=i;
    }
}

int findSet(int x){
    if(x!=parent[x]){
        parent[x]=findSet(parent[x]);
    }
    return parent[x];
}

void unionSets(int x, int y){
    int rootX=findSet(x), rootY=findSet(y);
    if(rootX!=rootY){
        parent[rootX]=rootY;
    }
}

vector<pair<int, int>> primAlgorithm(int n, vector<tuple<int, int, int>>& edges) {
    int weight, u, v;
    vector<pair<int, int>> mstEdges; // Store MST edges

    sort(edges.begin(), edges.end()); // Step 1: Sort edges based on their weights

    makeSet(n);// Step 2: Initialize parent array

    for(auto edge : edges){   // Step 3: Iterate through each edge
        tie(weight, u, v) = edge; // Extract edge information

        if(findSet(u) != findSet(v)){  // Step 4: Check if it creates a cycle
            unionSets(u, v);
            mstEdges.emplace_back(u, v);
        }
    }

    return mstEdges;
}

int main(){
    int n, e, i, u, v, w;
    cout<<"Enter the number of vertices : ";
    cin>>n;
    cout<<"Enter the number of edges : ";
    cin>>e;

    vector<tuple<int, int, int>> graph;
    cout<<"Enter the value as vertex1 vertex2 weight "<<endl;

    for(i=0;i<e; i++){
        cin>> u >> v >> w;
        graph.emplace_back(w, u,v);
    }

    vector<pair<int, int>> mstEdges = primAlgorithm(n, graph);

    cout << "Edges of the Minimum Spanning Tree:" << endl;
    for(auto edge : mstEdges){
        cout << edge.first << " - " << edge.second << endl;
    }

    return 0;
}
```
