

# Issue
My axolotl tank does not have a cooling unit. And bought solutions are expensive or not closed loop. room temp is a bit high for them. 

safe temps: 61-65F
comfortable up to 68F

my tank sits at 72.5F in spring, which is a bit warm.

If we are building something, make it have 2 independent sockets GFCI  (NEMA 6-50) for heater and cooler. 
# 3 Stage Design

I have an old ice maker (Frigidaire counter top) that is non  potable due to corrosion.  Can use this as a cooling unit. Could use an ice bucket with water too. Doesn't really matter what the cold water reservoir is. 

Stick a submersible pump in the reservoir, and pump fluid to a 316 stainless cooling coil in the tank. Then on the outlet side of the coil returns to the ice machine, and sprays over the accumulated ice in the basket. Could do 25-50% antifreeze for its anti corrosive properties as well. If ice doesn't form that's fine.  It will still cool since the ice maker will cool the water. Downside to antifreeze is a leak at all will probably kill the dude. vs tap water leaks less damaging to everything. 

Use Ras Pi Pico W and max31855 thermocouple amps to have temp control of the aquarium.  one TC by the cooling coil, and one by the filter.  PI or bang bang is fine for control.  With a cutout of 55F at the cooling coil so we don't freeze the lil dude. 

Silicon to ensure water doesn't enter control box or fuses / breakers / GFCI outlets on the box, need 

The Pico will have hardcoded setpoints and calibrations, defaults. But will have a small protocol to read and write data to the system. 

Eventually have a .NET Blazor application hosted on my server that I can write setpoints, calibrations, and other data to the Pico.  and periodically read and graph the two temperature measurements at an adjustable interval. InfluxDB probably in this stack as well. 

Due to deadline to get working cooler,  build in a few stages / milestones. 
## manual control

Get the cooling circuit functional and built.  Have the ability to engage the pump by plugging it in And maybe a switch.  Maybe a cheapo thermometer in the tank. This way we can keep the dude cool quickly.
## Pico controller with network command script

Get schematics of the control box. Get embedded control on Pico.  Have simple protocol for sending new data to the Pico for setpoints and calibration. Use max31855 prebuilt breakouts (the nice ones with extra filtering, not the bare breakouts). Need to find a GFCI outlet where i can have separate power sources for each socket, I know there are non GFCI outlets like this. Hot on each plug is through a relay controlled by Pico, GPIO vs relay voltage might be an issue, transitsor and proto board might be the way.  Need a 120VAC to 5VDC and maybe a 3.3V Out Buck converter for the Pico power.  Fusing / breakers maybe. Due to running heaters / motors need to decide on fast blow or slow blow. The transformer circuit might be the limiter, and fuse to that. 

Power to control box via standard IEC C13/C14 power cable and plug.

should expose the debug pins to a terminal block on outside of control box to reflash as needed. 
debug terminal block on top of control box,  and thermocouples coming out of bottom. With a lot of silicone sealing the bottom, as the TCs will be in the tank. 

have network settings in own file outside repo. (no leaked secrets).  See if we can use CMAKE to inject these settings into the code or something at compile time. 
### network command script
no rocket surgery here, just a simple .NET console app that speaks in the same protocol, has some hardcoded settings. 

when script is run it dumps settings to the Pico and then polls at a set interval the readouts of the Pico to standard out in inf loop. 

shoot for the new ..NET 10 scripting feature here. One file to rule them all. 

## .NET Blazor web control 
Have a few simple pages. 
- TC calibration / settings / debug info / gains
- setpoint and current readings
	- poll rate adjustment here
- graph view

All settings and setpoints should save somewhere, probably a JSON DTO.  On boot of service it should attempt to connect to Pico and assert settings to it. the Pico has no storage or non volatile. memory.  

Have configurable polling time for background graphing, and for the active page readout. Need to ensure that the service is always active and not just when open in a browser. 