# The (Apparent) Gibbs energy equation from the elements



$$
G(T,P) = G_0(T_r,P_r) - \int_{T_r}^T S(T,P_r)dT + \int_{P_r}^P V(T,P)dP \label{ref1}
$$
where the subscript $r$ denotes reference conditions (298.15 and 1 bar). It is implicit that the first integral is done at constant pressure ($P_r$) and the volume integral at a constant temperature different from $T_r$. Note that this expression is written differently in most common thermodynamic databases such as the ones from Hollan and Powell, that involve enthalpy, the one presented here seems more natural.

The computed $G(T,P)$ values are apparent because the entropy and heat capacity of the forming elements of the mineral phase is not considered and it complicates the computation in that it is unnecessary for phase equilibria computations (because )only relative differences are necessary. Remember however that the retrieved values are not absolute and therefore cannot be directly compared to other absolute computations such as those done with first principle calculations.

## Reference Gibbs energy 

One common source of confusion comes from different conventions about the $G_0(T_r,P_r)$ in the above expression (referred to in Perple_X by J. Connolly as SUPCRT and HSC convection). The confusion comes when even the same authors used different conversions for different versions of the datasets (such as in the case of hp02ver.dat = SUPCRT and hp11ver.dat = HSC, both by Holland and Powell). For the convection used in other datasets see https://www.perplex.ethz.ch/perplex_thermodynamic_data_file.html

##### SUPCRT convention

$$G_0 = H_f(T_r,P_r) - T_r·S(T_r,P_r)$$

Remember that the enthalpy of formation assumes by convection that the enthalpy of formation from the elements in its stable form is zero ($H_f =H(T_r,P_r) - H^{elements}(T_r,P_r) $). The same is not true for the entropy of formation but in the SUPCRT convection, the entropy of formation of the elements is considered to be zero as well.

##### HSC convention

$$ G_f(T_r,P_r) = H_f(T_r,P_r) - T_r·\left (S(T_r,P_r) - S^{elements}(T_r,P_r) \right )$$

Note that here the reference Gibbs energy is properly speaking the Gibbs energy of formation $G_f$ because it uses $S_f =S(T_r,P_r) - S^{elements}(T_r,P_r) $.

In most cases the experimental reference energy is obtained adiabatically and corresponds to the enthalpy of formation, this is the reason by it is tabulated as such in most datasets (usually the first column).

## Entropy integral and heat capacity

The reversible heat transfer at constant pressure is enthalpy and can be measured experimentally at different temperatures which is usually expressed as a polynomial function (see below).

$$
 C_P (T,P_r) = \left (\frac{\partial H}{\partial T} \right )_{P_r} \equiv \frac{dH}{dT} 
$$
 We can relate this experimental value to entropy by noting that at constant pressure that $ dH = TdS - VdP$ becomes $dH=TdS$, and $dS = \frac{dH}{T}$, therefore we can express the heat capacity in terms of entropy variations 

$$C_P = \frac{TdS}{dT} $$, thus having a way to compute $S$ if a reference $S$ is used from the expression $dS = \frac{C_P}{T}dT$. Because the at 0 K the entropy of a perfect crystal is zero, the reference entropy ($S^0$, or third law entropy) is defined as the integral from 0 K to $T_r$ (298.15),

$$
\int_0^{T_r} dS = S - 0 = S^0 (T_r,P_r) = \int_0^{T_r} \frac{C_P}{T}dT
$$
The third law entropy can be measured by cryogenic calorimetry, but this technique is not able to measure residual configurational entropy so a more general expression for the reference entropy (and that can be derived from equilibrium experiments, as we will be done this week) is

$$
S (T_r,P_r) =S^{conf} +  \int_0^{T_r} \frac{C_P}{T}dT
$$
because $C_P$ is measured at ambient conditions ($P_r$) it is implicit that the above integration is done over a constant pressure $P_r$.

So the entropy integral is expressed as,

$$ - \int_{T_r}^T S(T,P_r)dT = -\int_{T_r}^T \left [S(T_r,P_r) + \int_{T_r}^T \frac{C_P}{T}dT \right]dT = - (T-T_r)·S_{T_r,P_r} - \int_{T_r}^{T}\left[\int_{T_r}^{T} \frac{C_p}{T}dT \right]dT$$

