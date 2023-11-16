## Solution
```cpp
#include<bits/stdc++.h>
using namespace std;

#define fastIO ios_base::sync_with_stdio(false);cin.tie(NULL);cout.tie(NULL);

int32_t main() { fastIO
    int a, b, c, d; cin >> a >> b >> c >> d;
    if (a > c) {
        cout << a << "\n";
        return 0;
    }
    bool driverTurn = false;
    int res = a;
    while (true) {
        if(driverTurn) {
            if (c - d > a) {
                c -= d;
                driverTurn = false;
            }
            else {
                res = a;
                break;
            }
        }
        else {
            if(a + b < c) {
                a += b;
                driverTurn = true;
            }
            else {
                res = c;
                break;
            }
        }
    }
    cout << res << "\n";
}
```
