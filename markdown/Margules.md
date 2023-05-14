### A brief introduction to ideal and regular solutions

If one wants not to get lost with solid solutions is better to start from definitions (I am copying here the notes from the course of James Connolly). The most fundamental equation is the gibbs energy of a (non-ideal) mixture (in units of J/mol, here is mol of the solid solution as given in the arbitrarily defined structural formulae,)
$$
g = g^{mechanical} + g^{configurational} + g^{excess}
$$
The real complication here (and source of confusion) is the configuration energy. It is confusing because *ideal* mixing is far from being obvious as it is not known *a priori* if you are mixing in crystallographic sites or you are mixing molecules (where the original definition of activity and classic thermodynamics is coming). In the case that the pure endmembers do not have configuration entropy themselves (this happens in albite), the configuration energy is defined as,

$$
g^{conf}= RT\sum_{i=1}^n \sum_{j=1}^{m_i} q_i z_{ij}\ln z_{ij}
$$
where $q_i$ is the number of sites of the i-th type (also called mutiplicity), $m_i$ is the number of kinds of atoms mixing on the i-th type, and $z_{ij}$ is the atomic fraction of the j-th type of atom mixing on the i-th identisite. **The problem here is that the definition is not given in terms of mole fraction of the endmember $y_i$ but atomic site fractions $z_{ij}$. **

For olivine, if you assumed that there is only one type of octahedral site ($i=1=M$) (crystallographers will argue that this can not be the case...), you have only one site with a multiplicity of 2 ($q_M =2$), $m_M =2$ (two kind of atoms mixing in $M$) and it is straightforward to relate mole fraction of the endmemeber and atomic site fractions. So $z_{M,Fe} = y_{fa}$ and $z_{M,Mg} = y_{fo}$​, that leaves the traditional expression.

$$
g^{conf}= RT(2 y_{fo}\ln y_{fo} + 2 y_{fa}\ln y_{fa})
$$

### Excess energy

Then the excess energy is defined for a 2-compoenent end member (note that in this definition the Margules term is defined in terms of fayalite and forsterite endmember **not Fe and Mg in atoms**)
$$
g^{excess} = W_{fofa}y_{fo}y_{fa}
$$
So the gibbs energy of the solution is

$$
g = y_{fo}g_{fo}^o + y_{fa}g_{fa}^o + RT(2 y_{fo}\ln y_{fo} + 2 y_{fa}\ln y_{fa}) + W_{fofa}y_{fo}y_{fa}
$$

### Definition of gibbs energy of a endmember in a solid solution

Before getting to the derivation of activity you need to solve for the gibbs energy of the end member, for instances forsterite $g_{fo}$, this is found as

$$
g_{fo} = g + (1-y_{fo})\frac{\part g}{\part y_{fo}}
$$
Once you know $g_{fo}$, the activity is

$$
a_{fo} = exp\left( \frac{g_{fo}-g_{fo}^o}{RT} \right)
$$
I wrote a python script to do the symbolic calculation in Jupyter (see link in the previous page), the activity is

$$
a_{fo} = y_{fo}^2exp\left( \frac{Wy_{fo}^2-2Wy_{fo}+W}{RT} \right)
$$
That can be simplified as usual as,

$$
RT\ln a_{fo} = 𝑅𝑇 \ln y_{fo}^2 + W(1-y_{fo})^2
$$
Which is the same as in the classical papers (please note that sometimes people use W for the exchange per atom, but in the above definition it is taken per mole of atoms exchanged in the structural formula, therefore 2 in olivine)