integrating by parts the double integral results in

$$ - \int_{T_r}^T S(T,P_r)dT = - T·S(T_r,P_r)+ T_r·S(T_r,P_r) - T\int_{T_r}^{T}\frac{C_p}{T}dT +\int_{T_r}^{T}C_p dT $$

that when plugged in the main expression [$\ref{ref1}$] gives

$$G(T,P) = G_0(T_r,P_r) - S(T_r,P_r)T+ S(T_r,P_r)T_r - T\int_{T_r}^{T}\frac{C_p}{T}dT +\int_{T_r}^{T}C_p dT + \int_{P_r}^P V(T,P)dP $$

noting that the reference Gibbs energy is expressed in the SUPCRT convention as  

$$G_0 = H_f(T_r,P_r) - T_r·S(T_r,P_r)$$

the term $- S(T_r,P_r)T_r$ cancel out living the innocent expression appearing in most books and early papers by Holland and Powell. In his thermo notes, J. Connolly refers to this as a *perverse* formulation.

$$
G(T,P) = H_f(T_r,P_r) - T·S(T_r,P_r) - T\int_{T_r}^{T}\frac{C_p}{T}dT +\int_{T_r}^{T}C_p dT + \int_{P_r}^P V(T,P)dP \label{ref5}
$$
I think the perversion comes from the fact that it might be not so obvious how to reach [$\ref{ref5}$] from [$\ref{ref1}$] , especially to people like me that forgot how to make integration by parts to solve for the double entropy integral. For those like me,
$$
\int_a^b uv'dx = [uv]_a^b -\int_a^b u'vdx
$$
so if you take $u = \int Cp/T$ and $v=T$,
$$
\int_{T_r}^{T}\left[\int_{T_r}^{T} \frac{C_p}{T}dT \right]dT =  T\int_{T_r}^{T}\frac{C_p}{T}dT -\int_{T_r}^{T}C_p dT
$$

## The volume term	

We need still to bring the volume term to pressures higher than 1 bar. This is accomplished by using different Equations of States (EoS). Here I derive the most simple one but in practice, we will use another popular one in geosciences (Murnaghan EoS).

#### Isobaric expansion

It is defined as (in units of 1/K) 
$$
\alpha = \frac{1}{v}\left(\frac{\partial v}{\partial T} \right)
$$
The simplest approach is to assume that $\alpha$ and 1 bar is constant and independent of temperature. If so, we can solve for $v$ (here the small letters denote specific properties, molar volume in this case). Remember also that volume needs to be expressed in energy units (J/bar/mol) so when multiplied by pressure gives Joules.

## Implementation in Perple_X

In Perple_X the Gibbs energy of a phase is expressed using several equations of states. In this course, we will use one of the simplest ones (EoS = 2) with normal polynomials for $\alpha$, $C_P$, $K_T$ and Murnaghan type EoS for $V$ (Holland & Powell 1998).

### Heat capacity

Only $c_1,c_2,c_3,c_5$ are used

$$C_P(T,P_r) = c_1 + c_2·T + c_3/T^2 + c_4·T^2 + c5/\sqrt T + c_6/T + c_7/T^3 + c_8·T^3$$

so for EoS = 2

$$C_P(T,P_r) = c_1 + c_2·T + c_3/T^2 + c5/\sqrt T$$

### Murnaghan equation for volume

#### Isobaric thermal expansivity

From an **experimental** point of view, the isobaric expansivity is found by fitting volumetric data at 1 bar over a temperature range,



We start with the isobaric expansivity ($\alpha$),
$$
\alpha (T,P_r) = b_1 + b_2·T + b_3/T + b_4/T^2 + b_5/\sqrt T
$$
Only $b_1,b_5,b_6,b_7$ are used


$$
\alpha (T,P_r) = b_1 + b_5/\sqrt T
$$
Note that in PerpleX $b_5$ is redundant $b_5 = -10b_1$, this simplification is taken from Pawley et al. (1996), where $b_1 = \alpha_0$ and $ b_5 = -10\alpha_0$.
$$
\alpha = \alpha_0(1-10T^{-1/2})
$$
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