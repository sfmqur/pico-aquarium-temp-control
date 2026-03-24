Need to decide how feasible that this prototype is. How much energy/power can we remove from the tank.  or the cooling power of the ice maker.  This might be difficult due to the phase change, but could put a certain amouunt of room temp water into the ice maker, and measure the mass of ice creation over time. 

# ice maker generation 
need to figure out the cooling power of the ice maker
quick experiment to figure out ice generation over time. 

## assumptions
- ice temperature is 0C = 32F
	- while ice can be lower, this is conservative, as its fresh ice
## procedure
1. put 918 g of water into ice maker to start
2. start the ice maker on large cubes and start stopwatch
3. record initial water temp
4. once the ice maker fans turn off record the time elapsed and reset the stopwatch
5.  once the ice dumps shortly after into basket measure mass of created ice
6. dump measured ice into sink. removing that mass from system. 
7.  jump to step 3

## data

| sample no | start $T_{w}$  \[C] | $\Delta t$  \[sec] | ice mass \[g] | $H_{2}O$  $\Delta  T_{w}$ \[C] | $H_{2}O$ mass left \[g] |
| --------- | ------------------- | ------------------ | ------------- | ------------------------------ | ----------------------- |
| 1         |                     |                    |               |                                |                         |
| 2         |                     |                    |               |                                |                         |
|           |                     |                    |               |                                |                         |
|           |                     |                    |               |                                |                         |
|           |                     |                    |               |                                |                         |
|           |                     |                    |               |                                |                         |
|           |                     |                    |               |                                |                         |

## analysis
It seems that the water is chilled as well, not just ice creation.  This is good as we have a phase change and temp reduction of the water reservoir. 

specific heat of water
$c_w = 4.186 \frac{J}{g * C}$
Latent heat of melting for water 
$L_{w} = 334 \frac{J}{g}$ 

to create ice we have
$T_{st}$ = start temperature
$T_{f}$ = final temp: start temp of next sample
$m_{i}$ = ice mass created
$m_{w}$ = water mass remaining

The energy to make ice is 
$E_{i}=c_{w}m_{i}T_{st} +L_{w}m_{i}$

The energy for the water temp change is
$E_{w} = c_{w}m_{w}\Delta T_{w}$

Total cooling energy is
$E = E_{i} + E_{w}$


| sample no | $H_{2}O$  $\Delta  T$ \[C] | $\Delta E$ \[kJ] | $P_{avg}$ \[W] |
| --------- | -------------------------- | ---------------- | -------------- |
|           |                            |                  |                |
|           |                            |                  |                |
|           |                            |                  |                |
|           |                            |                  |                |
|           |                            |                  |                |
|           |                            |                  |                |

## conclusion


# calculation of heat conduction into tank. 

## Assumptions
- 