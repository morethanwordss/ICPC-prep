## Theory
<pre>
Trick: the way the books are put in the shelf, the front page appears at the right side and the last page appears at the left.

c -> starting volume no.
d -> stopping volume no.

if the worm goes from left to right->

    *   a -> thickness of a volume without cover
        number of volumes = (d - c - 1)
        route length for volumes = (d - c - 1) * a

    *   b -> thickness of the cover
        number of covers = 2 * (d - c) 
        route length for covers = 2 * (d - c) * b

    *   total route length = (d - c - 1) * a + 2 * (d - c) * b


if the worm goes from right to left ->

    *   a -> thickness of a volume without cover
        number of volumes = (c - d + 1)
        route length for volumes = (c - d + 1) * a


    *   b -> thickness of the cover
        number of covers = 2 * (c - d)
        route length for covers = 2 * (c - d) * b

    *   total route length = (c - d + 1) * a + 2 * (c - d) * b

if the worms stays in the same volume ->

    *   route length = a (only 1 volume, no cover)
    *   which follows the eq for the worm going right to left
</pre>
## Solution
```cpp
#include<bits/stdc++.h>
using namespace std;

#define fastIO ios_base::sync_with_stdio(false);cin.tie(NULL);cout.tie(NULL);

int32_t main() { fastIO

    int a, b, c, d;
    cin >> a >> b >> c >> d;
    if (c >= d) cout << (c - d + 1) * a + 2 * (c - d) * b << "\n";
    else cout <<  (d - c - 1) * a + 2 * (d - c) * b << "\n";
        
}
```
