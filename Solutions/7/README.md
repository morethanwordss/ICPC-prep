## Theory:
<pre>
Fermat's Last Theorem states that x ^ n + y ^ n = z ^ n has no integer solutions x, y, z, n for n greater than 2.
</pre>
## Solution:
```c++
#include<bits/stdc++.h>
using namespace std;

#define fastIO ios_base::sync_with_stdio(false);cin.tie(NULL);cout.tie(NULL);

int32_t main() { fastIO

    int n; cin >> n;
    if (n == 0 || n > 2) cout << -1 << "\n";
    else if (n == 1) cout << "1 2 3\n";
    else cout << "3 4 5\n";
}
```
