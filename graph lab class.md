```cpp
______________________________________
Creating a graph (Undirected Graph)
______________________________________

#include<iostream>
#include<vector>

using namespace std;

void addEdge(vector<int> adj[], int u, int v){
    adj[u].push_back(v); // Add v to u's list
    adj[v].push_back(u); // Add u to v's list for undirected graph
}

void printGraph(vector<int> adj[], int V){
    int i;
    for(i=0;i<V;i++){
        cout<<"\nAdjacency list of vertex " << i ;
        for(auto j: adj[i]){
            cout<<"-> "<<j;
        }
        cout<< endl;
    }
}

int main(){
    int V=5;
    vector<int> adj[V];

    addEdge(adj, 0, 1);
    addEdge(adj, 0, 4);
    addEdge(adj, 1, 2);
    addEdge(adj, 1, 3);
    addEdge(adj, 1, 4);
    addEdge(adj, 2, 3);
    addEdge(adj, 2, 4);
    addEdge(adj, 3, 4);

    printGraph(adj, V);

    return 0;
}

______________________________________
Creating a graph (Directed Graph)
______________________________________

#include<iostream>
#include<vector>

using namespace std;

void addEdge(vector<int> adj[], int u, int v){
    adj[u].push_back(v); // Add v to u's list
    //adj[v].push_back(u); // Add u to v's list for undirected graph
}

void printGraph(vector<int> adj[], int V){
    int i;
    for(i=0;i<V;i++){
        cout<<"\nAdjacency list of vertex " << i ;
        for(auto j: adj[i]){
            cout<<"-> "<<j;
        }
        cout<< endl;
    }
}

int main(){
    int V=5;
    vector<int> adj[V];

    addEdge(adj, 0, 1);
    addEdge(adj, 0, 4);
    addEdge(adj, 1, 3);
    addEdge(adj, 1, 4);
    addEdge(adj, 2, 1);
    addEdge(adj, 2, 3);
    addEdge(adj, 3, 4);
    addEdge(adj, 4, 2);


    printGraph(adj, V);

    return 0;
}

______________________________________________________________
Print the degree of each vertex for an undirected graph
______________________________________________________________
#include<iostream>
#include<vector>

using namespace std;

void addEdge(vector<int> adj[], int u, int v){
    adj[u].push_back(v); // Add v to u's list
    adj[v].push_back(u); // Add u to v's list for undirected graph
}

void printGraph(vector<int> adj[], int V){
    int i;
    for(i=0;i<V;i++){
        cout<<"\nAdjacency list of vertex " << i ;
        for(auto j: adj[i]){
            cout<<"-> "<<j;
        }
        cout<< endl;
    }
}

void printDegree(vector<int> adj[], int V){
    int i;
    for(i=0; i<V; i++){
        cout << "Degree of vertex " << i << " is " << adj[i].size() << endl;
    }
}

int main(){
    int V=5;
    vector<int> adj[V];

    addEdge(adj, 0, 1);
    addEdge(adj, 0, 4);
    addEdge(adj, 1, 2);
    addEdge(adj, 1, 3);
    addEdge(adj, 1, 4);
    addEdge(adj, 2, 3);
    addEdge(adj, 2, 4);
    addEdge(adj, 3, 4);


    cout << "\nDegrees of all vertices:\n";

    printDegree(adj, V);

    return 0;
}

______________________________________________________________

Find the min degree of an undirected graph
______________________________________________________________

#include<iostream>
#include<vector>

using namespace std;

void addEdge(vector<int> adj[], int u, int v){
    adj[u].push_back(v); // Add v to u's list
    adj[v].push_back(u); // Add u to v's list for undirected graph
}


void findMinDegree(vector<int> adj[], int V){
    if(V == 0) {
        cout << "Graph is empty!" << endl;
        return;
    }
    int minDegree = adj[0].size();
    for(int i=1; i<V; i++){
        if(adj[i].size() < minDegree){
            minDegree = adj[i].size();
        }
    }
    cout << "Minimum degree of the graph is " << minDegree << endl;
}

int main(){
    int V=5;
    vector<int> adj[V];

    addEdge(adj, 0, 1);
    addEdge(adj, 0, 4);
    addEdge(adj, 1, 2);
    addEdge(adj, 1, 3);
    addEdge(adj, 1, 4);
    addEdge(adj, 2, 3);
    addEdge(adj, 2, 4);
    addEdge(adj, 3, 4);

   findMinDegree(adj, V);

    return 0;
}

______________________________________
Disjoint Set (Basic)
______________________________________

#include<iostream>
using namespace std;
const int MAX = 1e5; // Adjust size as needed
int parent[MAX]; // Stores the parent of each element
void makeSet(int n){
    int i;
    for(i=1;i<=n;i++){
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
    int rootX= findSet(x);
    int rootY= findSet(y);

    if(rootX != rootY){
        parent[rootX]=rootY; // Attach rootX under rootY
    }
}

int main(){
    int i, n=7;
    makeSet(n);

    unionSets(1,2);
    unionSets(2,3);
    unionSets(4,5);
    unionSets(6,7);
    unionSets(5,6);
    unionSets(3,7);

    for(i=1; i<=n; i++){
        cout << "Element: " << i << " -> Set: " << findSet(i) << endl;
    }

    return 0;
}

______________________________________
Disjoint Set (Union by Rank)
______________________________________
#include<iostream>
using namespace std;

const int MAX=1e5;
int parent[MAX];
int ranking[MAX];

void makeSet(int n){
    int i;
    for(i=1;i<=n;i++){
        parent[i]=i;
        ranking[i]=0;
    }
}

int findSet(int x){
    if(x!=parent[x]){
        parent[x]=findSet(parent[x]); // Path compression
    }
    return parent[x];
}

void unionSets(int x, int y){
    int rootX=findSet(x);
    int rootY=findSet(y);

    if(rootX!=rootY){
        if(ranking[rootX]<ranking[rootY]){
            parent[rootX]=rootY;
        }
        else if(ranking[rootX]>ranking[rootY]){
            parent[rootY]=rootX;
        }
        else{
            parent[rootY]=rootX;
            ranking[rootX]=ranking[rootX]+1;
        }
    }
}

int main(){
    int i, n=7;
    makeSet(n);

    unionSets(1,2);
    unionSets(2,3);
    unionSets(4,5);
    unionSets(6,7);
    unionSets(5,6);
    unionSets(3,7);

    for(i=1; i<=n; i++){
        cout << "Element: " << i << " -> Set: " << findSet(i) << endl;
    }

    return 0;
}
```