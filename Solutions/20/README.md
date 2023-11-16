## Theory
<pre>
Let,
ss1 = 2212112
ss2 = 2112112112

Our target is to do the following simulation:
Rule: if matches, length = number of x + size of ss2
We have  to find out the minimum length

22212112
||||||||
xxxxxxxx2112112112xxxxxxxx

 22212112
 ||||||||
xxxxxxxx2112112112xxxxxxxx

  22212112
  ||||||||
xxxxxxxx2112112112xxxxxxxx

   22212112
   ||||||||
xxxxxxxx2112112112xxxxxxxx

    22212112
    ||||||||
xxxxxxxx2112112112xxxxxxxx

     22212112
     ||||||||
xxxxxxxx2112112112xxxxxxxx

      22212112
      ||||||||
xxxxxxxx2112112112xxxxxxxx

       22212112
       ||||||||
xxxxxxxx2112112112xxxxxxxx

        22212112
        ||||||||
xxxxxxxx2112112112xxxxxxxx

         22212112
         ||||||||
xxxxxxxx2112112112xxxxxxxx

          22212112
          ||||||||
xxxxxxxx2112112112xxxxxxxx

           22212112
           ||||||||
xxxxxxxx2112112112xxxxxxxx

            22212112
            ||||||||
xxxxxxxx2112112112xxxxxxxx

             22212112
             ||||||||
xxxxxxxx2112112112xxxxxxxx

              22212112
              ||||||||
xxxxxxxx2112112112xxxxxxxx

               22212112
               ||||||||
xxxxxxxx2112112112xxxxxxxx

                22212112
                ||||||||
xxxxxxxx2112112112xxxxxxxx

                 22212112
                 ||||||||
xxxxxxxx2112112112xxxxxxxx

                  22212112
                  ||||||||
xxxxxxxx2112112112xxxxxxxx
</pre>

## Solution
```cpp
#include <iostream>
using namespace std;

#define fastIO ios_base::sync_with_stdio(false);cin.tie(NULL);cout.tie(NULL);

int main() { fastIO
    string ss1, ss2; cin >> ss1 >> ss2;
    if (ss1.size() > ss2.size()) swap(ss1, ss2);

    string ss = "";
    for (int i = 0; i < ss1.size(); i ++) ss += 'x';
    ss += ss2;
    for (int i = 0; i < ss1.size(); i ++) ss += 'x';

    int mnsize = ss1.size() + ss2.size();

    for (int i = 0; i < ss2.size() + ss1.size(); i ++) {
        bool possible = true;
        int x_count = 0;
        for (int j = i; j < i + ss1.size(); j ++) {
            if (ss[j] == 'x') x_count ++;
            if (ss[j] == '2' && ss1[j - i] == '2') {
                possible = false;
                break;
            }
        }
        if (possible) mnsize = min(mnsize, x_count + (int)ss2.size());
    }
    cout << mnsize << "\n";

        
}
```
