# Estimation of $f\ce{O2}$ based on Fe-Mg exchange in olivine-orthopyroxene in magnetite buffered assemblages

This is based on the following equilibrium (see classic paper of Frost 1982, JPet)

$$ 6\ce{Fe_2SiO4} + \ce{O2} = 3\ce{Fe2Si2O6} + 2\ce{Fe3O4}$$ 			(1)

Oxygen fugacity can be expressed as follows

$$\log f\ce{O_2} = 3 \log a_{\ce{Fe2Si2O6}}^{opx} + 2 \log a_{\ce{Fe3O4}}^{mt} - 6\log a_{\ce{Fe2SiO4}}^{ol} + \Delta G°_1/ (\ln(10)·RT)$$                         [Eq. 1]

In order to derive this expression, let's start as

$$\Delta G^o + RT\ln K =0 $$

where 

$$ K = \frac{(a_{\ce{Fe2Si2O6}}^{opx})^3 + (a_{\ce{Fe3O4}}^{mt})^2}{ (a_{\ce{Fe2SiO4}}^{ol})^6+a_{\ce{O_2}}^{fl}}$$

and 

$$ RT\ln K = 3RT \ln a_{\ce{Fe2Si2O6}}^{opx} + 2RT \ln a_{\ce{Fe3O4}}^{mt} - 6RT\ln a_{\ce{Fe2SiO4}}^{ol} - RT\ln a_{\ce{O_2}}$$

the activity of $\ce{O_2}$ is

$$ \ln a_{\ce{O_2}} = 3 \ln a_{\ce{Fe2Si2O6}}^{opx} + 2 \ln a_{\ce{Fe3O4}}^{mt} - 6\ln a_{\ce{Fe2SiO4}}^{ol} + \Delta G°_1/RT $$ 

but we want $\log_{10}$ units instead so,

$$\log f\ce{O_2} = 3 \log a_{\ce{Fe2Si2O6}}^{opx} + 2 \log a_{\ce{Fe3O4}}^{mt} - 6\log a_{\ce{Fe2SiO4}}^{ol} + \Delta G°_1/ (\ln(10)·RT)$$                         [Eq. 1]

## Formal derivation

The above treatment is obscure in the definition of $\Delta G°_1$ because it is calculated at the P,T conditions for all endmembers except for $\ce{O2}$ that is computed at 1 bar. The derivation is as follows

$$ 6\ce{Fe_2SiO4} + \ce{O2} = 3\ce{Fe2Si2O6} + 2\ce{Fe3O4}$$ 			(1)

for this reaction in solid solution we have

$$3 g_{fs}^o + 2g_{mt}^o - 6g_{fa}^o - \mu _{\ce{O2}}^o + RT\ln K = 0$$ 

Which is strictly

$$\Delta G^o + RT\ln K =0 $$

then

$$3 g_{fs}^o + 2g_{mt}^o - 6g_{fa}^o - \mu _{\ce{O2}}^o + 3RT \ln a_{\ce{Fe2Si2O6}}^{opx} + 2RT \ln a_{\ce{Fe3O4}}^{mt} - 6RT\ln a_{\ce{Fe2SiO4}}^{ol} - RT\ln a_{\ce{O_2}}$$

but noting that

$$ \mu _{\ce{O2}} = \mu _{\ce{O2}}^o + RT\ln a_{\ce{O_2}} $$

that simplifies to

$$3 g_{fs}^o + 2g_{mt}^o - 6g_{fa}^o - \mu _{\ce{O2}} + 3RT \ln a_{\ce{Fe2Si2O6}}^{opx} + 2RT \ln a_{\ce{Fe3O4}}^{mt} - 6RT\ln a_{\ce{Fe2SiO4}}^{ol}$$

then

$$\mu _{\ce{O2}} = 3 g_{fs}^o + 2g_{mt}^o - 6g_{fa}^o + 3RT \ln a_{\ce{Fe2Si2O6}}^{opx} + 2RT \ln a_{\ce{Fe3O4}}^{mt} - 6RT\ln a_{\ce{Fe2SiO4}}^{ol}$$

we normally report this value as $f_{\ce{O2}}$, that by definition is

$$f_{\ce{O2}} = \exp(\frac{\mu _{\ce{O2}}-\mu _{\ce{O2}}^{1bar}}{RT})$$

$$f_{\ce{O2}} = \exp(\frac{{3 g_{fs}^o + 2g_{mt}^o - 6g_{fa}^o -\mu _{\ce{O2}}^{1bar} + 3RT \ln a_{\ce{Fe2Si2O6}}^{opx} + 2RT \ln a_{\ce{Fe3O4}}^{mt} - 6RT\ln a_{\ce{Fe2SiO4}}^{ol}}}{RT})  $$



$$f_{\ce{O2}} = \exp(\frac{3 g_{fs}^o + 2g_{mt}^o - 6g_{fa}^o -\mu _{\ce{O2}}^{1bar}}{RT}) + 3 a_{\ce{Fe2Si2O6}}^{opx} + 2a_{\ce{Fe3O4}}^{mt} - 6 a_{\ce{Fe2SiO4}}^{ol}  $$

or in $\ln$ units

$$\ln f_{\ce{O2}} = \frac{3 g_{fs}^o + 2g_{mt}^o - 6g_{fa}^o -\mu _{\ce{O2}}^{1bar}}{RT} + 3\ln a_{\ce{Fe2Si2O6}}^{opx} + 2\ln a_{\ce{Fe3O4}}^{mt} - 6\ln a_{\ce{Fe2SiO4}}^{ol}  $$

and more frequently ($\ln x = log_{10}x\ln(10))$

$$\log_{10} f_{\ce{O2}} \ln(10) = \frac{3 g_{fs}^o + 2g_{mt}^o - 6g_{fa}^o -\mu _{\ce{O2}}^{1bar}}{RT} + 3\ln a_{\ce{Fe2Si2O6}}^{opx} + 2\ln a_{\ce{Fe3O4}}^{mt} - 6\ln a_{\ce{Fe2SiO4}}^{ol}  $$

$$\log_{10} f_{\ce{O2}} = \frac{3 g_{fs}^o + 2g_{mt}^o - 6g_{fa}^o -\mu _{\ce{O2}}^{1bar}}{\ln(10)RT} + 3\log a_{\ce{Fe2Si2O6}}^{opx} + 2\log a_{\ce{Fe3O4}}^{mt} - 6\log a_{\ce{Fe2SiO4}}^{ol}  $$

which is Eq.1