### An expression to derive the definition of activity

```python
import numpy as np 
import sympy as sp
from sympy.interactive import printing 
printing.init_printing(use_latex = True)
```

Definition of symbolic variables


```python
g_fo_o,g_fa_o,y_fo,y_fa,T,R,W = sp.symbols('g_fo^o,g_fa^o,y_fo,y_fa,T,R,W')
```

Definition of gibbs energy of the olivine solid solution


```python
g = y_fo*g_fo_o + (1-y_fo)*g_fa_o + R*T*(2*y_fo*sp.log(y_fo) + 2*(1-y_fo)*sp.log(1-y_fo)) + W*y_fo*(1-y_fo)
```


```python
display(g)
```

$$
\displaystyle R T \left(2 y_{fo} \log{\left(y_{fo} \right)} + \left(2 - 2 y_{fo}\right) \log{\left(1 - y_{fo} \right)}\right) + W y_{fo} \left(1 - y_{fo}\right) + g^{o}_{fa} \left(1 - y_{fo}\right) + g^{o}_{fo} y_{fo}
$$


Definition of the gibss energy of forsterite in the olivine solid solution


```python
g_fo_ss = g + (1-y_fo)*sp.diff(g,y_fo)
display(sp.simplify(g_fo_ss))
```

$$
\displaystyle 2 R T \log{\left(y_{fo} \right)} + W y_{fo}^{2} - 2 W y_{fo} + W + g^{o}_{fo}
$$


# Definition of activity
Activity of forsterite is defined as the gibbs energy of the endmember in the solid solution (g_fo_ss $g_{fo}$) relative to the gibbs energy of the pure endmember forsterite $g_{fo}^o$

$$
a_{fo} = exp\left( \frac{g_{fo}-g_{fo}^o}{RT} \right)
$$


```python
a_fo = sp.exp((g_fo_ss-g_fo_o)/R/T)
sp.simplify(a_fo)
```

$$
\displaystyle y_{fo}^{2} e^{\frac{W \left(y_{fo}^{2} - 2 y_{fo} + 1\right)}{R T}}
$$


```python
print(sp.simplify(a_fo))
```

    y_fo**2*exp(W*(y_fo**2 - 2*y_fo + 1)/(R*T))


being awkwards the expression is usually expressed as $RT\ln a_{fo}$


```python
RTlna_fo = R*T*sp.log(sp.exp((g_fo_ss-g_fo_o)/R/T))
```


```python
sp.simplify(RTlna_fo)
```

$$
\displaystyle R T \log{\left(y_{fo}^{2} e^{\frac{W y_{fo}^{2} - 2 W y_{fo} + W + g_{fo} - g^{o}_{fo}}{R T}} \right)}
$$

Just note that


```python
sp.simplify(g_fo_ss-g_fo_o)
```

$$
\displaystyle 2 R T \log{\left(y_{fo} \right)} + W y_{fo}^{2} - 2 W y_{fo} + W
$$


```python
sp.collect(W*y_fo**2-2*W*y_fo+W,W)
```

$$
\displaystyle W \left(y_{fo}^{2} - 2 y_{fo} + 1\right)
$$

and that


```python
sp.factor(W*y_fo**2-2*W*y_fo+W,y_fo)
```

$$
\displaystyle W \left(y_{fo} - 1\right)^{2}
$$

so ,

$$
R T \ln{\left(a_{fo} \right)} = 2 R T \ln{\left(y_{fo} \right)} + \displaystyle W \left(y_{fo} - 1\right)^{2}
$$


