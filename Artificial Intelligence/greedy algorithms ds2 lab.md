#Algorithm 

```cpp
___________________________________________________
Fractional knapsack
___________________________________________________
#include<bits/stdc++.h>
using namespace std;

struct Item{
    int value, weight;
    double ratio; //v/w
};

bool compare(Item one, Item two){
    return one.ratio>two.ratio;
}

double fractionalKnapsack(int W, Item arr[], int N){
    sort(arr,arr+N,compare); // descending order
    int cap_left=W, i=0;
    double profit=0.0;

    while(cap_left>0 && i<N){
        if(cap_left>=arr[i].weight){
            profit=profit+ arr[i].value;
            cap_left=cap_left-arr[i].weight;
        }
        else{
            profit= profit+(arr[i].ratio*cap_left);
            cap_left=0;
        }
        i++;
    }
    return profit;
}

int main(){
    int W, N, i;
    cout<<"How many items? ";
    cin>>N;
    Item arr[N];
    cout<<"Enter the value and weight of each item: ";
    for(i=0;i<N;i++){
        cout<<"Item no "<<i+1<<" : ";
        cin>> arr[i].value>> arr[i].weight;
        arr[i].ratio= static_cast<double>(arr[i].value)/arr[i].weight;
    }
    cout<<"Enter the capacity of the sack: ";
    cin>>W;
    cout<<"Maximum profit: "<<fractionalKnapsack(W, arr, N)<<endl;

    return 0;
}


___________________________________________________
Activity Selection Problem
___________________________________________________

#include<bits/stdc++.h>
using namespace std;

void max_activity(int S[], int F[], int N){
    int i, j;
    cout<<"The following activities are selected: "<<endl;
    i=1;
    cout<<i;
    for(j=2;j<=N;j++){
        if(S[j]>=F[i]){
            cout<<" "<<j;
            i=j;
        }
    }
}

int main(){
    int n, i;
    cout<<"Enter the number of activities: ";
    cin>>n;
    int s[n], f[n];
    cout<<"Enter the starting time of the activities: "<<endl;
    for(i=1;i<=n;i++){
        cout<<"Starting time of activity "<<i<<" : ";
        cin>>s[i];
    }
    cout<<"Enter the finishing time of the activities: "<<endl;
    for(i=1;i<=n;i++){
        cout<<"Starting time of activity "<<i<<" : ";
        cin>>f[i];
    }
    max_activity(s,f,n);
    return 0;
}

___________________________________________________
Greedy Coin Change
___________________________________________________

#include<bits/stdc++.h>
using namespace std;

void min_coin_change(int Note){
    int num_of_coin, i, count;
    int coins[]={1000, 500, 100, 50, 20, 10, 5, 2, 1};
    num_of_coin=sizeof(coins) / sizeof(coins[0]);
    vector<int> change_coin;

    for (int i = 0; i <num_of_coin; i++) {
		while (Note >= coins[i]) {
			Note -= coins[i];
			change_coin.push_back(coins[i]);
		}
	}
    cout << "Minimum number of coins needed: " << change_coin.size() << "\n";
    cout << "Coins/notes: ";
    for (int coin : change_coin) {
        cout << coin << " ";
    }
}



int main(){
    int note;
    cout<<"Enter the amount you want to change: ";
    cin>>note;

    min_coin_change(note);
    return 0;
}
```