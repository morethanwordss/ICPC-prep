## Theory:
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
## Solution:
```cpp
#include<bits/stdc++.h>
using namespace std;

#define fastIO ios_base::sync_with_stdio(false);cin.tie(NULL);cout.tie(NULL);

void __print(int x) {cerr << x;}
void __print(long x) {cerr << x;}
void __print(long long x) {cerr << x;}
void __print(unsigned x) {cerr << x;}
void __print(unsigned long x) {cerr << x;}
void __print(unsigned long long x) {cerr << x;}
void __print(float x) {cerr << x;}
void __print(double x) {cerr << x;}
void __print(long double x) {cerr << x;}
void __print(char x) {cerr << '\'' << x << '\'';}
void __print(const char *x) {cerr << '\"' << x << '\"';}
void __print(const string &x) {cerr << '\"' << x << '\"';}
void __print(bool x) {cerr << (x ? "true" : "false");}

template<typename T, typename V>
void __print(const pair<T, V> &x) {cerr << '{'; __print(x.first); cerr << ','; __print(x.second); cerr << '}';}
template<typename T>
void __print(const T &x) {int f = 0; cerr << '{'; for (auto &i: x) cerr << (f++ ? "," : ""), __print(i); cerr << "}";}
void _print() {cerr << "]\n";}
template <typename T, typename... V>
void _print(T t, V... v) {__print(t); if (sizeof...(v)) cerr << ", "; _print(v...);}

#define __(x...) cerr << "[" << #x << "] = ["; _print(x)

int32_t main() { fastIO

    int a, b, c, d;
    cin >> a >> b >> c >> d;
    if (c >= d) cout << (c - d + 1) * a + 2 * (c - d) * b << "\n";
    else cout <<  (d - c - 1) * a + 2 * (d - c) * b << "\n";
        
}
```
