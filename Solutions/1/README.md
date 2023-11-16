## Theory
<pre>
(x - x1)^2 + (y - y1)^2 = r1^2 ........(i)
(x - x2)^2 + (y - y2)^2 = r2^2 ........(ii)

here, (x1, y1) is the center of the Circle 1 and r1 is its radius
and , (x2, y2) is the center of the Circle 2 and r2 is its radius

if (center1 == center2):
    if (radius1 == radius2): 
        The circles are the same
    else:
        No intersection
}
again, 
if (distance between two center > r1 + r2):
    they won't intersect

(i) -> x^2 - 2.x.x1 + x1^2 + y^2 - 2.y.y1 + y1^2 = r1^2
(ii) -> x^2 - 2.x.x2 + x2^2 + y^2 - 2.y.y2 + y2^2 = r2^2

(ii) - (i) ->
-> 0 - 2.x.(x2 - x1) + (x2^2 - x1^2) + 0 - 2.y.(y2 - y1) + (y2^2 - y1^2) = r2^2 - r1^2
-> - 2.x.(x2 - x1) - 2.y.(y2 - y1) = (r2^2 - r1^2) - (x2^2 - x1^2) - (y2^2 - y1^2)
-> x(x2 - x1) + y(y2 - y1) = ((r2^2 - r1^2) - (x2^2 - x1^2) - (y2^2 - y1^2)) / -2
-> x(x2 - x1) = (((r2^2 - r1^2) - (x2^2 - x1^2) - (y2^2 - y1^2)) / -2) - y(y2 - y1)
-> x = ((((r2^2 - r1^2) - (x2^2 - x1^2) - (y2^2 - y1^2)) / -2) - y(y2 - y1)) / (x2 - x1) 
-> x = ((r2^2 - r1^2) - (x2^2 - X1^2) - (y2^2 - y1^2)) / (-2.(x2 - x1)) + y.-(y2 - y1)/(x2 - x1)
-> x = const1 + y.const2 ........ (iii)

here, 
const1 = ((r2^2 - r1^2) - (x2^2 - x1^2) - (y2^2 - y1^2)) / (-2 * (x2 - x1))
const2 = - (y2 - y1) / (x2 - x1)

(iii) is the equation of the straight line that goes through the intersection points of the two circle.
solving eq (i) and (iii) we'll get the  intersection points.
    
Now, (iii) -> (i):
-> (const1 + y.const2)^2 - 2.(const1 + y.const2).x1 + x1^2 + y^2 - 2.y.y1 + y1^2 = r1^2
-> const1^2 + 2.const1.y.const2 + y^2.const2^2 - 2.const1.x1 - 2.y.const2.x1 + x1^2 + y^2 - 2.y.y1 + y1^2 = r1^2
-> y^2.(const2^2 + 1) + y.(2.const1.const2 - 2.const2.x1 - 2.y1) + (const1^2 - 2.const1.x1 + x1^2 + y1^2 - r1^2) = 0
-> A.Y^2 + B.Y + C = 0

here,
A = const2^2 + 1
B = 2.const1.const2 - 2.const2.x1 - 2.y1
C = const1^2 - 2.const1.x1 + x1^2 + y1^2 - r1^2

therefore, Y1 = (-B + sqrt(B^2 - 4AC)) / 2A
and,       Y2 = (-B - sqrt(B^2 - 4AC)) / 2A

using the eq (iii) ->
X1 = const1 + Y1.const2
X2 = const1 + Y2.const2

these two are the intersecting points, BUT: 
if (X1 == X2 && Y1 == Y2):
    There's only one intersecting point
</pre>

## Solution
```cpp
#include<bits/stdc++.h>
using namespace std;

#define fastIO ios_base::sync_with_stdio(false);cin.tie(NULL);cout.tie(NULL);
#define double long double

bool equals(double x, double y) {
    if (fabs(x - y) < 1e-3) return true;
    else return false;
}

double modif(double d) {
    long long intpart = d;
    d -= intpart;
    d *= 1000;
    long long floatpart = d;
    double res = intpart + (floatpart * 0.001);
    return res;
}


int32_t main() { fastIO

    double x1, y1, r1, x2, y2, r2;
    while(cin >> x1 >> y1 >> r1 >> x2 >> y2 >> r2) {
        bool swapped = false;
        if (x1 == x2 && y1 == y2) {
            if (r1 == r2) cout <<"THE CIRCLES ARE THE SAME\n";
            else cout << "NO INTERSECTION\n";
            continue;
        }
        if (sqrtl(pow((x1 - x2), 2) + pow((y1 - y2), 2)) > r1 + r2) {
            cout << "NO INTERSECTION\n";
            continue;
        }
        if (equals(x1, x2)) {
            swap(x1, y1);
            swap(x2, y2);
            swapped = true;
        }
        double const1 = ((pow(r2, 2) - pow(r1, 2)) - (pow(x2, 2) - pow(x1, 2)) - (pow(y2, 2) - pow(y1, 2))) / (-2 * (x2 - x1));
        double const2 = - (y2 - y1) / (x2 - x1);
        double A = pow(const2, 2) + 1; 
        double B = 2 * const1 * const2 - 2 * const2 * x1 - 2 * y1;
        double C = pow(const1, 2) - 2 * const1 * x1 + pow(x1, 2) + pow(y1, 2) - pow(r1, 2);
        double Y1 = (-B + sqrt(pow(B, 2) - 4 * A * C)) / (2 * A);
        double Y2 = (-B - sqrt(pow(B, 2) - 4 * A * C)) / (2 * A);
        double X1 = const1 + Y1 * const2;
        double X2 = const1 + Y2 * const2;
        if (swapped) {
            swap(X1, Y1);
            swap(X2, Y2);
        }
        X1 = modif(X1);
        X2 = modif(X2);
        Y1 = modif(Y1);
        Y2 = modif(Y2);
        if (equals(X1, X2) && equals(Y1, Y2)) {
            cout << "(" << 
            fixed << setprecision(3)  << X1 << "," << 
            fixed << setprecision(3) << Y1 <<")\n";
            continue;
        }
        pair <double, double> pr1 = {X1, Y1}, pr2 = {X2, Y2};
        if (pr1 > pr2) swap(pr1, pr2);
        cout << "(" << 
        fixed << setprecision(3) << pr1.first   << "," << 
        fixed << setprecision(3) << pr1.second << ")(" << 
        fixed << setprecision(3) << pr2.first << "," << 
        fixed << setprecision(3) << pr2.second << ")\n";
    }  
}
