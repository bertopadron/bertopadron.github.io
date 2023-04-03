# Advanced Petrology

I will try to keep this alive by leaving you here the material we will be using in the class. 



The repository of Jupyter notebook can be found in https://github.com/bertopadron/test4Students



## An introduction to Schreinemakers analyses

Some website that might be useful 

* A rather complete exposition of the Schreinamkers analyses can be found in https://serc.carleton.edu/research_education/equilibria/schreinemakers.html

* A refresh of the phase rule https://serc.carleton.edu/research_education/equilibria/phaserule.html Note a (unintentional?) typo in the section relative to the derivation of the phase rule



#### Phase rule

In our notation, the phase rule is written as

$$
f + p = k + 2
$$
where $f$ is degree of freedom (or variance), $p$ is phase and $k$ is number of independent components in the system (more traditionally written as $c$ but that I will avoid for some subtle reasons).

Although is not conventional I would write the number of phases for invariant ($f=0$), univariant ($f=1$), divariant ($f=2$) and f-variant equilibria as $p_0$, $p_1$,$p_2$ and $p_f$. So for a 2 component system ($k=2$), $p_0 =4 $, $p_1 = 3$, $p_2 = 2$ and $p_f = 4 -f$, where $f$ is comprised between $[0,k+1]$. 



#### Combinatorial formula

It is possible to compute all potential equilibria of any degree of freedom ($n$) by using the combinatorial formula, where $p_f$ elements are taken from a set of $p$ phases,
$$
\left(\frac{p}{p_f} \right) = \frac{p!}{p_f!(p-p_f)!}
$$

##### 1-component system

Write all possible reactions for a given set of phases ($p$), lets consider all potential reactions among 3 phases.

* for an invariant equilibrium $p_0 = 3$, so there is only one way of taken 3 phases among 3 phases.
* for an univariant equilibrium $p_1 = 2$, so there are 3 ways of taken 2 phases among 3 phases.
* for a divariant equilibrium $p_2 = 1$, so there are 3 ways of taken 1 phase among 3 phases.

