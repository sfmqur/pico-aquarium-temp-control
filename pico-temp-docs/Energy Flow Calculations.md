Need to decide how feasible that this prototype is. How much energy/power can we remove from the tank.  or the cooling power of the ice maker.  This might be difficult due to the phase change, but could put a certain amount of room temp water into the ice maker, and measure the mass of ice creation over time. 

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
4. once the ice maker fans turn off, record the time elapsed and reset the stopwatch
5.  once the ice dumps into basket, measure mass of created ice
6. dump measured ice into sink. removing that mass from system. 
7.  jump to step 3

## data
start mass 918g water at 55

with the addition of water after step 1, where the ice maker already sucked up the 10.88C water. Then the 284g of water was added. This yielded a tank temp at start of step 2 of: 
$(284*19.38 + 872*10.88)/{1156} = 12.96 C$

| sample no | start $T_{w}$  \[C] | $\Delta t$  \[sec] | ice mass \[g] | $H_{2}O$  $\Delta  T_{w}$ \[C] | $H_{2}O$ mass left \[g] |
| --------- | ------------------- | ------------------ | ------------- | ------------------------------ | ----------------------- |
| 1         | 13.27               | 495                | 46            | -2.38                          | 872                     |
|           | add                 | water              |               | (284g 19.38C)                  |                         |
| 2         | 10.88               | 475                | 49            | -1.35                          | 1107                    |
| 3         | 11.61               | 518                | 50            | -1.66                          | 1057                    |
| 4         | 9.94                | 502                | 52            | -1.27                          | 1005                    |
| 5         | 8.66                | 520                | 54            | -0.94                          | 951                     |

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


| sample no | $E_{i}$ \[kJ] | $E_{w}$ \[kJ] | $E_{t}$ \[kJ] | $P_{avg}$ \[W] |
| --------- | ------------- | ------------- | ------------- | -------------- |
| 1         | 17.9          | 8.69          | 26.6          | 53.8           |
| 2         | 18.6          | 6.26          | 24.9          | 52.3           |
| 3         | 19.1          | 7.34          | 26.5          | 51.1           |
| 4         | 19.5          | 5.34          | 24.9          | 49.6           |
| 5         | 20.0          | 3.74          | 23.7          | 45.6           |

## conclusion

It seems that the ice maker can only do about 50W of cooling. The one thing that this experiment doesn't consider is that the ice is left in the system. Although I don't think that matters too much,  as our goal was to establish the total cooling power of the system. 
# calculation of heat conduction into tank. 
use conductivity equation
$q=(k/s)A dT$
q = heat transfer (W, Btu/hr)
k = thermal Conductivity of material W/k \* K
s = material thickness (m)
A = heat transfer area ($m^2$)

$k_{glass}$ = 1.05 (@ 25C)
$k_{air}$ = 0.0262
s = 4.25 mm

## tank area
24Wx12.25Dx15H in
for the 4 walls,
A = 24x15x2+15x12.25x2 = 1087.5 $in^2$ = 0.702 $m^2$

the air pocket at top of tank conducts heat 2 magnitudes slower than walls, on top of the plastic layer of 2 mm. so we will ignore that. 

## energy calc

$q = 173 dT$ 
$\frac{dq}{dT} = 173 \left[ \frac{W}{K}\right]$  = $96.1 \left[ \frac{W}{F}\right]$
This will be the energy flow into the tank based on the delta temperature. 

or our ability to reduce tank temp is
$$\frac{q_{cooling}}{96.1} = \Delta T [F]$$




# Conclusions
Unfortunately I don't think this will work well. As we have about 50W of cooling. This will give us about 0.5F temperature delta between the tank and the room temp. In summer it might get as warm as 75 in the upstairs. So seeing a temp delta of 5F would be good. On the other hand.  Can build an open loop version with  the cooling coil and submersible pump, and aquarium tubing for about $40.  Which is some cooling. And experimentally see what the actual temp delta is at. 
Could also insulate the back side of the tank with something like styrofoam. Then the conduction area would be reduced much further. 