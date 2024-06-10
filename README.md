# LockTabletOnWindow
lock pointer device to a screen's portion

## Requirements
- xorg
- xinput

## Guide
### Select the device

➜  ~ xinput list       
⎡ Virtual core pointer                    	id=2	[master pointer  (3)] \
⎜   ↳ Virtual core XTEST pointer              	id=4	[slave  pointer  (2)] \
⎜   ↳ SEMITEK USB-HID Gaming Keyboard         	id=8	[slave  pointer  (2)] \
⎜   ↳ Logitech USB Receiver Consumer Control  	id=12	[slave  pointer  (2)] \
⎜   ↳ Logitech USB Receiver Mouse             	id=14	[slave  pointer  (2)] \
⎜   ↳ UC-LOGIC Tablet WP5540U Mouse           	id=16	[slave  pointer  (2)] \
⎜   ↳ UC-LOGIC Tablet WP5540U Pen Pen (0)     	id=18	[slave  pointer  (2)] \
⎣ Virtual core keyboard                   	id=3	[master keyboard (2)] \
    ↳ Virtual core XTEST keyboard             	id=5	[slave  keyboard (3)] \
    ↳ Power Button                            	id=6	[slave  keyboard (3)] \
    ↳ Power Button                            	id=7	[slave  keyboard (3)] \
    ↳ SEMITEK USB-HID Gaming Keyboard         	id=9	[slave  keyboard (3)] \
    ↳ Logitech USB Receiver                   	id=10	[slave  keyboard (3)] \
    ↳ SEMITEK USB-HID Gaming Keyboard         	id=11	[slave  keyboard (3)] \
    ↳ Logitech USB Receiver Consumer Control  	id=13	[slave  keyboard (3)] \
    ↳ Logitech USB Receiver System Control    	id=15	[slave  keyboard (3)] \
    ↳ UC-LOGIC Tablet WP5540U Pen             	id=17	[slave  keyboard (3)] 

in this case i want: UC-LOGIC Tablet WP5540U Pen Pen (0)     	id=18

### Select the device's property
➜  ~ xinput list-props 18                      
Device 'UC-LOGIC Tablet WP5540U Pen Pen (0)': \
	Device Enabled (160):	1 \
	Coordinate Transformation Matrix (162):	1.000000, 0.000000, 0.000000, 0.000000, 1.000000, 0.000000, 0.000000, 0.000000, 1.000000 \
	libinput Left Handed Enabled (312):	0 \
	libinput Left Handed Enabled Default (313):	0 \
	libinput Send Events Modes Available (275):	1, 0 \
	libinput Send Events Mode Enabled (276):	0, 0 \
	libinput Send Events Mode Enabled Default (277):	0, 0 \
	Device Node (278):	"/dev/input/event2" \
	Device Product ID (279):	21827, 4 \
	libinput Tablet Tool Pressurecurve (622):	0.000000, 0.000000, 0.000000, 0.000000, 1.000000, 1.000000, 1.000000, 1.000000 \
	libinput Tablet Tool Area Ratio (623):	0, 0

 ### Example
 xinput set-prop 18 162 0.5 0 0 0 1 0 0 0 1

tablet working on left half of the screen
