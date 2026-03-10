# Ultiprint
A CoreXY 3d printer with an ACM enclosure and 300x300x360mm build volume. It has 3 point ABL when a probe is mounted, and can do sensorless/endstopless homing with a TMC2209.
<img width="777" height="700" alt="image" src="https://github.com/user-attachments/assets/6e60d6b1-c809-48ab-9a39-d887c5a3ea0a" />

My aims for the project were to design a 3d printer that could print materials I didn't have access to printing before. I wanted to design something with an enclosure, as I think that looked cool. 3 point auto bed levelling was also something I wanted to explore mechanically in being able to handle tilt of the print bed with out restricting motion. 

**Note:** The prices in the BOM are for the products, but when added to cart there are a number of deals, coupons etc that bring the price well under $350. I also have the remaining components at home already.

# About
### Frame
The frame is made of 2020 T slot profiles in a cube like structure with 90 degree brackets to hold it together. The profiles used for the Y axis can be raised or lowered to provide more clearance if it is needed when using a different hotend or if more clearance is needed for filament to run through a drilled hole in the top panel. Linear rails are mounted on the underside to allow the X axis to move back and forth. On the X carriage the blower fan blows air into the duct to cool both the nozzle and the part.

### Motion
The printer uses a standard CoreXY system with stacked belts, meaning there is no need for a belt crossover. The belts attach to the extruder by lopping around and being held with belt clamps. This is the belt path:
<img width="474" height="521" alt="image" src="https://github.com/user-attachments/assets/1f431335-3a0f-49fa-9de7-aed1c167958b" />

For the Z axis, there are 3 3d printed brackets that each hold smooth rods and leadscrews. This moves the three bed support brackets. The beds sits on the support brackets in a similar manner to the Vcore 3.1, where threaded steel balls attached to the bed sits on metal dowels in the brackets. When a z probe is attached, the print can use 3 point auto bed levelling. 

### Electronics
For the motherboard, I am using a PCB motherboard I designed a while ago (reduces cost). It is based on the Mega2560 and A4988 (or other driver of same footprint) drivers. The electronics (motherboard + display) are housed external to the enclosure in a small box. The box can be mounted onto the back on an ACM panel or sit standalone. The cables run through a drilled hole in the panel and then go their destination.
<img width="655" height="384" alt="image" src="https://github.com/user-attachments/assets/63cb0cf2-4cec-45dc-8ecd-44137e8a9e55" />
<img width="645" height="394" alt="image" src="https://github.com/user-attachments/assets/a052aa6f-885b-404f-b8f2-fc39dfec88b0" />

### Firmware
There is a full zipped marlin build in the firmware folder above. Additionally, I pasted the files that I had to edit to support my custom board. I added a custom board to boards.h, then made a full pin mapping in pins_ULTIPRINT.h, and tweaked the config and config adv files.


