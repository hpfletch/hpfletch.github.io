---
# *Beehive Monitoring System*

## *Background*

The interior climate of a beehive is vital for a healthy colony and efficient
honey production. A healthy colony will work to strictly regulate the
temperature and humidity of the brood nest (the part of the hive where eggs are
laid and develop). Any deviation from ideal brood nest climate will give the
beekeeper an indication of poor colony health or hive equipment.

## *Objectives*

Design and test a battery-powered sensor solution for reporting the interior
temperature and humidity of a [Langstroth
beehive](https://en.wikipedia.org/wiki/Langstroth_hive). Measured data must be
logged via a wireless connection and can be accessed from any web browser with
internet connection. Power consumption should be as low as possible to prolong
battery life.

## *Bee Space Constraints*

Bee space refers to the dimensions of open space which occur between the combs
and interior walls of a natural beehive (Figure 11). Bee space is commonly said
to be between 4.5 mm and 8.0 mm, which is approximately the gap bees require to
pass freely. Violating bee space (i.e. creating open space with dimensions
greater than 8.0 mm or smaller than 4.5 mm) can cause bees to fill the space
with extra comb, making hive inspection more difficult. Violating bee space may
also provide pests such as the hive beetle to access an area unreachable by
worker bees, allowing the pests to reproduce without intervention.

Figure 11: Bee Space

## *Hardware Design*

To meet the desired functionality, an ESP8266 based embedded sensor solution has
been designed and tested. The entire solution is mounted on a simple laser cut
frame which is sized to sit on top of a standard langstroth super. 12 bit
temperature and humidity samples are provided by a lower power [Silicon Labs
SI7021](https://www.silabs.com/sensors/humidity/si7006-13-20-21-34/device.si7021-a20-gm)
temperature and humidity sensor embedded in a custom 3D printed probe. This
probe is plugged through the frame wall into the back face of the main
electronic enclosure and is suspended over the brood nest frames. The main
enclosure is mounted on the exterior frame surface and with the solar cell. A
[Texas Instruments BQ24210](http://www.ti.com/product/BQ24210) LiPo Charger IC
charges the on board 18650 lithium ion cell via a small 5W solar cell or USB
port. On board debugging and programming is provided with a [Silicon Labs
CP2102N](https://www.silabs.com/interface/usb-bridges/usbxpress) USB to UART
bridge. Charge status LEDs and switches for resetting the device have proven
convenient when debugging and verifying this device.

Figure 12: Laser Cut Frame and Enclosure Assembly

Figure 13: 3D Printed Probe

Figure 14: Assembled PCB
