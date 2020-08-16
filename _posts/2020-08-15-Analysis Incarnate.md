---
title: 'Analysis Incarnate'
---

This is a quick proof of Euler's formula without the use of the Taylor Series. 

![a](https://latex.codecogs.com/png.latex?\dpi{300}&space;\tiny&space;e^{i\phi}&space;=&space;cos&space;\phi&space;&plus;&space;i&space;sin\phi)


Even with the imaginary number "i", this equation is differentiable, so we can take the derivative of :

![b](https://latex.codecogs.com/png.latex?\dpi{300}&space;\tiny&space;f(x)=\frac{e^{i\phi}}{cos\phi&plus;isin\phi})
<!--more-->
Using the quotient rule, we end up with : 

![c](https://latex.codecogs.com/png.latex?\dpi{300}&space;\tiny&space;f\prime(x)=\frac{(cos\phi&plus;isin\phi)ie^{i\phi}-e^{i\phi}(-sin\phi&plus;icos\phi)}{(cos\phi&plus;isin\phi)^{2}})

The derivative of f(x) being ie^(iphi), and the derivative of g(x) being e^(iphi). Let's focus on the numerator. Distributing the respective pairs, we get : 

![d](https://latex.codecogs.com/png.latex?\dpi{300}&space;\tiny&space;=e^{i\phi}(icos\phi-sin\phi&plus;sin\phi-icos\phi))

![e](https://latex.codecogs.com/png.latex?\dpi{300}&space;\tiny&space;=e^{i\phi}(0))

As you can see, the derivative of f(x)=0, and the only function whose derivative is zero is a constant. Let's call our constant "c". If we find a value for c, we know the value is the same for the entire equation, because it's a constant. If we plug "0" into the equation that we originally derived :

![f](https://latex.codecogs.com/png.latex?\dpi{300}&space;\tiny&space;f(0)=\frac&space;{e^{i0}}{cos0&plus;isin0}=\frac{1}{1})

After simplifying, we end up with (1/1), because e^(i0) is one, isin(0) is zero, and cos(0) is one. Since we know that "c" is a constant, the value of f(x) remains the same.

![g](https://latex.codecogs.com/png.latex?\dpi{300}&space;\tiny&space;f(x)=\frac&space;{e^{i\phi}}{cos\phi&plus;isin\phi}=1)

After we simplify, we are done :) 

![h](https://latex.codecogs.com/png.latex?\dpi{300}&space;\tiny&space;e^{i\phi}=cos\phi&plus;isin\phi)