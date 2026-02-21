These concepts are very helpful to understand gradient descent and backprogation algorithm.

### Slope of a curve

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

### Chain Rule:

The chain is the main essence that is needed for getting the derivative of the loss function with respect to the parameters of the problem. The derivative of the loss function is needed for gradient descent and backpropagation algorithm.

The chain rule helps us to get the derivative of a function with respect to a parameter when the function is not directly connected to the parameter but it is connected with it by one or more than one intermediary parameters. For instance, if we think this way that, the more we do physical work, the more we feel tired, and the more we feel tired, we want to take more rest. Here if we want to see the relationship between physical work with taking rest:

$$
  \frac{dRest}{dWork}
$$
it is not directly connected with the physical work. However, it is connected with feeling tired and feeling tired is directly connected with the physical work. So we can use the "chain" as the mean to get our desired derivative. So,

$$
  \frac{dRest}{dWork} = \frac{dRest}{dTired} \dot \frac{dTired}{dWork}
$$

Chain rule can be understood with this derivative of the log problem:

$$
  \frac{d}{dx} log(1+x^2)
$$

We know that derivative of $log(x)$ is $\fract{1}{x}. However, the value inside the parentheses is not directly $x$. But we can consider it as x and as it is not the exact $x$, we can take the derivative of the inner part again to get the final derivative. So, let assign the value inside the parentheses $z$ and take the derivative of the log w.r.t $z$, and then again we can take the derivative of the $z$ w.r.t $x$.

$$
  z = 1 + x^2
  \frac{d}{dx} log(1+x^2) = \frac{d}{dz} log(z) \dot \frac{dz}{dx}
$$

$$
  \frac{d}{dx} log(1+x^2) = \frac{1}{z} \dot \frac{d}{dx}(1+x^2)
$$

$$
  \frac{d}{dx} log(1+x^2) = \frac{1}{z} \dot 2x
$$

Finally we have to replace the value of $z$ with the value we substituted it with. So the final result:

$$
  \frac{d}{dx} log(1+x^2) = \frac{1}{1+x^2)} \dot 2x
$$

This is the essence of the chain rule. We need to put things in the parentheses and we can take the derivative as a chain fashion.

These online resource by Josh Starmer is very helpful to understand this:

[The Chain Rule, Clearly Explained!!!](https://www.youtube.com/watch?v=wl1myxrtQHQ)
