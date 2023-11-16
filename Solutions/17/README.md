## Theory
<pre>
Assume you have an array A[N].
Now, consider a custom array arr[N],
where the value at the ith index represents the sum of elements from index 0 to i in array A, known as the 'prefix sum.'

Now, let's analyze the expression arr[r] - arr[l]:

arr[r] - arr[l] = sum of elements from 0th to rth - sum of elements from 0th to lth
                 = sum of elements from (l + 1)th to rth

However, the question requires the result to be inclusive of both l and r.
Therefore, the corrected expression is arr[r] - arr[l - 1].

But, there's a catch. What if l == 0?

If l == 0, then l - 1 becomes -1, causing arr[l - 1] to throw an error.
To address this, when l == 0, it implies the summation of all elements till index r.
In this case, simply print arr[r].
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
