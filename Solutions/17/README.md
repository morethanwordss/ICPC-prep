## Theory
<pre>
Assume you have an array A[N].
Create another array prefixSum[N] where prefixSum[i] = Sum (A[0] to A[i])
Now, considering r > l
prefixSum[r] - prefixSum[l] = Sum (A[0] to A[r]]) - Sum (A[0] to A[l])
                            = Sum (A[l + 1] to A[r])
__________________________________________________________
0                                                        r
____________________________
0                          l
                            _______________________________
                            l + 1                         r
So, Sum (A[l] to A[r]) = prefixSum[r] - prefixSum[l - 1]
If l == 0,
Sum (A[l] to A[r]) = Sum (A[0] to A[r]) = prefixSum[r]
  
</pre>
## Solution
```cpp
#include<bits/stdc++.h>
using namespace std;

#define fastIO ios_base::sync_with_stdio(false);cin.tie(NULL);cout.tie(NULL);

int32_t main() { fastIO

    int n; cin >> n; int arr[n];
    for (int i = 0; i < n; i ++) cin >> arr[i];

    for (int i = 1; i < n; i ++) arr[i] += arr[i - 1]; // prefix sum

    int t; cin >> t; while (t --) {
        int l, r; cin >> l >> r;
        if (l == 0) cout << arr[r] << "\n";
        else cout << arr[r] - arr[l - 1] << "\n";
    }
        
}

```
