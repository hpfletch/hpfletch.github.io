---
# CareChanger

### *Background*
Urinary incontinence affects approximately 423 million individuals worldwide.
Within this population, physical or cognitive impairments may inhibit
individuals from communicating urinary void events to caretakers. This lack of
efficient communication frequently leads to skin infections and tissue damage
resulting in unnecessary health care costs and decreased quality of life. To
combat these issues, Jim McDermott conceptualized a device capable of detecting
void events and alerting caretakers. In Summer 2019, Jim reached out to partner
with the UVic Biomedical Engineering Design (BMED) Club for the design of an
assistive platform he called CareChanger.

### *Objective*  
To develop a small and mobile urinary void event detection and alert system for
wheelchair bound users which provides the following functionality:

-   Detection of urinary void events

-   Alert caretakers of events and display live client data

### *Design Overview*  
The proposed design consists of four modules:

1.  Wheelchair cushion sensor

2.  Primary battery-powered embedded device

3.  Backend database

4.  Mobile web application

### *Hardware Design*  
The CareChanger device is a battery-powered embedded system based on the
[NINA-W102](https://www.u-blox.com/en/product/nina-w10-series) Wi-Fi module. It
has been designed for quick and accurate detection of urinary void events. A
wearable device design ethos was adopted when approaching the functionality of
this device. That is, the device is simple, small and promotes caretaker
efficiency. The hardware provides the following functionality:

1.  LED Indication for charge status, Wi-Fi connection status, and event
    detection

2.  LiPo Battery charging ([Skyworks
    AAT3693IDH-AA](https://store.skyworksinc.com/products/detail/aat3693idhaat1-skyworks/74683/))

3.  Tactile switches for basic user inputs such as turning the device on/off,
    configuring the Wi-Fi connection and displaying the remaining battery charge

4.  Micro USB port for convenient device debugging, programming and charging

5.  A temperature and humidity sensor probe conveying all the data required to
    sense a urinary void event

Figure 1: CareChanger PCB

Figure 2: CareChanger Device

A [Silicon labs
Si7021](https://www.silabs.com/sensors/humidity/si7006-13-20-21-34/device.si7021-a20-gm)
low power temperature and humidity sensor is embedded in a small 3D-printed
probe (Figure 3). Embedding this probe in the seat cushion of the wheelchair
provides an acceptable measure of local temperature and humidity. Temperature
and humidity is periodically sampled and processed by the embedded system with a
dynamic algorithm which reliably identifies urinary void events. Data and event
status are then communicated to a remote database via Wi-Fi. Databased samples
are viewable via interactive plots. After an occurrence of a void event, the
device typically requires approximately 5 seconds to identify the user as
“dirty”.

Figure 3: Temperature and Humidity Probe

### *Results*  
A prototype device was completed and delivered to Jim in Fall 2019. Since then
it has been successfully sensing void events in the wheelchair of Jim’s
Daughter, Mariel. The success of this prototype has proven the utility of void
event detection in modern care facilities.

### *Awards, Recognition and Articles*

-   Second place in the technological barriers category at the [2019 National
    IDeA
    challenge](https://www.univcan.ca/programs-and-scholarships/innovative-designs-accessibility-competition/meet-the-2019-idea-competition-winners/)

-   Winner of the 2019 UVic Biomedical Engineering and Health Technology
    Showcase
    ([BEEP](https://www.uvic.ca/research/centres/biomedical/events-outreach/partnership-day/index.php))
    poster challenge

    For more on CareChanger and Jim’s story please check out the following
    articles:

1.  [“Dad’s invention for disabled daughter gets recognition at national
    contest”, Times
    Colonist](https://www.timescolonist.com/news/local/dad-s-invention-for-disabled-daughter-gets-recognition-at-national-contest-1.23918747)

2.  [“Improving Lives with the CareChanger Project”, My Life
    UVic](https://onlineacademiccommunity.uvic.ca/myuviclife/2019/08/30/improving-lives-with-the-carechanger-project/)
