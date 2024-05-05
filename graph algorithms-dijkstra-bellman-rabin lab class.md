```cpp
___________________________________________________

Dijkstra
___________________________________________________

#include <iostream>
#include <vector>
#include <queue>
#include <climits>

using namespace std;

void Dijkstra(const vector<vector<pair<int, int>>>& graph, int source, vector<int>& distances) {
    int V,distance, u, v, weight;
    V = graph.size();
    distances.assign(V, INT_MAX);
    distances[source] = 0;

    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
    pq.push({0, source});

    while (!pq.empty()) {
        distance = pq.top().first;
        u = pq.top().second;
        pq.pop();

        // If the distance is not the currently known shortest, skip it
        if (distance > distances[u]) {
            continue;
        }

        for (const auto& edge : graph[u]) {
            v = edge.first;
            weight = edge.second;

            if (distances[u] + weight < distances[v]) {
                distances[v] = distances[u] + weight;
                pq.push({distances[v], v});
            }
        }
    }
}

int main() {
    int V = 5;
    vector<vector<pair<int, int>>> graph(V);

    graph[0].emplace_back(1, 10);
    graph[0].emplace_back(4, 3);
    graph[1].emplace_back(2, 2);
    graph[1].emplace_back(4, 4);
    graph[2].emplace_back(3, 9);
    graph[3].emplace_back(2, 7);
    graph[4].emplace_back(1, 1);
    graph[4].emplace_back(3, 8);

    vector<int> distances;
    Dijkstra(graph, 0, distances);


    for (int i = 0; i < V; ++i) {
        cout << "Distance from 0 to " << i << ": " << distances[i] << endl;
    }

    return 0;
}

___________________________________________________
Bellman Ford
___________________________________________________

#include <iostream>
#include <vector>
#include <tuple>
#include <climits>

using namespace std;

bool BellmanFord(int V, int start, const vector<tuple<int, int, int>>& edges, vector<int>& distances) {
    int u, v, w;
    distances.assign(V, INT_MAX);
    distances[start] = 0;

    for (int i = 0; i < V - 1; ++i) {
        for (const auto& edge : edges) {
            tie(u, v, w) = edge;
            if (distances[u] != INT_MAX && distances[u] + w < distances[v]) {
                distances[v] = distances[u] + w;
            }
        }
    }

    for (const auto& edge : edges) {
        tie(u, v, w) = edge;
        if (distances[u] != INT_MAX && distances[u] + w < distances[v]) {
            return false;
        }
    }

    return true;
}

int main() {
    int V = 6;
    vector<tuple<int, int, int>> edges = {
        {0, 1, 6},
        {0, 2, 4},
        {0, 3, 5},
        {1, 4, -1},
        {2, 1, -2},
        {3, 2, -2},
        {3, 5, -1},
        {4, 5, 3}
    };

    vector<int> distances;
    bool hasSolution = BellmanFord(V, 0, edges, distances);

    if (hasSolution) {
        for (int i = 0; i < V; ++i) {
            cout << "Distance from source to vertex " << i << " is " << distances[i] << endl;
        }
    } else {
        cout << "The graph contains a negative weight cycle." << endl;
    }

    return 0;
}

___________________________________________________

Rabin-karp 
___________________________________________________

#include <iostream>
#include <cmath>
#include<cstring>
using namespace std;
#define d 256

void search(char pat[], char txt[], int q) {
    int M, N, i, j, p = 0, t = 0, h=1; // p and q hash value for pattern and text
    M = strlen(pat);
    N = strlen(txt);

    for (i = 0; i < M - 1; i++)
        h = (h * d) % q;

    // Calculate the hash value of pattern and first window of text
    for (i = 0; i < M; i++) {
        p = (d * p + pat[i]) % q;
        t = (d * t + txt[i]) % q;
    }

    // Slide the pattern over text one by one
    for (i = 0; i <= N - M; i++) {
        // Check the hash values of current window of text and pattern.
        // If the hash values match then only check for characters one by one
        if (p == t) {
            /* Check for characters one by one */
            for (j = 0; j < M; j++) {
                if (txt[i + j] != pat[j])
                    break;
            }

            // if p == t and pat[0...M-1] = txt[i, i+1, ...i+M-1]
            if (j == M)
                cout << "Pattern found at index " << i << endl;
        }

        // Calculate hash value for next window of text: Remove
        // leading digit, add trailing digit
        if (i < N - M) {
            t = (d * (t - txt[i] * h) + txt[i + M]) % q;

            // We might get negative value of t, converting it to positive
            if (t < 0)
                t = (t + q);
        }
    }
}

int main() {
    char txt[] = "GEEKS FOR GEEKS";
    char pat[] = "GEEK";
    int q = 101;
    search(pat, txt, q);
    return 0;
}
```