<pre>
  <strong>
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

(iii) is the equation of the straight line that goes through the intersection points of then two circle
solving eq (i) and (iii), (iii) -> (i):

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

then, using (iii) ->
X1 = const1 + Y1.const2
X2 = const1 + Y2.const2

these two are the intersecting points, BUT: 
if (X1 == X2 && Y1 == Y2):
    There's only one intersecting point
  </strong>
</pre>
