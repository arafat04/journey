For a function of a line, the slope is the division between the change between $y$ coordinates and the change between $x$ coordinates.

$$
  slope = \frac{\Delta(y)}{\Delta(x)}
  \tag{1}
  \label{eq:slope-delta}
$$

$$
  slope = \frac{y_2 - y_1}{x_2 - x_1}
  \tag{2}
  \label{eq:slope-two-point}
$$

For a line, there is only one slope, we need to take any two points on the line and can calculate the slope and this slope is the slope for the entire line. But for a curve, each point will have different slope, the slope will change everytime based on the point along the curve. The slope of a point on the curve is the slope of the tangent line touching that point.

However, if we want to find a slope at a point on a curve, we can not find a slope for a single point as we need two points to calculate the slope. To solve this problem, we can take another point on the curve not too far from the intial point. The reason we . For instance we can take another point along the x axis that is close to the initial point $x_0$, let's say h distance from it. So the two points on the x axis are $x_0$ and $x_0 + h$. As we need to find the slope for the $x_0$, we can take limit where h will approach to 0 and we will finally can get the slope of the point $x_0$ when h is really small like .00001 or something like this. For a function $f(x)$:

$$
f^{\prime}(x) = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}
\tag{3}
\label{eq:slope-derivative}
$$


Here $f^{\prime}(x)$ is another function because the slope changes at every x value and this is the derivative of the initial function $f(x)$. The derivative function $f^{\prime}(x)$ of the function $f(x)$ gives the slope of the original function at any point along the curve. And $h$ is the difference between $x_0+h$ and $x_0$. The derivative of the function of the curve is the slope of the curve at any point.

The equation in \(\ref{eq:slope-derivative}\) initially gives the slope of the secant line between two points on the curve. To get the slope at any point $x_0$, the $h$ needs to be very close to 0. This limiting equation is the exactly same if we took the derivative of the original function at the first place. So for any value of $x$, the original function will give the corresponding y axis coordinate for the curve, but the derivative will give the slope of the function at that given point.

Resources that are helpful to understand this and used to make this note:

[Derivative as slope of a tangent line | Taking derivatives | Differential Calculus | Khan Academy](https://www.youtube.com/watch?v=ANyVpMS3HL4)

[Calculating slope of tangent line using derivative definition | Differential Calculus | Khan Academy](https://www.youtube.com/watch?v=IePCHjMeFkE)

[The derivative of f(x)=x^2 for any x | Taking derivatives | Differential Calculus | Khan Academy](https://www.youtube.com/watch?v=HEH_oKNLgUU)
