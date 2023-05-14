# The (apparent) Gibbs energy equation from the elements

These are some notes that I have recompiled for the *"Thermodynamic modeling course, a short course"* organized at Clermont-Ferrand, France (20-24 June 2022). These notes are compiled mostly following the notes from the James Connolly course at the ETH (www.perplex.ethz.ch/thermo_course), the Perple_X website (https://www.perplex.ethz.ch) and Holland and Powell (1998, Journal of Metamorphic Geology). Any error or misunderstanding is of mine. Rather than a comprehensive derivation of thermodynamic quantities, these notes are intended as a cheat sheet, that could we useful for your project at the end of the week. 

There is only **one** number (scalar) that rules all phase diagrams (assuming your variables are strictly pressure and temperature only), and I am still perplexed about the beauty resulting from it (*nothing but a scalar*). Although in detail the computation is rather sophisticated, the only important thing that feed the algorithm is the Gibbs energy of the potential phases at the specific $T$ and $P$ that can be stable given the compositional space of your system. The trick is then to find those phases (and their proportion) having [1] the lowest Gibbs energy and [2] satisfying a mass balance conservation equation **constrained** by the composition of the system. So the bricks of all this construction are the Gibbs energies of the phases that can be computed by integrating the differential equation, 
$$
dG = -SdT + VdP
$$
  which is,
$$
G(T,P) = G_0(T_r,P_r) - \int_{T_r}^T S(T,P_r)dT + \int_{P_r}^P V(T,P)dP \label{Gibbs}
$$
where the subscript $r$ denotes reference conditions (298.15 and 1 bar). It is implicit that the first integral is done at constant pressure ($P_r$) and the volume integral at a constant temperature different from $T_r$. Note that this expression is written differently in most common thermodynamic databases such as the ones from Holland and Powell but the expression [$\ref{Gibbs}$] seems more natural when coming from the definition of the Giggs function to describe isothermal, isobaric chemically closed systems ($G = U -TS +PV$).

The computed $G(T,P)$ values are say to be **apparent** because the entropy, volume and heat capacity of the elements forming the phase are not considered. The reason is because it makes computation hairy and because it is unnecessary for phase equilibria computations that need only relative differences. Remember however that the retrieved values are not absolute and therefore cannot be directly compared to other absolute computations such as those done with first principle calculations.

## Reference Gibbs energy 

One common source of confusion comes from different conventions about the $G_0(T_r,P_r)$ in [$\ref{Gibbs}$] (referred in Perple_X as SUPCRT and HSC convection). The confusion comes when even the same authors used different conversion for different version of the datasets (such as in the case pf hp02ver.dat = SUPCRT and hp11ver.dat = HSC, both by Holland and Powell). For the convection used in other datasets see https://www.perplex.ethz.ch/perplex_thermodynamic_data_file.html

##### SUPCRT convention

$$G_0 = H_f(T_r,P_r) - T_r·S(T_r,P_r)$$

Remember that the enthalpy of formation assumes that the enthalpy of formation from the elements in its stable form is by convection zero ($H_f =H(T_r,P_r) - H^{elements}(T_r,P_r) $). The same is not true for the entropy of formation but in the SUPCRT convection, the entropy of formation of the elements is considered to be zero as well.

##### HSC convention

$$ G_f(T_r,P_r) = H_f(T_r,P_r) - T_r·\left (S(T_r,P_r) - S^{elements}(T_r,P_r) \right )$$

Note that here the reference Gibbs energy is properly speaking the Gibbs energy of formation $G_f$ because it uses $S_f =S(T_r,P_r) - S^{elements}(T_r,P_r) $.

In most cases the experimental reference energy is obtained adiabatically and corresponds to the enthalpy of formation, this is the reason by it is tabulated as such in most datasets (usually the first column) and explains why enthalpy enters in other popular expression of [$\ref{Gibbs}$].

## Entropy integral and heat capacity

The reversible heat transfer at constant pressure is enthalpy and can be measured experimentally at different temperatures. It is usually expressed as a polynomial function (see below).

$$
 C_P (T,P_r) = \left (\frac{\partial H}{\partial T} \right )_{P_r} \equiv \frac{dH}{dT} 
$$
 We can relate this experimental value to entropy by noting that at constant pressure $ dH = TdS - VdP$ becomes $dH=TdS$, and $dS = \frac{dH}{T}$, therefore we can express the heat capacity in terms of entropy variations,

$$
C_P = \frac{TdS}{dT},
$$
thus having a way to compute $S$ from the expression,
$$
dS = \frac{C_P}{T}dT
$$
 if a reference $S(T_r,P_r)$ is known. Contrary to ther references in thermodynamic, the reference for entropy is absolute because the at 0 K the entropy of a perfect crystal is zero. This can be used to define the third law entropy ($S^0(T_r,P_r$)) as the integral from 0 K to $T_r$ (298.15),
$$
\int_0^{T_r} dS = S(T_r) - S(0) =  S^0 (T_r,P_r) = \int_0^{T_r} \frac{C_P}{T}dT
$$
The third law entropy can be measured by cryogenic calorimetry, but this technique is not able to measured residual configurational entropy so a more general expression for the reference entropy (and that can be derived from equilibrium experiments, as we will done this week) is

$$
S (T_r,P_r) =S^{conf} +  \int_0^{T_r} \frac{C_P}{T}dT
$$
because $C_P$ is measured at ambient conditions ($P_r$) it is implicit that the above integration is done over a constant pressure $P_r$.

So the entropy integral is expressed as,

$$ - \int_{T_r}^T S(T,P_r)dT = -\int_{T_r}^T \left [S(T_r,P_r) + \int_{T_r}^T \frac{C_P}{T}dT \right]dT = - (T-T_r)·S_{T_r,P_r} - \int_{T_r}^{T}\left[\int_{T_r}^{T} \frac{C_p}{T}dT \right]dT$$

integrating by parts the double integral results in

$$ - \int_{T_r}^T S(T,P_r)dT = - T·S(T_r,P_r)+ T_r·S(T_r,P_r) - T\int_{T_r}^{T}\frac{C_p}{T}dT +\int_{T_r}^{T}C_p dT $$

that when plugged in the main expression [$\ref{Gibbs}$] gives

$$
G(T,P) = G_0(T_r,P_r) - S(T_r,P_r)T+ S(T_r,P_r)T_r - T\int_{T_r}^{T}\frac{C_p}{T}dT +\int_{T_r}^{T}C_p dT + \int_{P_r}^P V(T,P)dP
$$
noting that the reference Gibbs energy is expressed in the SUPCRT convention as  

$$G_0 = H_f(T_r,P_r) - T_r·S(T_r,P_r)$$

the term $- S(T_r,P_r)T_r$ cancel out living the innocent expression appearing in most books and early papers by Holland and Powell. In his thermo notes, J. Connolly refer to this as *perverse* formulation.

$$
G(T,P) = H_f(T_r,P_r) - T·S(T_r,P_r) - T\int_{T_r}^{T}\frac{C_p}{T}dT +\int_{T_r}^{T}C_p dT + \int_{P_r}^P V(T,P)dP \label{ref5}
$$
I think the perversion comes from the fact that it might be not so obvious how to reach [$\ref{ref5}$] from [$\ref{ref1}$] , specially to people like me that forgot how to make integration by parts to solve for the double entropy integral. For those like me,
$$
\int_a^b uv'dx = [uv]_a^b -\int_a^b u'vdx
$$
so if you take $u = \int Cp/T$ and $v=T$,
$$
\int_{T_r}^{T}\left[\int_{T_r}^{T} \frac{C_p}{T}dT \right]dT =  T\int_{T_r}^{T}\frac{C_p}{T}dT -\int_{T_r}^{T}C_p dT
$$

## The volume term	

We need still to bring the volume term to pressures higher that 1 bar. This is accomplished by using different Equation of States (EoS). Here I derive the most simple one but in practice we will use another popular one in geosciences (Murnaghan EoS).

#### Isobaric expansion

It is defined as (in units of 1/K) 
$$
\alpha = \frac{1}{v}\left(\frac{\partial v}{\partial T} \right)_{P_r}
$$
The simplest approach is to assume that $\alpha$ and **1 bar** is constant and independent of temperature. If so, we can solve for $v$ (here the small letters denotes specific properties, molar volume in this case). Remember also that volume needs to be expressed in energy units (J/bar/mol) so when multiply by pressure gives Joules.
$$
\alpha dT = \frac{dv}{v}
$$

$$
\int_{T_r,1}^{T,1} \alpha dT = \int_{v(T_r,1)}^{v(T,1)} \frac{1}{v}dv
$$

Noting $v(T_r,1) = v_0$, we have,
$$
\alpha(T-T_r) = \ln v(1,T) - \ln v_0
$$
Then the volume at **1 bar** and T is
$$
v(T,1) = v_0 \exp(\alpha(T-T_r))
$$

#### Isothermal compressibility 

We can proceed similarly for the isothermal compressibility (i.e. assuming $\beta_T$ is a constant),
$$
\beta_T = -\frac{1}{v}\left(\frac{\partial v}{\partial P} \right)_{T}
$$
that is most commonly referred using its inverse, the bulk modus ($K_T$),
$$
K_T = -v\left(\frac{\partial P}{\partial v} \right)_{T}
$$

$$
v(T_r,P) = v(T_r,1) \exp(\beta_T(P-P_r))
$$

Taking both effect at the same time gives
$$
\int_{T_r,1}^{T,1} \alpha dT - \int_{T_r,P_r}^{T_r,P} \beta_T dP= \int_{v(T_r,P_r)}^{v(T,P)} \frac{1}{v}dv
$$

$$
v(T,P) = v_0 \exp(\alpha(T-T_r)-\beta_T(P-P_r))
$$

## Implementation in Perple_X

In Perple_X the molar Gibbs energy of a phase ($g$) is expressed using several equation of states. In this course we will use one of the simplest (EoS = 2) with normal polynomials for $\alpha$, $C_P$, $K_T$ and Murnaghan type EoS for $V$ (Holland & Powell 1998).

### Heat capacity

$$C_P(T,P_r) = c_1 + c_2·T + c_3/T^2 + c_4·T^2 + c5/\sqrt T + c_6/T + c_7/T^3 + c_8·T^3$$

Only $c_1,c_2,c_3,c_5$ are used for EoS = 2, so

$$
C_P(T,P_r) = c_1 + c_2·T + c_3/T^2 + c_5/\sqrt T
$$

### Murnaghan equation for volume

#### Isobaric expansivity

From an **experimental** point of view the isobaric expansivity is found by fitting volumetric data at 1 bar over a temperature range,

$$
\alpha = \left(\frac{\partial \ln v}{\partial T} \right)_{P_r}
$$
That it is fitted to a polynomial of the general time
$$
\alpha (T,P_r) = b_1 + b_2·T + b_3/T + b_4/T^2 + b_5/\sqrt T
$$
where only $b_1,b_5,b_6,b_7$ are used in EoS = 2,


$$
\alpha (T,P_r) = b_1 + b_5/\sqrt T
$$
Note that in PerpleX $b_5$ is redundant $b_5 = -10b_1$, 

then the volume at any temperature and 1 bar is computed as (note that we use the Taylor expansion approximation for small numbers where $\exp(x) \approx 1 +x $)

$$
V(T,P_r) = V_0·\left [1 + \int_{T_r}^{T}\alpha(T,P_r)dT \right]
$$

#### Isothermal bulk modulus

The isothermal bulk modulus at the temperature T and 1bar is,

$$K(T,P_r) = b_6 + b_7·(T-T_r) $$

equivalent to the HP98 expression,

$$K(T,P_r) = K(T_r)(1-1.5·10^{-4}(T-T_r))  $$

Note that $b_7$ is also redundant and equal to $b_7 = -b_6·1.5 ·10^{-4}$

### Volume at pressure and temperature

If the pressure derivative of the bulk modulus ($K'$) is positive ($K'$ = 4) we retrieve the Murnaghan equation,

$$
V(T,P) = V(T,P_r)·\left( 1 - \frac{4P}{4P + K(T,P_r)} \right)^{1/4}
$$
by changing the notation for the bulk modulus $K(T,P_r)$ as simply $K_T$, and making $P_r=1$
$$
V(T,P) = V(T,1)·\left( 1 - \frac{4P}{4P + K_T} \right)^{1/4}
$$
Now, in order to compute the energy contribution due to volume at T,P with need to integrate the above expression from 1 bar to P (see Holland and Powell 1998, page 312),
$$
\int_1^PV(T,P)dP= \frac{V(T,1)K_T}{3}\left [\left (1+\frac{4P}{K_T} \right)^{3/4}-1 \right]
$$
Now you have all the necessary knowledge to compute the apparent Gibbs energy of a **pure** mineral phase at any desired temperature and pressure conditions (EoS is expected to works at $P<10^5$ bar, $<10$ GPa), for higher pressure other more sophisticated EoS with thermal pressure correction effects, is needed (such as the one implemented by Holland and Powell, 2011, called Modified Tait equation of state). We will not dive into this business. 