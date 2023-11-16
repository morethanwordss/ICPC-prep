## Theory
<pre>
S = Square

Case 01:
S S
S S

Case 02:
S S S S

Case 03:
S
S
S
S

We can convert Case 03 into Case 02 by swapping the width with the height 
</pre>

## Solution
```c++
#include<bits/stdc++.h>
using namespace std;

#define fastIO ios_base::sync_with_stdio(false);cin.tie(NULL);cout.tie(NULL);

int32_t main() { fastIO

    while (true) {
        int testCase; cin >> testCase;
        if (testCase == 0) return 0;

        int maxSquareLength = -1;
        int paper = -1;

        for (int i = 0; i < testCase; i ++) {

            double width, height; cin >> width >> height;
            if (width < height) swap(width, height); // making width > height to convert it into Case 2: S S S S

            // Case 01
            double squareLength = height / 2.00;

            // Case 02
            if (width > 4 * height) squareLength = max(squareLength, height);
            else squareLength = max(squareLength, width / 4.00);


            if (maxSquareLength < squareLength) {
                maxSquareLength = squareLength;
                paper = i + 1;
            }
        }
        cout << paper << "\n";
    }   
}
```
