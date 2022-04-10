parts:

USB C breakout basic breakout board 
Used this one https://www.amazon.com/Type-C-Breakout-Serial-Connector-Converter/dp/B09KC1SMGD/
wiring:
```
For most usages, you can just connect VBUS to your 5V input, GND to ground, and D+ and D- as you expect. You can monitor the CC and SBU pins to determine cable polarity, or send side-band data. Or leave them disconnected
```

A USB 2.0 USB C cable to cut up
USB C to Micro usb can be gotten pretty cheap

choc v1 keyswitches

diodes


## Assembly Tips:

Must trim a very very slight amount off of the center pin on keyswitches over the body/thumbcluster rod

Body/ThumbCluster Pivot Rob
  - BodyThumbRod Cap gets glued on body end of rod
  - thumb cluster end of rod gets glued in place
  
Retain wire in thumb cluster with 2 dots of super glue

Area around the body/baseplate hinge needs clearence, so keep all wires to the other side of the keyswitch


### Wire lengths:

#### Body -> Baseplate
9 wires
420mm

#### Thumb -> Baseplate
6 wires
240mm
70mm threaded through



TODO: 
- redo wiring for bluemicro & to make wiring easier with controller position
- choose place for power switch by usb-c port, make it recessed

nice to haves
- latch to keep folded?
- latches to retain body/thumb extensions in base?


Animation:
BaseBodyAngle goes from 0 -> 32


Print Settings:
Supports on buildplate
Detect Bridging
100% infill
0.20mm
PLA/PETG



Body wire:
9 wires, 300mm
- 180mm should be put into the wire managers
- 120 should be free

Future: 
Attach trackpoint/ball or touchpad somewhere?


Friction fit redesign notes:
https://markforged.com/resources/blog/joinery-onyx
https://www.hubs.com/knowledge-base/how-design-snap-fit-joints-3d-printing/


firmware:
https://zmk.dev/docs/development/new-shield
https://zmk.dev/docs/development/setup/
https://zmk.dev/docs/troubleshooting
https://github.com/SolidHal/zmk


## Build ZMK
```
cd zmk
source zephyr/zephyr-env.sh
cd app
west build -b bluemicro840_v1 -- -DSHIELD=btrfld
```

make pristine
```
west build -p -b bluemicro840_v1 -- -DSHIELD=btrfld
```
