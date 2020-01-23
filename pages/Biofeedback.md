---
# *Achilles Biofeedback Wearable*

## *Background*
Currently there are few affordable tools to aid practitioners in the diagnosis
of conditions affecting the Achilles tendon. Providing a real-time quantifiable
diagnosis within a physician-patient consultation is generally achieved with
expensive gait monitoring systems which track the patient’s range of motion.
Additionally, practitioners often observe a lack of adherence to the prescribed
exercise regime by the patient. It is believed that this is partially due to an
absence of motivational results which illustrate the healing progress to the
patient. Both issues are being challenged by a wearable biofeedback device
designed and developed by the Dr. Giles Lab at UVic.

## *Objective*
Provide a wearable, battery-powered device which provides the following
functionality:

1.  Measurement of key gait parameters such as relative pressure distribution
    across the user’s plantar region and angular displacements for ankle
    flexion/extension/rotation.

2.  Tracking at-home patient exercise adherence by allowing them to plan, count
    and display customized rehabilitation exercises while providing pertinent
    statistics regarding the recovery process to the patient and clinicians.

3.  Allowing clinicians to set and send live warnings to patients regarding
    dangerous and prescribed movement limitations to prevent further injury.

  
## *Design Overview*

The proposed solution consists of a hardware platform and android application.
The wearable device includes a small enclosure, which is strapped

around the user’s calf and an insole which is inserted in the user’s shoe. The
primary embedded PCB, Bluetooth hardware and battery are enclosed in the calf
module. In the most recent version (not pictured) a thin ribbon cable connects
the calf module and insole.

Figure 1: Wearable Device

### *Pressure Sensor Theory of Operation*

After reviewing the literature, a prototype resistive sensor matrix has been
designed for sampling the pressure distribution across the user’s plantar
region. Velostat, an ESD safe packing material manufactured by 3M, acts as the
pressure sensing element. Since Velostat has a very high resistance between
points on its surface (Rx and Ry in Figure 1), strips of conductive copper tape
fixed to the same layer of Velostat will pass negligible currents between each
other (Figure 2). 

Figure 1: Directional Resistances of Velostat Figure 2: Velostat with Copper
Traces

However, copper traces on opposite sides of the Velostat sheet will
exchange a current dependent on the Velostat’s pressure-variant
vertical resistance (Rz in Figure 1) which is situated between the two
conductors (Figure 3). 

Figure 3: Pressure Dependent Resistances Between Copper Traces

The relative pressure, or vertical Velostat resistance (Rz), can be determined
by simply acquiring the output voltage of a resistive divider. Therefore, any
area of Velostat which is between two adjacent copper traces can be considered
an individual sensing element. By applying a positive voltage to one copper
trace on the top layer, the relative pressure on each sensor can be acquired by
simply measuring the voltages on each overlapping trace on the bottom layer.
Prototyping the pressure sensing insole required laser cutting a simple stencil
system which provided a convenient means for accurately placing copper strips on
the Velostat material (Figure 4). In the future, a flexible copper-polyamide
film will be masked and etched to provide more professional results and a higher
density of sensor elements.

Figure 4: Laser Cut Prototyping System and Assembled Insole Prototype

### *Inertial Measurement Units (IMUs)*

Inertial measurement units (IMUs) have been selected to measure the angular
displacements of ankle flexion, inversion/eversion and abduction/adduction. To
achieve this, two IMUs are required: one mounted on the user’s calf and one
embedded in the insole (Figure 5). Each IMU combines a MEMs accelerometer and
gyroscope to measure linear and angular velocity along three axes. This data is
buffered inside the IMU and communicated to a micro controller unit (MCU) via a
digital serial interface such as I2C or SPI.

Figure 5: Ankle Movements and IMU Locations

### *Printed Circuit Board Design*

Two circuit boards have been designed to complete this wearable platform. The
first is enclosed inside the insole and provides all electronics required to
read out the pressure sensor array. A STM32L0 microcontroller samples the entire
range of resistive sensors and stores the data in a buffer. An [ST
LSM6DSM](https://www.st.com/en/mems-and-sensors/lsm6dsm.html) inertial
measurement (IMU) unit communicates linear and angular acceleration to the
STM32L0 over I2C. The STM32L0 acts as a slave device on a SPI bus and streams
the measured pressure distribution and IMU data to the main processor housed in
the calf module. The second PCB hosts the main Bluetooth module, another ST
LSM6DSM IMU and a variety of electronics which provide:

-   Lipo single cell battery charging

-   USB 2.0 data transfer

-   Control of a small haptic feedback motor

-   Connector to insole board

-   LEDs for battery and connection status

    Figure 6: Main Board (Left) and Insole Board (Right)
