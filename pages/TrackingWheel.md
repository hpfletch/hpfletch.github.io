---
# *Tracking Wheel*

## *Background*

In December 2017 ASAsoft, a Victoria, BC based manufacturer of polymer power
line insulators,  
reached out to Dennis Hore, an Associate Professor of the University of Victoria
(UVIC), to  
create a partnership focused on researching the material performance of polymer
insulators.  
Specifically, how certain material properties such as hydrophobicity change as
an insulator is  
exposed to contaminates. Understanding how these contaminants accumulate and  
interact with surface and bulk polymer requires a controlled test environment in
which  
insulators can be contaminated and then subjected to high voltages. Such
requirements are  
satisfied by an electromechanical test apparatus known as the tracking wheel.

Completed as a joint effort between UVIC’s Science Machine Shop and Department
of  
Chemistry’s Electronics Shop, the proposed tracking wheel design consists of the
following primary components ():

1.  Rotor

2.  Lift

3.  Tanks

4.  High Voltage Contactor

5.  Frame

>   Figure 1: Tracking Wheel Apparatus (Isometric View)

## *Control System Design*

To achieve complete automation of the electromechanical assembly it is first
required to understand what actions it must perform. A tracking wheel test
simply consists of repeating a specified number of test cycles. Each cycle Is
composed of the following four steps (Figure 15).

>   Step 1: Contaminate  
>   The insulator is submerged in the contaminant solution.

>   Step 2: Drip  
>   After being submerged the excess contaminant solution drips off the
>   insulator

Step 3: Energize  
The user specified voltage is applied to the active end of the insulator

>   Step 4: Idle  
>   After being energized, the insulator in position 2 drains of any excess
>   charge and sits idle for contamination

Figure 2: Tracking Wheel Cycle Diagram

Therefore, to complete the proposed tracking wheel design, a control system must
be implemented which addresses the following objectives:

1.  Fully automates all actuations of the high voltage source, rotor motor and
    lift motor to perform each step in an aforementioned test cycle

2.  Repeat a specified number of cycles

3.  Allows the user a means of inputting test parameters

4.  Provides multiple safety measures and fail-safe operation

5.  Monitors and displays test progress

6.  Alerts the user of system malfunctions

To meet these requirements, a PLC based control system was assembled with off
the shelf components. The design primally relies on the discrete switching of
relays to energize motors and HV sources in a control sequence. An off the shelf
HMI was ideal for providing a means of inputting test parameters and providing
alerts and feedback.
