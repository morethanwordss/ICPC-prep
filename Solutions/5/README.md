## Solution:
```cpp
#include<bits/stdc++.h>
using namespace std;

#define fastIO ios_base::sync_with_stdio(false);cin.tie(NULL);cout.tie(NULL);

bool cmp(pair<int, int> pr1, pair<int, int> pr2) {
    return pr1.first > pr2.first;
}

int32_t main() { fastIO

        vector <pair <int, int>> pr;
        int n; cin >> n; while (n --) {
            int a, b; cin >> a >> b;
            pr.push_back({b, a});
        }

        stable_sort(pr.begin(), pr.end(), cmp);
        for (auto &x: pr) {
            cout << x.second << " " << x.first << "\n"; 
        }
}
```
