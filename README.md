# Robot

Big Goal: 6 axis robot arm. Hardware, software and docs.   
Current Goal: Finish the controller to drive a motor got from a kitchen mixer/blender (for some extra power). 

## What we have (very short overview)

A controller design. It's meant to control both speed and position of the motor, using 2 inputs:

   - IR Led <-> IR transistor counter mounted at the motor's fan - poor man's rotary encoder
   - Current sense through the rotor using the Atmega's ADC port connected to a 1ohm resistor in series with the rotor as measurement. (there's some extra circuitry to that - check out the schematics for details)

   and 2 outputs:

   - stator current flow direction (via the L6202 H-bridge) + PWM power control
   - PWM fed to a solid-state relay to control the power in the rotor


We've also printed the layout on a pcb (looking pretty nice, UV printing is really fine). Stuck on some details, that out of the sudden showed up just now.

Pictures below the questions section.


## Design Questions

* I'm using a phase sensing circuit made with an CNY74 optocoupler and two 22K resistors. I've seen various LED circuts powered from the mains. However they also had a capacitor [in there](http://www.extremecircuits.net/2010/07/mains-powered-white-led-lamp.html).  
Is my design safe, or should I modify anything? Also, will 0.5W resistors work?  

* The stator will be powered by ~40V @ 0.8 - 1 Amp. The track widths are 2.5mm @ 0.35um thickness. Are they too narrow to support that?



### Schematic
![Controller Schematic](http://griminal.net/robot/robot-power.jpg)

### Board Layout
![Board Layout](http://griminal.net/robot/robot-power-brd.jpg)

### Current looks of the board
![Front](http://griminal.net/robot/robot-board-front.jpg)
![Back](http://griminal.net/robot/robot-board-back.jpg)


