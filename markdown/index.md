# **A swift introduction to thermodynamic modelling (Part II)**

¡Hola!, this site will be dedicated to the last two days of the course and a place to download files. 

![Course logo](https://bertopadron.github.io/docs/assets/images/DALL_Lyell.png)

### The last challenge

You've learned quite a lot of things this week so I propose the following game.

After a long field campaign in the Antarctic, a bunch of petrologists from our PGG group brought a collection of 10 unusual samples (samples PGG23-01 to PGG23-10 ) from two sites but with no contextual information (i.e., *"xenoliths"*). Back in Granada (Armilla), they discovered that most of the samples contained significant amounts of an unknown element that they temporarily called X. 

Inspired by the discovery, members of the team wrote a proposal and after a year they got funded by a generous grant to constrain one of the two thermal gradients where the strategic element can be found for future explorations and (of course) revolutionize our current knowledge of the thermal state of the lithosphere.

You will start by looking at the petrological data (bulk rock chemistry, mineralogy and mineral chemistry of the 10 samples).

**Site 1** Samples from PGG23-01 to PGG23-05.

**Site 2** Samples from PGG23-06 to PGG23-10.

[XRF data](https://bertopadron.github.io/data/Geochemistry/XRF.xlsx) and [EPMA data](https://bertopadron.github.io/data/GeochemistryEPMA.xlsx). ([XRF](https://bertopadron.github.io/data/Geochemistry/XRF.numbers) and [EPMA](https://bertopadron.github.io/data/Geochemistry/EPMA.numbers) with Numbers format for Macs.

No more information is given (but as you know the PGG is excellently equipped with all experimental techniques necessary to accomplish the project). Your challenge is to discuss what kind of experimental data you would need to solve the puzzle.

Good luck!      

### NEWS!!! (1)

Here's the data that we managed to collect yesterday using just density measurements and X-ray diffraction data (cell paramters and Z number)

```
vic      EoS = 2 |                                                                   
X2O3(1)
G0 = -1560000 S0 = 49.9 V0 = 2.658  
c1 = 160.0 c2 = .600E-2 c3 = -2560600 c5 = -599.2  
b1 = .429E-4 b5 = -.429E-3 b6 = 2620000. b7 = -388 b8 = 4  
```

```
menz     EoS = 2                                                                    
MGO(3)X2O3(1)SIO2(3)
G0 =       S0 =         V0 = 8.318  
c1 = 600.0 c3 = -5100000 c5 = -4000.2 
b1 = .2500E-4 b5 = -.2500E-3 b6 = 2007000. b7 = -300.55 b8 = 4  
```

```
rom    EoS = 2                                                                   
MGO(1)X2O3(1)
G0 =       S0 =         V0 = 3.978  
c1 = 342.7 c2 = -.5037E-2 c3 = -2205100 c5 = -1678.1 
b1 = .431E-4 b5 = -.431E-3 b6 = 1945000. b7 = -291.75 b8 = 4 
```

### NEWS!! (2)

This is the calorimetric [data](https://bertopadron.github.io/data/Calorimetric_data/Calorimetric_data_1bar.csv) at high temperatures.

### NEWS!! (3)

This is the X-ray volume data at high [temperatures](https://bertopadron.github.io/data/X-ray_data/isobar-1bar.csv) and [high pressures](https://bertopadron.github.io/data/X-ray_data/isotherm-298K.csv).

### NEWS!! (4)

[Low temperature](https://bertopadron.github.io/data/Calorimetric_data/Calorimetry_vic_low_T.txt) colorimetric data for vicentite.

### Resources

* Here is a summary of the key expression needed to understand what is behind the scenes of a phase diagram ([click here)](https://bertopadron.github.io/Computing_gibbs_Granada.html).

* A few notes about the simplest solid solutions (ideal and regular). ([Clic here](https://bertopadron.github.io/Margules.html))

* An example of olivine as a simple non-ideal binary solid solution implemented in Python ([Clic here](https://bertopadron.github.io/forsterite_activity.html))

  

### Other unrelated resources 

* Oxygen fugacity based on Fe-Mg exchange in olivine-orthopyroxene in magnetite buffered assemblages ([Clic here](https://bertopadron.github.io/FFM_buffer.html)).

  

