## Theory
<pre>
-> x1, y1 is the lower left point 
-> x2, y2 is the upper right point
-> All rectangles are parallel to the X axis and Y axis

keep track of the current intersection's 
1) rightest left point -> x_left
2) leftest right point -> x_right
3) highest low point   -> y_low
4) lowest up point     -> y_up

if x_left is in the right side of x_right or if y_low is above y_up,
then all of these rectangles don't have any common intersecting area

width of the intersecting area  = x_right - x_left
height of the intersecting area = x_up - x_low

area of the intersecting area = width * height
</pre>
## Solution
```cpp
#include<bits/stdc++.h>
using namespace std;

#define fastIO ios_base::sync_with_stdio(false);cin.tie(NULL);cout.tie(NULL);

int32_t main() { fastIO
    int testCase; cin >> testCase; for (int i = 0; i < testCase; i ++) {

        cout << "Case " << i + 1 << ": ";

        // initially the intersection area is the largest, it will gradually get smaller
        int x_left = INT_MIN, y_low = INT_MIN, x_right = INT_MAX, x_up = INT_MAX; 
        int x_lowerLeft, y_lowerLeft, x_upperRight, y_upperRight;

        int n; cin >> n; for (int i = 0; i < n; i ++) {
            cin >> x_lowerLeft >> y_lowerLeft >> x_upperRight >> y_upperRight;
            x_left  = max(x_left, x_lowerLeft);
            x_right = min(x_right, x_upperRight);
            y_low   = max(y_low, y_lowerLeft);
            x_up    = min(x_up, y_upperRight);
        }
        int width  = x_right - x_left;
        int height = x_up - y_low;

        if (width < 0 || height < 0) cout << 0 << "\n";
        else cout << width * height << "\n";
    }
}
```
