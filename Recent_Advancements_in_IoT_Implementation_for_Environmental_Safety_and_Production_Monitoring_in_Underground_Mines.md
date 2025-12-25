IEEE INTERNET OF THINGS JOURNAL, VOL. 10, NO. 16, 15 AUGUST 2023 14507
Recent Advancements in IoT Implementation
for Environmental, Safety, and Production
Monitoring in Underground Mines
Huili Zhang , Binghao Li , Senior Member, IEEE, Mahmoud Karimi, Serkan Saydam,
and Mahbub Hassan , Senior Member, IEEE
```
Abstract—Internet of Things (IoT) technology has been widely
```
used for real-time monitoring of the environment, safety, and
production in underground mines. This article presents the basic
```
structure of a Mine IoT (MIoT) system based on a widely used
```
three-layer IoT architecture, classifies types of sensors commonly
used in underground mines by specific application, and intro-
duces available wired and wireless communication technologies
and network topologies that can be applied in underground
mines. This article provides a comprehensive review of recent
developments in IoT applications in underground mines to mon-
itor various environmental parameters, including mine gas and
dust concentrations, temperature, humidity and airflow, ground-
water, ground support, and seismic activity. MIoT applications
for fire and hazard detection, personnel and equipment posi-
tioning, and production safety management have also been
investigated. This article highlights key challenges for the broad
application of IoT technology in underground mines, such as
operation disruption, additional investment, limited battery life,
poor quality of underground communication, and difficulty in
data management. Further research on novel advanced tech-
niques, such as self-powered sensors, MIoT standardization, and
underground wireless communication technologies, is essential to
improve the applicability and effectiveness of IoT applications in
underground mines.
```
Index Terms—Mine Internet of Things (MIoT), underground
```
communications, underground mine management, wireless sensor
```
network (WSN).
```
I. I NTRODUCTION
M
INING is critical for global socio-economic growth as
almost every industry value chain has a high demand
for mineral resources. However, the global mining industry
is facing economic concerns, such as high initial invest-
ment [1] and fluctuating commodity prices [2], extreme mining
```
Manuscript received 28 February 2023; revised 6 April 2023; accepted
```
```
11 April 2023. Date of publication 18 April 2023; date of current version
```
8 August 2023. This work was supported in part by the Australian Coal
```
Industry’s Research Program (ACARP) under Grant C33033. (Corresponding
```
```
author: Binghao Li.)
```
Huili Zhang, Binghao Li, and Serkan Saydam are with the School of
Minerals and Energy Resources Engineering, University of New South Wales,
```
Sydney, NSW 2052, Australia (e-mail: huili.zhang@unsw.edu.au; binghao.li@
```
```
unsw.edu.au; s.saydam@unsw.edu.au).
```
Mahmoud Karimi is with the Centre for Audio, Acoustics and Vibration,
```
University of Technology Sydney, Sydney, NSW 2007, Australia (e-mail:
```
```
mahmoud.karimi@uts.edu.au).
```
Mahbub Hassan is with the School of Computer Science and Engineering,
```
University of New South Wales, Sydney, NSW 2052, Australia (e-mail:
```
```
mahbub.hassan@unsw.edu.au).
```
Digital Object Identifier 10.1109/JIOT.2023.3267828
conditions, such as deeper and steeper deposits [3], severe
geotechnical and geological challenges [4], such as lower ore
grade [5], and a range of social and environmental issues,
such as safety and diverse community responses to min-
ing activities [6]. To address these problems, the mining
industry has implemented numerous emerging technologies to
improve mining efficiency and safety and reduce environmen-
tal hazards. Like many other industries, the mining industry
is implementing digital transformation to achieve automation.
To achieve efficient and safe mineral exploitation and extrac-
tion in underground mines, intelligent mining has become a
trend in operations by increasing the autonomy of machines
and by real-time monitoring of the environment, equipment,
and crew [7].
The complicated and extreme working environment in
underground mines is one of the main constraints to produc-
tivity and safety in the mining industry. Underground mines
have long and sometimes relatively narrow tunnels [8], unsta-
ble geological structures [9], hazardous atmospheres [10], and
equipment failures [11]. Considering these environmental and
operational challenges, monitoring of relevant environmen-
tal and structural parameters, positioning of personnel and
equipment, and supervision of mine personnel can effectively
enhance the productivity, efficiency, and safety of underground
mining. Traditionally, wired sensors monitor working condi-
tions at underground mines. However, a wired system can fail
easily once the network has faults [12], significantly increas-
ing the complexity of cable deployment and maintenance and
reducing system scalability and capability [13]. With the devel-
opment of sensor and communication technologies, wireless
```
sensor networks (WSNs) have gained popularity and have been
```
widely used in the mining industry. Small, light, and energy-
efficient wireless sensor nodes can overcome the limitations
of wired systems due to the advantages of convenient deploy-
ment, cost effectiveness, high reliability, scalability, capability,
mobility, and flexibility [14]. To maintain safe and efficient
underground mining operations, the demand for various types
```
of sensors will continue to grow. Internet of Things (IoT) tech-
```
nology has great potential to achieve real-time monitoring of
the underground mining process without blind areas by using
a large number of sensors.
```
Mine IoT (MIoT) is a technological paradigm that originates
```
from IoT. IoT is a global network that enables connectivity
and interaction between devices or machines [15]. Industrial
This work is licensed under a Creative Commons Attribution 4.0 License. For more information, see https://creativecommons.org/licenses/by/4.0/
14508 IEEE INTERNET OF THINGS JOURNAL, VOL. 10, NO. 16, 15 AUGUST 2023
TABLE I
C OMPARISON OF R ELATED W ORKS AND T HIS S URVEY
```
IoT (IIoT) is the industrial application of IoT. IIoT is a
```
network of interconnected smart industrial objects embed-
ded with electronics, sensors, and/or actuators, and these
interconnected things can communicate with each other [16].
MIoT is an important branch of IIoT, mainly referring to
a network that comprises a group of interconnected sensors
and actuators at mine sites. Sensors are used for data col-
lection, and actuators are responsible for system adjustment
and warning of abnormal conditions when the obtained value
exceeds the prelimited value. In other words, MIoT can help
real-time monitoring of mines, predicting potential accidents,
optimizing the mining process, and managing personnel and
equipment [17], [18], [19].
```
In contrast to underground IoT in other industries (e.g., oil
```
```
and agriculture) where sensors are buried and communicate
```
through the soil, IoT systems designed for underground mines
enable IoT devices to be placed in open underground spaces
and communicate through the air. Although MIoT devices are
located deep underground, communication methods in surface
and underground mines are similar, mainly achieved through
```
cable-based or radio frequency (RF) communication technolo-
```
gies [20]. However, due to the signal attenuation caused by
tunnel walls, the deployment and operation of IoT devices in
underground mines is much more challenging and complicated
than in surface mines.
There are several representative reviews on communication
technologies and IoT-based environmental monitoring applica-
tions in underground mines. The review by Yarkan et al. [21]
focused on existing wired, RF, hybrid, and emergency com-
munication systems in underground mines. The survey by
Forooshani et al. [22] investigated wireless communication
technologies and signal propagation modeling techniques in
underground mines. Singh et al. [23] provided an overview of
information and communication systems in underground mines
based on IoT technologies. The related security challenges and
open issues of IoT systems in underground mines have also
been discussed. Dohare et al. [9] reviewed the recent tech-
nological development of wireless communication networks
and environmental monitoring systems in underground coal
mines. Muduli et al. [11] proposed a systematic review
on WSN-based applications for the monitoring of environ-
mental and other parameters in underground coal mines.
Zhou et al. [17] discussed the feasibility, potential applications,
and challenges of bringing IoT to the coal mining industry
based on the current infrastructure in underground coal mines.
Molaei et al. [24] focused on the adaptability, current develop-
ments, and challenges of adopting IoT in the mining industry
based on data collection, communication, and management.
Key contributions and the main limitations of the review works
mentioned above are summarized in Table I.
From a mining perspective, the mining industry is focused
on deploying robust, reliable, and cost-effective MIoT systems
in underground mines by placing sensors and communica-
tion hardware at appropriate locations and is less concerned
with tasks that can be completed outside the mine site. Only
the end users in the mining sector, such as workers, know
exactly what parameters should be monitored in underground
mines, and decide what type of sensors are required and where
to deploy them. However, the above-mentioned reviews pri-
marily focused on protocols and algorithms applied in MIoT
applications for data communication and processing. They
have not investigated the applicability of wireless commu-
nication systems for underground mines based on technical
characteristics and application scenarios. They also have not
systematically summarized design parameters for MIoT appli-
cations, such as sensor types, deployment of sensor nodes, and
the threshold value of monitored environmental parameters.
Potential further directions for IoT research in underground
mining have not been discussed. Therefore, this article pro-
vides a comprehensive and state-of-the-art review of IoT
ZHANG et al.: RECENT ADVANCEMENTS IN IoT IMPLEMENTATION 14509
Fig. 1. Organization of this survey.
applications for environmental, safety, and production mon-
itoring in underground mines from a mining perspective and
identifies key challenges and further research directions for
developing underground MIoT.
```
This article is organized as follows (shown in Fig. 1).
```
Section II presents a three-layer MIoT architecture adapted
from [25] and key components of underground MIoT
systems. Section III provides a review of IoT applications
in underground mines for environmental monitoring, fire
detection, personnel and equipment positioning, and pro-
duction safety management. Section IV discusses key chal-
lenges and further directions for IoT research in underground
mines. Finally, Section V provides the conclusion of this
survey.
II. MI O T A RCHITECTURE
Due to the harsh environmental conditions and poor com-
munications in confined spaces, it is difficult to collect and
transmit data from underground mines. To successfully deploy
reliable IoT systems at mine sites, it is crucial to have
a clear understanding of sensors required for underground
mine monitoring and communication technologies suitable for
underground mine communications. On the one hand, com-
mon sensors and communication hardware may need to be
redesigned to withstand hostile environments, such as extreme
temperatures and depth. On the other hand, the problem of
limited communication connectivity and coverage must be
addressed to achieve ultralow latency underground commu-
nication up to hundreds of kilometers. Thus, the architecture
of MIoT should emphasize the importance of data acquisition
and data transmission at mine sites. The MIoT architecture
must also be flexible and scalable to meet the demands of
continuous dynamic mining operations.
In our study, the widely used three-layer architecture [25]
is applied to represent the basic structure of the MIoT system,
which consists of the perception and control layer, network
```
layer, and application layer (as shown in Fig. 2). Such an
```
architecture can provide more practical guidance for design-
ing IoT systems in hostile and confined underground mining
environments due to its simplicity and ease of implementa-
tion. It is also familiar to other disciplines, therefore increasing
cross-discipline collaboration. Other MIoT architectures can
be customized based on the three-layer architecture by adding
additional layers to meet specific operational requirements and
environmental conditions.
The perception and control layer is the lowest layer of
the MIoT architecture. This layer is responsible for collect-
ing data and information from the environment and “things”
through sensors, transmitting collected information to the
upper layer, and executing feedback commands using actua-
tors. The network layer acts as a bridge between the perception
layer and the application layer. It carries and transmits the
information collected from the physical objects through sen-
sors and interconnects machines embedded with sensors,
actuators, communication devices, and networks. The medium
for the data transmission can be wired, wireless, or hybrid
based. Communication technology and network topology are
two main factors that determine the stability and timeliness of
underground mine communication.
The application layer is the top layer of the MIoT archi-
tecture, the interface between the users and applications. This
layer is designed to analyze the data and information collected
by the perception layer using appropriate data processing tools.
After data analytics, decisions are made locally or remotely,
and relevant commands are sent to the control layer to perform
specific control functions. Currently, the required actions are
mostly carried out by humans due to insufficient collaboration
```
with artificial intelligence (AI) in the mining industry.
```
In terms of data processing, cloud computing deals with
big data analysis and storage, where all computing services
from MIoT are delivered to remote cloud computing platforms
14510 IEEE INTERNET OF THINGS JOURNAL, VOL. 10, NO. 16, 15 AUGUST 2023
Fig. 2. Three-layer architecture of MIoT.
```
provided by Internet enterprises (e.g., Google and Microsoft)
```
on demand through the Internet [26]. To reduce network
congestion and service latency of MIoT systems, distributed
```
computing approaches (e.g., edge computing and fog com-
```
```
puting) are introduced to store and compute the collected data
```
locally rather than directly delivering all the information to the
cloud server [27]. Edge computing is capable of raw data anal-
```
ysis and processing using limited computing resources (e.g.,
```
```
embedded microcontroller unit and gateway) at each isolated
```
edge node within the proximity of sensors. Fog computing can
be regarded as an extension of cloud computing, which pro-
vides data integration and computation at interconnected fog
nodes located between edge nodes and cloud data centers [26].
AI can be leveraged at edge and fog nodes for real-time
data processing and analysis, enabling more efficient and more
accurate decision making or predictions. Muduli et al. [28]
applied a supervised learning method based on the Naive
Bayes classification algorithm to analyze collected environ-
mental data sets of an underground coal mine at the base
station for early fire predictions. The simulation results indi-
cated that the proposed machine learning algorithm could
improve the accuracy and responsiveness of the environmental
monitoring system. Zhang et al. [29] developed a distributed
gas concentration prediction model for underground coal
mines based on a single hidden layer random weights neu-
```
ral network (SRWNN) and a nondominated sorting genetic
```
```
algorithm II (NSGA-II) for interval prediction. This model was
```
trained in a distributed manner using intelligent edge devices,
which could reduce training time and achieve load balancing.
Sanyal and Chattopadhyay [30] proposed a methane prediction
ZHANG et al.: RECENT ADVANCEMENTS IN IoT IMPLEMENTATION 14511
Fig. 3. Sensors used in underground mines for environmental, safety, and production monitoring.
platform for underground mines, where data was aggregated
in the fog layer and processed using long short-term memory
```
(LSTM) networks. This system achieved a forecast accuracy of
```
94.23%. Zhang et al. [31] used the Vision Swin Transformer-
YOLOv5 algorithm to develop an object detection model that
was capable of handling data captured by underground mine
surveillance cameras. The proposed model improved the aver-
age detection accuracy by 25% and was designed to operate
at the edge due to its low memory and computational require-
ments. The integration of AI and IoT in underground mining
is expected to realize proactive and predictive maintenance of
operating machines, while also facilitating the development
of fully automated systems [3], [32]. Currently, the applica-
tion of AI in underground mines is still in its early stages
due to challenges, such as limited data availability and power
constraints.
A. Sensors in Underground Mines
There are two types of sensors. Common sensors convert
measured physical quantities into electrical signals suitable for
further processing and interpretation in the upper layer, while
a smart sensor is embedded with a microprocessor unit for
the initial data processing [33]. Actuators operate in an oppo-
site working principle of a sensor, which converts a source
of energy, such as electrical input into a physical–mechanical
motion [34]. In MIoT applications, different types of sen-
sors are introduced to collect useful data and information,
where sensors are installed on tunnel walls, attached to oper-
```
ating machines, and worn by underground miners (as shown
```
```
in Fig. 3). Taking the environmental monitoring system in
```
```
underground mines as an example, numerous sensors (e.g.,
```
gas sensors, smoke and dust sensors, temperature sensors,
humidity sensors, airflow sensors, water quality sensors, level
```
sensors, etc.) are required to monitor environmental parame-
```
ters to ensure mine safety. Table II summarizes sensors that
are commonly used in underground mining.
B. Communication in Underground Mines
Because of the complex, dynamic, and harsh operational
environment in underground mines, it is highly challenging
to deploy a reliable and robust communication system for
data collection and information exchange for MIoT applica-
tions. To provide efficient and cost-effective communication in
underground mines, both wired and wireless communication
technologies are used for underground communication.
```
1) Wired Communication: Fiber-optic communication is a
```
commonly used wired communication method in the mining
industry. A fiber-optic communication system realizes data
transmission through conversion between electrical and opti-
cal signals. First, an optical transmitter converts electrical input
signals into optical signals. Then, optical signals are transmit-
ted to the optical receiver along an optical fiber cable. Finally,
an optical receiver reconverts optical signals back to the elec-
trical signals [43]. The fiber-optic system has the advantage of
being lightweight, flexible, reliable, low latency, intrinsically
safe, and interference proof [44]. Therefore, compared with
other cables, optical fibers are the most suitable for under-
ground mine communications. Currently, optical fibers are
always used as a backbone network in an underground mine
communication system to interconnect different networks [45].
14512 IEEE INTERNET OF THINGS JOURNAL, VOL. 10, NO. 16, 15 AUGUST 2023
TABLE II
S ENSORS C OMMONLY U SED IN U NDERGROUND M INING O PERATIONS [11], [35], [36], [37], [38], [39], [40], [41], [42]
TABLE III
A PPLICATION OF RFID S YSTEMS IN THE M INING I NDUSTRY [50]
The leaky feeder is one of the most commonly used commu-
nication approaches in underground mines that combines wired
and wireless communication methods. A leaky feeder system
emits and receives radio signals along the tunnel by using a
coaxial radiating cable [21]. Moreover, amplifiers are deployed
```
at fixed intervals (typically 350–500 m) along the leaky feeder
```
cable to compensate for signal loss [22]. Therefore, the leaky
feeder cable can significantly extend the communication range
of radio waves and is suitable for underground mine envi-
ronments. Leaky feeder systems can be used for ventilation
control [36] and rescue communication in mines [46].
```
2) Wireless Communication: RF and identification (RFID)
```
is widely used in the mining industry. An RFID system mainly
consists of tags and readers. The reader is continuously send-
ing radio waves. Once the tag attached to the object is within
range of the reader, the tag can transmit data to the reader.
RFID tag devices can be passive, semi-passive, or active. An
RFID system with a passive tag only works when the tag is in
proximity to the reader because received radio waves are used
to power the internal circuit of a tag. Then, the tag takes advan-
tage of backscattering to send the data back to the reader. A
semi-passive tag uses the battery to power its circuit but relies
on backscattering for data transmission. In contrast, an active
tag is embedded with a transmitter to transmit data and is fully
powered by an onboard power supply [47]. RFID systems with
passive tags are used for access control [48] and asset track-
ing [49] due to the advantages of low cost, small size, long
lifetime, and easy maintenance. Active RFID systems are com-
monly used for real-time localization of mobile personnel and
equipment because they provide a more accurate and wider
communication range of up to 100 m in open areas [50] com-
pared to passive tags with a coverage range of 5–10 m [49].
Table III summarizes the application of RFID systems in the
mining industry according to the operating frequency.
Apart from RFID, many other noncable-based wireless
communication technologies have also been developed for
underground mine communication systems, including Wi-Fi,
```
ultra-wideband (UWB), ZigBee, 3G, LTE/4G, Bluetooth low
```
```
energy (BLE), long-range (LoRa), narrowband-IoT (NB-IoT),
```
and 5G. Although MIoT applications based on RFID, ZigBee,
BLE, and Wi-Fi are most used in underground mining opera-
tions in recent years, Mekki et al. [51] expected that low-power
```
wide-area networks (LPWANs) technologies, such as LoRa
```
and NB-IoT, would dominate the communication of MIoT
applications in the near future because of their low-power,
LoRa, and low-cost network communication. Moreover, cel-
```
lular mobile communications (3G, LTE/4G, and 5G) are
```
developing rapidly. 5G may provide a new era for MIoT
because 5G networks have high data rates and low latency.
It means that 5G has the potential to realize fully digital
management of the mining area and real-time remote control
of mining operations with minimal manual intervention [52].
Among the above-mentioned wireless communication tech-
nologies, Wi-Fi and cellular mobile communications are not
suitable for battery-powered IoT applications due to their
high energy consumption. Table IV summarizes the tech-
nical features and the typical IoT applications of wireless
communication technologies in underground mines.
```
3) Network Topology: The network topology of an under-
```
ground mine communication system refers to the architecture
of the communication devices and data transmission medium
```
(wired or wireless) within the communication network [65].
```
An appropriate network topology design ensures highly reli-
able and robust underground communication for MIoT in
complex geographical environments. As shown in Fig. 4, the
communication hardware in the network can be regarded as
a point, while the transmission medium can be regarded as a
line to interconnect the communication devices. Four network
topologies are commonly used for underground mine commu-
```
nications: bus, star, ring, and mesh topologies [66], [67].
```
```
In a bus topology [Fig. 4(a)], each node is directly con-
```
nected to the bus. Thus, all data is transmitted along the bus
ZHANG et al.: RECENT ADVANCEMENTS IN IoT IMPLEMENTATION 14513
TABLE IV
S UMMARY OF W IRELESS C OMMUNICATION T ECHNOLOGIES IN U NDERGROUND M INES [36], [42], [46], [50], [52], [53],
[54], [55], [56], [57], [58], [59], [60], [61], [62], [63], [64]
```
Fig. 4. Commonly used network topologies for underground mines. (a) Bus topology. (b) Ring topology. (c) Star topology. (d) Mesh topology.
```
and is visible to all connected nodes. Although bus topol-
ogy has the advantages of easy wiring and high scalability,
network traffic frequently occurs due to the bottleneck of the
bus transmission capacity. Meanwhile, fault diagnosis can be
challenging in such a simple structure. The controller area
```
network (CAN) bus and RS485 are two typical examples of
```
bus topology.
```
In a ring topology [Fig. 4(b)], all communication devices
```
are interconnected in a closed circular structure. In this topol-
ogy, data jackets pass through all nodes in the ring layout
14514 IEEE INTERNET OF THINGS JOURNAL, VOL. 10, NO. 16, 15 AUGUST 2023
TABLE V
C OMPARISON OF N ETWORK T OPOLOGIES FOR
U NDERGROUND M INES [66], [67]
until they reach the destination node. This structure is rela-
tively simple and suitable for long-distance communication.
However, this structure has poor performance in reliability
and fault diagnosis because a single node failure can lead
to network failure. The optical fiber backbone network in
underground mines always adopts a ring topology.
```
In a star topology [Fig. 4(c)], each node in the network is
```
connected to a central hub that can organize and transmit mes-
sages. This structure can withstand joint point failure and is
capable of fault diagnosis. However, the network performance
mainly depends on the central node because the failure of the
central hub can lead to the failure of the entire network. The
network of a control room in an underground mine may use
the star topology.
```
In a full mesh topology [Fig. 4(d)], every device can directly
```
communicate with other devices in the network through a
point-to-point connection, and data can be simultaneously
shared among all nodes. To reduce the cost and system
complexity, partial mesh topologies are introduced. In this
topology, most nodes are interconnected, while a few nodes are
only linked to several other nodes. Mesh topologies are widely
used for underground mine interactive communications among
sensors due to their high robustness and reliability. However,
routing algorithms and flow control methods are required to
enable accurate and efficient data transmission. Table V com-
pares network topologies commonly used for communication
in underground mines.
III. MIOT A PPLICATIONS IN U NDERGROUND M INING
This section reviews MIoT applications for environmental
monitoring, fire detection, personnel and equipment posi-
tioning, and production safety management in underground
mines.
A. Environmental Monitoring
To ensure the safety of underground mining operations,
environmental parameters should be monitored in real time,
including gas and dust concentrations, variations of tempera-
ture, humidity and airflow, groundwater level and quality, and
the locations of seismic activities and roof collapses.
```
1) Gas and Dust Monitoring: Underground mining can
```
generate hazardous gases as well as explosive and respirable
mine dust. Therefore, gas monitoring systems can provide
early warning for potential hazards and achieve safe mining.
To ensure that miners can survive in underground mines,
```
atmospheric gases (O2 and CO2 ), typical toxic gases (e.g.,
```
```
SO2 , NOx, CO, and H2 S) and respirable concentration of
```
mine dust should be continuously monitored. Concentrations
```
of explosive gases (e.g., CH4 , C2 H2 , and H2 ) and total
```
```
incombustible content (TIC) of mine dust also need to be
```
maintained at a relatively low level to prevent fatal explo-
sions and fire incidents [11]. Sensors should be deployed
at places where hazardous gases are prone to accumulate
or release. Table VI summarizes the properties and primary
sources of commonly identified gases and dust in underground
mines. The concentration of each type of hazardous gas in
underground mines should always be below the 8-h shift time-
```
weighted average (TWA) concentration to avoid any adverse
```
```
health effects and should never exceed the ceiling limit (CL)
```
concentration.
Qin et al. [73] proposed a wireless gas monitoring system
in coal mines based on ZigBee to monitor methane concen-
tration. In this system, methane in the coal mine laneway was
detected by fixed and mobile sensor nodes. A large number
of catalytic combustion methane sensors were placed along
the laneway as fixed detection nodes. Hand-held nondispersive
infrared methane sensors and catalytic combustion methane
sensors attached to the miner’s helmet and mobile car were
regarded as mobile detection nodes. Once the detected gas
concentration exceeds the prescribed limit, the sound and light
alarm will be triggered, and the location of abnormal methane
concentration can be determined based on the address code.
Osunmakinde [74] developed an autonomous toxic gas remote
monitoring framework based on real-time gas detection, which
also introduced mobile robot sensing nodes to expand the
detection area. This design adopted an integrated network,
where optical fiber was the backbone network along the shaft
and ZigBee-based WSNs were used for gas monitoring. The
proposed system simultaneously monitored five types of haz-
```
ardous gases (i.e., CO2 , CO, H2 , CH4 , and NO2 ) through static
```
and mobile robot sensing nodes. A ZigBee-based gas moni-
```
toring platform with an Internet protocol (IP)-enabled Wi-Fi
```
gateway was designed by Mishra et al. [13]. It continuously
detected and recorded gases in underground mines, including
O2 , CO2 , CH4 , CO, H2 S, and H2 . In this design, sensor nodes
could be more power efficient by discarding redundant data
before transmitting information to the IP gateway for further
communication. A dashboard installed between the perception
layer and application layer visualized sensed data to check
data validity. Useful data was transmitted to the server through
the Wi-Fi gateway, where the server was used for data pro-
cessing and generated audio–visual alarms whenever recorded
data exceeded the threshold. In addition, an Android appli-
cation was developed for data management and visualization,
which enabled professionals to access information remotely by
entering a specific IP address. Jo and Khan [35] proposed an
early-warning safety system using BLE communication proto-
col for a coal mine. Stationary sensor nodes were installed on
the side walls of the main roadway and galleries to monitor a
wide range of gases, including CO 2 , NH3 , smoke, CO, CH4 ,
and other combustible gases. A term called Mine Warning
Index, which combined the effect of temperature, humidity,
ZHANG et al.: RECENT ADVANCEMENTS IN IoT IMPLEMENTATION 14515
TABLE VI
P ROPERTIES OF C OMMONLY I DENTIFIED G ASES AND D UST IN U NDERGROUND M INES [68], [69], [70], [71], [72]
and hazardous gas concentrations, was defined to evaluate
mine safety.
A helmet embedded with sensors can also be used for gas
monitoring. Hazarika [75] designed a battery-powered smart
helmet to detect CH4 and CO gas concentrations. The col-
lected data was transmitted to the control room using Digi
XBee RF modules for continuous monitoring. XBee mod-
ules may go into cyclic sleep mode when idle to save power.
An alarm would be generated in the control room once the
gas concentration was beyond the threshold value. The hel-
met developed by Sharma and Maity [76] was equipped with
a microcontroller for data analytics followed by indicating
```
devices (a speaker and a light-emitting diode (LED) light)
```
to achieve real-time alerts of excessive CH4 and CO gases
in underground mines. Helmet prototypes with a gas mon-
itoring function were also presented in [77] and [78]. A
low-cost portable gas monitoring system was proposed by
Zie¸tek et al. [79] to alert miners of gas hazards in underground
mines. This system integrated portable sensors, a microcon-
troller, and a smartphone. Portable gas sensors were used to
detect CO and H2 S gases, and the microcontroller calculated
the corresponding gas concentrations of the collected data.
Then, data was transmitted to a smartphone via a Bluetooth
connection for storage, computing, and visualization. In an
emergency, the smartphone could vibrate along with the back-
ground flashing red to remind miners of increasing hazardous
gas concentration.
For dust monitoring, Mahdavipour et al. [80] presented a
dust sensing system in underground coal mines to continu-
ously monitor the variation of TIC of deposited coal dust. This
system consists of three types of wireless sensors, including
an optical dust deposition sensor for measuring TIC with
moisture, a dielectrometry moisture sensor for eliminating the
effect of moisture, and a capacitive mass sensor for evaluating
the dust accumulation level. XBee RF modules were also used
in this design to achieve low-power network communication.
Lebecki et al. [81] developed a dust monitoring system to mon-
itor dust concentration in underground coal mine headings. In
this design, gravimetric dust samplers CIP-10-R and CIP-10-I
were introduced to measure the mean concentration of res-
pirable dust and total dust, respectively, while optical dust
samplers PL-2 were introduced to record instantaneous dust
concentration. Table VII summarizes the MIoT applications
for gas and dust monitoring.
```
2) Temperature, Humidity, and Airflow Monitoring: The
```
variations in temperature, humidity, and air velocity exert
a significant impact on the physical comfort and work-
ing efficiency of underground miners [82]. Therefore, tem-
perature, humidity, and air velocity in underground mines
should be maintained within the human thermal comfort
zone [83], [84], [85], as shown in Table VIII. However, the
temperature level in underground mines mainly depends on
the depth and location of the mine site and can range from
−40 ◦C in Mongolia [86] to 50 ◦C in Western Australia [87].
To mitigate the adverse impact of high temperature, ventila-
tion is an effective approach. The function of a ventilation
system in an underground mine is to ensure that the values
```
of critical environmental parameters (i.e., hazardous gas con-
```
```
centration, dust concentration, temperature, and humidity) are
```
maintained at acceptable levels. Since real-time monitoring
of relevant environmental parameters can provide a reference
for mine ventilation, ventilation on demand can be realized
14516 IEEE INTERNET OF THINGS JOURNAL, VOL. 10, NO. 16, 15 AUGUST 2023
TABLE VII
S UMMARY OF MI O T A PPLICATIONS FOR G AS AND D UST M ONITORING
in underground mines. The ventilation system can provide
the required volume of fresh air for a specific underground
area based on the balance between intake air supply and
demand [88]. According to Table VII, MIoT applications for
gas monitoring always record variations of temperature and
humidity as auxiliary parameters to evaluate the safety of the
working environment in underground mines.
The airflow monitoring system can provide accurate
information on air distribution in each branch of an under-
ground mine [89] and reflect the working performance of a
ventilation system [90]. Most mines prefer to use handheld
vane anemometers to measure the airflow and determine air
velocity along the tunnel due to their high flexibility [36].
In recent years, airflow sensors are increasingly deployed at
```
key locations (e.g., main fans and regulators) for real-time
```
monitoring of airflow and assistance of ventilation control
integrated with data analysis tools and ventilation simulation
platforms [90]. Zhou et al. [17] also noted that ventilation-
related sensors could be added to the MIoT network to develop
a comprehensive monitoring system.
```
3) Groundwater Monitoring: Water inrush occurs fre-
```
quently during underground mining. It poses a serious threat
to mine safety, and direct discharge of untreated ground-
water can pollute the environment [91]. To address these
problems, IoT has provided technical support for accurate
and real-time monitoring of groundwater in underground
mines [39], [63], [92], [93]. More et al. [63] presented an
overview of using IoT to optimize mine water management.
WSNs were introduced to monitor physicochemical character-
istics of on-site mine water, including water level, temperature,
pH value, electrical conductivity, and dissolved oxygen. RFID
tags were attached to mine water sample bottles to track and
store basic sampling information.
More specifically, Bo et al. [39] designed an IoT-based
online mine water monitoring platform to characterize mine
water quantity and quality in real time. Data acquisition in this
design was realized via a wired multisensor network which
comprised level sensors, pH sensors, suspended solids sen-
sors, water oil sensors, and conductivity sensors. A wireless
communication network based on the LoRa protocol was intro-
duced for data transmission. Yan et al. [92] introduced an
IoT platform to monitor the water level, temperature, flow,
```
and quality (i.e., salinity and characteristic ions) of the water
```
source for the coal mine in real time. Then, the collected data
ZHANG et al.: RECENT ADVANCEMENTS IN IoT IMPLEMENTATION 14517
TABLE VIII
H UMAN T HERMAL C OMFORT Z ONE [83], [84], [85]
was transmitted to the cloud service platform through wired
and wireless networks for further data management and ana-
lytics. After a series of analyses and modeling, water inrush
sources could be identified rapidly, and relevant water disas-
ters could be prevented. Samuel and Christian [93] proposed
```
a mine water (precipitation and groundwater) management
```
system based on RFID technology and quantum computing. In
this system, RFID-tagged pumps and sensors could track the
volume and direction of water flow throughout the mine shaft
in real time, while quantum computing enabled fast processing
of large volumes of collected data.
```
4) Structural and Geotechnical Monitoring: Structural
```
changes in underground mines are mainly due to unstable
geological structures and sudden seismic events. The resulting
tunnel collapses and rock bursts can lead to fatal accidents
and/or huge damage to operations. Therefore, rapid and accu-
rate detection of collapse zones and real-time monitoring can
effectively prevent unexpected geotechnical hazards and pro-
vide timely early warning for underground mine workers. The
collapse detection system is developed to identify structural
variations due to roof or wall falls and provide the collapse
location for underground workers. Li and Liu [94] designed
a structure-aware self-adaptive monitoring system based on
the wireless mesh sensor network to detect collapse areas in
underground mines and report their locations. In this design,
sensor nodes were fixed on ceilings and walls of underground
tunnels at a certain distance to form a regular mesh network.
A beacon mechanism was proposed to identify the collapse
hole outline and location by neighbor nodes broadcasting. This
system could discover and reconfigure displaced sensor nodes
after the collapse to maintain system integrity and validity.
Hu et al. [95] presented a connectivity-based mine collapse
detection system using WSN. After simplifying the actual 3-D
layout of sensor nodes into an unfolded 2-D representation,
collapse hole regions were detected according to connectivity
measurements of the neighboring sensor nodes.
To prevent rock bursts caused by rock mass instabilities, a
copper mine introduced a wired seismic monitoring system to
quantify the seismicity activities of underground mine tunnels
by detecting changes in seismic parameters of rock mass in
spatial–temporal dimensions using tri-axial geophones [38].
However, Chaamwe et al. [38] recommended that the exist-
ing seismic monitoring system at Mufulira mine should be
replaced by a WSN with a multihop transmission scheme
to form an easy-wiring, reliable, and flexible communica-
```
tion network. Meanwhile, fiber Bragg grating (FBG)-based
```
systems were proposed to monitor the structural health of the
underground coal mine roof due to the high accuracy and
reliability of FBG sensors. Jo et al. [96] designed an IoT-
based structural monitoring platform for damage detection and
real-time remote information sharing in a coal mine. In this
design, sensing arrays consisted of FBG strain sensors and
FBG temperature sensors, where FBG temperature sensors
were installed in the vicinity of FBG strain sensors to pro-
vide temperature compensation for strain measurements. These
FBG arrays were placed at the axial center of the tunnel roof
to measure tensile strain and reflected the effect of dynamic
mining operations on roof stability. After data acquisition, the
collected information was transmitted to a Web 2.0 main server
via optic fiber for further data analytics and visualization along
with online real-time information sharing. In addition to strain
monitoring, the roof safety monitoring system presented by
Zhao et al. [97] also introduced FBG roof separation sen-
sors to detect roof strata separation and indicate potential roof
collapses. Horizontally mounted FBG accelerometer sensors
could also locate seismic events in underground mines by
recording micro-seismic signals [40].
B. Fire and Hazard Detection
Mine fires are one of the major concerns in coal mines and
can result in catastrophic accidents, with safety and environ-
mental consequences. Although coal fires can be attributed to
```
various external factors (e.g., open flame and electrical spark-
```
```
ing), coal spontaneous combustion is responsible for most coal
```
fire incidents [98]. Coal spontaneous combustion is caused
by coal oxidation which is a complicated exothermic process
along with the generation of a large amount of heat and various
gases. In the process of coal oxidation, heat is continuously
generated and accumulates in underground coal mines until it
reaches the coal ignition temperature [99].
Spontaneous combustion in coal can be judged by the
coal temperature and concentration changes of the indicator
gases [100]. As shown in Table IX, the coal spontaneous com-
bustion process can be divided into four oxidation stages, and
each stage corresponds to different coal temperature and indi-
cator gases. CO is the main indicator gas as it accumulates
throughout the entire coal spontaneous combustion process,
while the other five gases can be regarded as auxiliary indicator
gases to indicate the emergence of different oxidation stages.
Since the spontaneous combustion becomes more intense with
the increase of coal temperature, the gas sampling interval is
shortened to reflect the coal spontaneous combustion status in
real time.
IoT-based fire detection systems are widely used to mon-
itor the status of mine fires in underground coal mines to
prevent fire accidents. Bhattacharjee et al. [101] developed
a fire detection and prevention system based on WSNs for
bord and pillar coal mines to prevent the spread of coal
fires at the early stage. In this design, gas sensor nodes were
deployed at the inlet and outlet of a panel to detect CO and
O2 gas concentrations. Once the measured gas concentration
exceeded the threshold value, the temperature sensor node at
14518 IEEE INTERNET OF THINGS JOURNAL, VOL. 10, NO. 16, 15 AUGUST 2023
TABLE IX
C OAL T EMPERATURE AND I NDICATOR G ASES IN C OAL S PONTANEOUS C OMBUSTION P ROCESS [100]
the junction of each pillar was activated and measured tem-
perature. In this case, whenever the measured temperature was
above the threshold value, it indicated the possible presence
of fire. Therefore, continuous temperature monitoring could
effectively indicate the exact fire location and fire spread direc-
tion. Moreover, they [101] also proposed a fire prevention
```
system (i.e., water pipes with automatically controlled elec-
```
```
tronic valves) to keep the coal mine safe from fire. The fire
```
monitoring system proposed by Muduli et al. [98] detected
temperature and concentrations of CO, CO2 , and O2 gases
by deploying sensor nodes in underground coal mines and
introduced a fuzzy-logic approach to improve system reliabil-
ity. Liu et al. [40] noted that coal mine goaf combustion in
longwall mines could be monitored using a laser multigas sen-
sor array and a fiber-optic distributed temperature sensor. The
laser multigas sensor array measured concentrations of CH 4 ,
CO, O2 , and C2 H4 gases, and the distributed temperature sen-
sor recorded the temperature distribution along the ventilation
tunnels.
C. Personnel and Equipment Positioning
Global navigation satellite systems are not suitable for
underground positioning because the satellite signal is not
capable of penetrating ground and metals [102]. To deal with
this problem, WSN-based IoT applications can be widely used
for the real-time localization of personnel and vehicles in
underground mines. A positioning system includes two types
```
of sensor nodes (i.e., fixed and mobile sensor nodes), where
```
anchors are fixed sensor nodes with known locations, while
tags are mobile sensor nodes attached to personnel or equip-
ment. The location of a tag can be determined according to
the location information of reference anchors [42]. Range-
```
based techniques [e.g., received signal strength (RSS), Time of
```
```
Arrival (ToA), Time Difference of Arrival (TDoA), and Angle
```
```
of Arrival (AoA)] are commonly used for positioning in under-
```
ground mines because of their high accuracy. Range-based
methods directly determine the distance between anchors and
tags based on signal geometrical parameters, including signal
strength, distance, and angle [103], [104].
Positioning systems in underground mines are mainly
used for personnel tracking and proximity detection.
Moschevikin et al. [105] discussed the possibility of real-time
localization in underground linear mine tunnel environments
by using leak feeders. Fink and Beikirch [106] proposed a
personnel tracking system for longwall coal mines based on
RFID technology and RSS measurements. In this system,
anchors were attached to ground support at fixed intervals
along the mine galleries, and tags were carried by miners.
Mohapatra et al. [54] developed a local personnel positioning
scheme in underground mines using Wi-Fi-based sensor nodes.
To achieve long battery life, dynamic sensor nodes were con-
figured with deep sleep mode and powered by high-capacity
batteries. Liu et al. [107] designed a ZigBee-based position-
ing system with noncomplete coverage of underground mine
tunnels. The entire mine tunnel was divided into several dis-
tricts, and each district was covered by a separate WSN. They
also noted that the previous location of a miner in a blind
area was estimated using a linear interpolation approach, while
the present and future locations of the miner in a blind area
were predicted according to the previous movement using fore-
casting models [10]. Baek et al. [108] demonstrated that the
real-time location of dump trucks in an underground limestone
mine can be tracked by installing battery-powered Bluetooth
beacons along the haul roads. Furthermore, a LoRa-based
positioning system designed for emergencies was presented
in [61], where a linear WSN was introduced to transmit the
location information of personnel and equipment in under-
ground mines when existing communications infrastructure
has broken or failed.
Proximity detection provides miner-to-vehicle and vehicle-
to-vehicle awareness in underground mines to prevent colli-
sions. Bolic et al. [109] presented a novel RFID design to per-
form proximity detection. This system introduced a new device
called “Sense-a-Tag” to passively receive and decode signals
emitted by nearby normal RFID tags. Kianfar et al. [110]
developed a UWB module for highly accurate tracking and
proximity detection in underground mines based on a two-
way ranging method. The field test indicated that the proposed
UWB module could effectively alert miners of incoming
locomotives in their proximity. Kim et al. [111] designed a
smart helmet with a personal proximity detection and warning
system based on BLE technology in an underground lime-
stone mine. The BLE module at the rear of the smart helmet
received signals transmitted from the Bluetooth beacon that
was attached to heavy machines and dangerous zones at mine
sites. The smart helmet was equipped with LED straps to
provide personnel with visual warnings. Ullah et al. [112]
noted that the advent of 5G would greatly facilitate vehicle-
to-everything communication, which might be ideal for prox-
imity detection in underground mines. Table X summarizes
wireless communication technologies for underground mine
positioning.
ZHANG et al.: RECENT ADVANCEMENTS IN IoT IMPLEMENTATION 14519
TABLE X
S UMMARY OF W IRELESS C OMMUNICATION T ECHNOLOGIES FOR U NDERGROUND M INE P OSITIONING [22], [42], [102], [113]
D. Production Safety Management
IoT technology has been introduced to ensure the safety of
personnel in underground mines. An IoT-based smart helmet
could detect hazardous events suffered by miners in under-
ground mines and send a timely alert to the control room.
Ramya et al. [115] designed a smart helmet integrated with
four sensors using 2.4-GHz RF technology to detect potential
accidents in underground mines. The infrared sensor detected
abnormal helmet wearing such as helmet removal. The tem-
perature sensor and the gas sensor were used to monitor the
surrounding environment. The force sensor identified colli-
sion to the head. To timely alert the responsible person, an
alert message was displayed on the graphical user interface
and a buzzer was automatically activated in the control room
when unexpected accidents occurred. A similar design was
also presented by Eldemerdash et al. [116] based on ZigBee
technology. However, the proposed system only worked when
the infrared sensor reading was abnormal, and the buzzer
in the control room was activated only when collision acci-
dents might occur. Three LED lights in different colors were
attached to the helmet to visually indicate the abnormal envi-
ronmental parameters and infrared sensor value. Geetha [117]
mentioned that a wireless voice transmission system could
be established for the smart helmet based on ZigBee tech-
nology for communications between miners, and information
exchange between miners and the control center.
Porselvi et al. [118] developed an underground miner health
monitoring system based on LoRa technology. Heartbeat and
respiratory sensors were used to monitor the health status of
mine workers. Whenever the sensed value was beyond the
threshold range, a buzzer turned on to alert miners. Meanwhile,
the received data was uploaded to an online webpage in real
time. Once the abnormal status was detected, the supervisor
immediately received a crisis alarm and notified the rescue
team if necessary. Zhou [55] designed a 3G-based video
surveillance system to timely and accurately visualize the con-
dition of mine workers and equipment in underground mines.
If a mine accident occurred, the rescue team could gain a
better understanding of the underground mine and take appro-
priate rescue measures. To ensure the safety of the rescue team
in underground mines, Wang [41] designed a wireless emer-
gency rescue system to monitor the vital signs of the rescuers
using FBG and three-axis acceleration sensors. FBG sensors
were used to detect the heart rate and body temperature of the
rescuers, while the three-axis acceleration sensor was used to
recognize the posture of the rescuers. Moreover, after the mine
accident, mobile rescue equipment, such as radars [119] and
rescue robots [120], was widely used to search for trapped
miners and provide structural and environmental information
about disaster areas for the rescue team as soon as possible.
IV. R ESEARCH C HALLENGES AND F URTHER D IRECTIONS
Real-time connectivity and data analytics have great poten-
tial to improve the efficiency of mines today and in the
future [121]. Although IoT can greatly benefit underground
mining production, the industry lags behind other industries
in adopting IoT-related technologies. This section discusses
the key challenges in developing MIoT technologies in under-
ground mines and highlights some potential future directions
for underground MIoT research.
A. Inherent Issues in the Mining Industry
Mining activities require significantly high investment in the
initial stage, and generally, no profit is gained until the start
of continuous mining operations. The lifespan of a mine is
expected to be decades. During this period, the market prices
of minerals fluctuate. To maximize the value over the lifespan
of a mine, mining companies are reluctant to make signif-
icant changes that may affect their operations and interrupt
continuous production. Therefore, the mining industry is well
known for not being innovative but a fast follower. The layout
and mining status of underground mines varies from mine to
mine. Every underground mine needs to design IoT applica-
tions based on its specific conditions, which means it can be
expensive and difficult to develop standardization.
Data availability of MIoT applications is another intractable
issue in the mining industry as mining companies rarely share
their data with external parties due to concerns about confi-
dentiality and competitive advantage. This is especially true
for data sets that contain sensitive information, such as pro-
duction rates, mineral grades, and exploitation costs. There
are only a few open-access data sets relevant to underground
MIoT systems. Kozielski et al. [122] presented a data set
obtained by 28 sensors installed in different locations in an
underground coal mine in Poland. This data set contained
14520 IEEE INTERNET OF THINGS JOURNAL, VOL. 10, NO. 16, 15 AUGUST 2023
environmental data of the mine and status data of an oper-
ating longwall shear. The data was collected at 1-s interval
between March and July 2014, with a total of 9 199 930 data
samples. Using this data set, ´Sle¸zak et al. [123] developed a
forecasting model to predict the methane concentration in the
coal mine. Similarly, Lyu et al. [124] trained an LSTM-based
encoder–decoder model to predict the concentration of CH 4
gas in an underground coal mine working face using a smaller
data set. The data set included concentration data of CH4 gas
```
collected by four sensors (from 2017-10-30 to 2017-11-18) in
```
an underground coal mine working face in China.
B. Hardware Issues
IoT is an emerging technology, which encounters vari-
ous technical issues in practical applications. Since some
underground mines have explosive gases, dust, and humid-
ity, sensors and communication devices should be resilient
```
and intrinsically safe (especially for coal mines). The limited
```
power supply in an underground mine is one of the major
constraints for MIoT applications. Currently, the electricity
consumed in underground mining operations is mainly pro-
vided by power cables because most renewable energy sources
```
(e.g., solar, strong wind, and hydropower) are not avail-
```
able underground. Therefore, IoT-related electronic devices in
underground mines need to be connected to power cables or
equipped with batteries. Although small-size and low-power
smart wireless sensors and communication modules have been
developed for the IoT system to reduce power consump-
tion, the battery still needs to be replaced regularly due to
the limited battery life. Replacement can be complicated and
hazardous at underground mine sites.
Energy harvesting techniques can be a potential solution to
charge the batteries of low-power electronic devices by cap-
```
turing a small amount of dissipated energy (e.g., heat, wind,
```
```
sound, vibration, and movement) from working machines in
```
underground mines. Vibration is one of the most common
energy sources in underground mines because of the con-
tinuous operation of various machines. Energy harvesting
from vibrations is mainly based on piezoelectric, electromag-
netic, and electrostatic methods. Compared to electromagnetic
and electrostatic mechanisms, piezoelectric transduction is the
most suitable approach for vibration energy harvesting at mine
sites because piezoelectric energy harvesters have the advan-
tages of simple structure, miniature size, high energy density,
and ease of integration [125], which can minimize interference
to mining production.
So far, piezoelectric energy harvesting has demonstrated the
ability to generate sufficient energy to power a wireless sensor
node. Mouapi et al. [126] designed a cantilevered piezoelec-
tric energy harvester to scavenge the vibration of an operating
mining locomotive. The recorded vibration data indicated that
the test locomotive produced random vibrations with a domi-
nant acceleration of 0.72 g at a frequency of 21.88 Hz. In this
case, the proposed energy harvester could generate a maxi-
mum power of 240.3 μW, allowing a commercial wireless
```
ZigBee sensor node (CC2520 of Texas Instruments) to trans-
```
mit data approximately 1 km every 7 min with appropriate
power management. Khazaee et al. [127] developed a method
for autonomous condition monitoring of water pumps based
on the pulse duration of an RF transmitter. In this design, a
cantilevered piezoelectric transducer was attached to the water
pump to harvest vibration energy, with a power output of up
to 710.45 μW. The harvested energy was then stored in a
capacitor and used to provide continuous energy for the micro-
processor and RF pulse transmitter. Le Scornec et al. [128]
proposed a piezoelectric airflow energy harvester with a max-
imum power output of 60 μW at a wind speed of 6.3 m/s.
Experimental results showed that four generators connected in
```
parallel could fully charge a capacitor (capacitance of 1.2 mF)
```
in 1 h. Once fully charged, the capacitor was capable of
powering a wireless sensor node to conduct temperature mea-
surements and RF communications seven times at intervals of
4 min.
According to the measurement conducted by
Rodriguez et al. [129], the average power consumption
```
of a BLE board (TI’s CC2650) embedded with three sensors
```
was around 255.3 μW with a sleep time of 2.5 s, while
the average power consumption of a LoRaWAN end-device
```
(Pervasive Nation) embedded with four sensors can be as low
```
as 9.6 μW when the sleep time is 15 min. Therefore, due
to the relatively low energy requirements of wireless sensor
nodes, vibration energy harvesting from operating machines
and ventilation airflow in underground mines show great
potential for developing self-powered sensor nodes. As shown
in Table XI, there are numerous potential vibration sources
in underground mines. These vibration sources can generate
steady vibrations that can be harvested to power sensors in
nearby control and monitoring systems. However, to design
an efficient vibration energy harvester for underground mines,
the total amount, frequencies, and amplitudes of generated
```
vibrations (including air flow for ventilation as it can generate
```
```
vibration) in underground mines should be investigated.
```
Another outstanding hardware issue is system interoper-
ability. Interoperability refers to the ability of a system or
device to communicate and interoperate with other systems
or devices within one department [16]. Various types of sen-
sors are deployed in underground mines, and these sensors
may come from different manufacturers. In this case, verti-
cal fragmentation may occur because sensors from different
vendors have their own technology stack and data formats.
Therefore, sensors could only communicate with sensors of
the same brand, which can be a massive hurdle for develop-
ing MIoT. To deal with this problem, MIoT standardization is
an effective solution, which provides a unified approach for
device interoperability and information security regardless of
provider and communication technology.
C. Underground Communication Issues
Effective and efficient network communication is the key
for underground MIoT applications. Although there are vari-
ous communication technologies, wireless signal propagation
is poor in confined and narrow tunnels and can be affected
by metal and non-line-of-sight environments. The limited
network coverage significantly increases the complexity and
ZHANG et al.: RECENT ADVANCEMENTS IN IoT IMPLEMENTATION 14521
TABLE XI
S UMMARY OF P OTENTIAL V IBRATION S OURCES IN U NDERGROUND M INES FOR E NERGY H ARVESTING
expense of network deployment, while the low data rate
can lead to data congestion and time delay. Therefore, fur-
ther research on emerging RF communication technologies,
such as LoRa and 5G, is necessary to provide cost-effective
and real-time underground communication. Millimeter-wave
technology has also gained widespread attention in recent
years. On the one hand, millimeter-wave communication pro-
vides IoT applications with high-rate data transmission and
```
massive available bandwidth (30–300 GHz) [120]. On the
```
other hand, although millimeter-wave systems can experi-
ence significant signal path loss due to obstacles, they can
be used for accurate underground location estimation and
environment sensing, especially with the advent of low-cost,
small-sized, and light-weighted millimeter-wave radar sen-
sors [131]. For example, millimeter-wave radar systems have
been used for indoor human positioning and motion recogni-
tion [132], driver health monitoring [133], automotive tracking
and localization [134], and proximity detection [135]. With
further research, these applications can be adapted to vehi-
cles and miners working in underground mines. To improve
the effectiveness of millimeter-wave communication systems
in non-line-of-sight scenarios, techniques, such as massive
multiple-input–multiple-output [136], beamforming [137], and
reflector-assisted communication [138], [139], are introduced
to compensate for signal attenuation and scattering caused by
obstacles.
```
Visible light communication (VLC) is another potential
```
wireless solution for underground mine communication, espe-
cially in areas that pose risks or other challenges to radio
frequencies [140]. For instance, a VLC system can be used
for personnel localization when RF signals do not work. In
this case, a VLC system mainly consists of LED luminaries as
transmitters mounted on the ceilings and walls and photode-
```
tectors (PDs) as receivers placed on miners’ helmets [141].
```
Similarly, proximity detection for oncoming vehicles and
miners can be achieved using VLC [142].
Due to the uneven and dynamic geographical environment,
it is challenging to design a robust and reliable network
topology in underground mines. Node failure and damage may
occur in the event of roof collapses and mine accidents, and
more nodes are required as the working face advances. To cope
with these unexpected situations, network topology should be
self-adaptable and scalable to maintain the smooth operation
of the network and enable network expansion.
A communication system in an underground mine always
provides positioning and tracking capabilities. The configura-
tion and deployment of an underground mine communication
network have a significant influence on the accuracy of posi-
tioning because the locations of personnel and equipment in
underground mines are mainly predicted by various signal
metrics. However, accurate positioning is challenging because
of signal multipath effects and varying propagation charac-
teristics in dynamic underground environments. Additionally,
positioning systems consume high energy for signal trans-
mission and processing to improve positioning accuracy and
range. Ideally, the communication network can be parallelly
used for normal data communication and accurate position-
ing and tracking in underground mines with robust and
energy-efficient localization algorithms.
D. Data Management Issues
It is challenging to integrate data collected by MIoT appli-
cations because of the data silos and massive amount of data.
Data silos describe the incompatible data distributed across
different platforms [63]. Since an underground mine can oper-
ate for a long time, data obtained from legacy systems is often
in information silos. The existence of data silos leads to incon-
venience in data gathering and data management. Meanwhile,
the prevalence of underground MIoT applications can lead to
an unprecedented increase in data categories and data vol-
umes from various information systems across mining sectors,
which may exacerbate data silos and significantly increase the
workload of data processing. The use of MIoT applications
generates time-series data in the mining lifecycle which plays
a crucial role in the monitoring and prediction of mining safety
14522 IEEE INTERNET OF THINGS JOURNAL, VOL. 10, NO. 16, 15 AUGUST 2023
```
and production (e.g., predicting geological hazards based on
```
```
the time-series data).
```
For efficient data management, a unified data structure
should be proposed to standardize various collected data and
ensure compatibility with the time dimension iteration. Data
exchange and processing workflows, such as raw data conver-
sion, data cleaning, analytics data exchange, and multiplatform
data exchange, are required for initial data processing. Edge,
fog, and cloud computing platforms can be used for massive
data analytics and storage based on specific situations.
V. C ONCLUSION
This article has presented recent developments in IoT appli-
cations for environmental, safety, and production monitoring
in underground mines. To gain a comprehensive understanding
of IoT essentials in underground mines, this article discussed
a generic three-layer MIoT architecture, the sensors used for
data collection, and communication technologies used for data
transmission in underground mines. IoT applications have been
widely used for environmental monitoring in underground
mines, such as mine gas and dust monitoring, temperature,
humidity and airflow monitoring, groundwater monitoring,
and structural monitoring. Fire detection systems have been
developed to effectively prevent coal mine fire accidents by
monitoring coal temperature and indicator gases. Real-time
and accurate localization of personnel and equipment, and
production safety management in underground mines have
been realized by using IoT technology based on wireless
communication.
Although various IoT applications have been proposed to
monitor the operation of underground mines, most designs are
still in theoretical and experimental stages. It is challenging to
run in-situ tests in underground mines due to the potential dis-
ruption to active operations. To enhance the effectiveness and
efficiency of IoT-based monitoring systems, this article has
discussed the possibility of developing self-powered wireless
sensors and communication modules using energy harvest-
ing techniques. MIoT standardization, wireless communication
technologies suitable for underground mines, and efficient data
management approaches should be further investigated.
R EFERENCES
[1] H. Nourali and M. Osanloo, “A regression-tree-based model for mining
capital cost estimation,” Int. J. Min. Reclamat. Environ., vol. 34, no. 2,
pp. 88–100, 2020, doi: 10.1080/17480930.2018.1510300.
[2] J. E. Tilton and J. I. Guzmán, Mineral Economics and Policy.
New York, NY, USA: Routledge, 2016, doi: 10.4324/9781315733708.
[3] J.-G. Li and K. Zhan, “Intelligent mining technology for an under-
ground metal mine based on unmanned equipment,” Engineering,
vol. 4, no. 3, pp. 381–391, 2018, doi: 10.1016/j.eng.2018.05.013.
[4] D. P. Adhikary and H. Guo, “Measurement of longwall mining induced
strata permeability,” Geotech. Geol. Eng., vol. 32, no. 3, pp. 617–626,
2014, doi: 10.1007/s10706-014-9737-8.
[5] S. Northey, S. Mohr, G. M. Mudd, Z. Weng, and D. Giurco, “Modelling
future copper ore grade decline based on a detailed assessment of
copper resources and mining,” Resource Conserv. Recycling, vol. 83,
pp. 190–201, Feb. 2014, doi: 10.1016/j.resconrec.2013.10.005.
[6] K. Spitz and J. Trudinger, Mining and the Environment: from
Ore to Metal, 2nd ed. London, U.K.: CRC Press, 2019,
```
doi: 10.1201/9781351183666.
```
[7] J. Wang and Z. Huang, “The recent technological development of intel-
ligent mining in China,” Engineering, vol. 3, no. 4, pp. 439–444, 2017,
```
doi: 10.1016/J.ENG.2017.04.003.
```
[8] X. Xia, Z. Chen, and W. Wei, “Research on monitoring and prewarning
system of accident in the coal mine based on big data,” Sci. Program.,
vol. 2018, Mar. 2018, Art. no. e9308742, doi: 10.1155/2018/9308742.
[9] Y. S. Dohare, T. Maity, P. S. Das, and P. S. Paul, “Wireless com-
munication and environment monitoring in underground coal mines—
Review,” IETE Tech. Rev., vol. 32, no. 2, pp. 140–150, Mar. 2015,
```
doi: 10.1080/02564602.2014.995142.
```
[10] Z. Liu, C. Li, D. Wu, W. Dai, S. Geng, and Q. Ding, “A wire-
less sensor network based personnel positioning scheme in coal
mines with blind areas,” Sensors, vol. 10, no. 11, p. 11, Nov. 2010,
```
doi: 10.3390/s101109891.
```
[11] L. Muduli, D. P. Mishra, and P. K. Jana, “Application of wireless sen-
sor network for environmental monitoring in underground coal mines:
A systematic review,” J. Netw. Comput. Appl., vol. 106, pp. 48–67,
Mar. 2018, doi: 10.1016/j.jnca.2017.12.022.
[12] N. S. Reddy, M. S. Saketh, and S. Dhar, “Review of sensor tech-
nology for mine safety monitoring systems: A holistic approach,” in
```
Proc. IEEE 1st Int. Conf. Control Meas. Instrument. (CMI), 2016,
```
pp. 429–434. doi: 10.1109/CMI.2016.7413784.
[13] P. K. Mishra, S. Kumar, Pratik, M. Kumar, and J. Kumar, “IoT
based multimode sensing platform for underground coal mines,”
Wireless Pers. Commun., vol. 108, no. 2, pp. 1227–1242, 2019,
```
doi: 10.1007/s11277-019-06466-z.
```
[14] W. Nan and S. Xue-Li, “Research on WSN nodes location technology
in coal mine,” in Proc. Int. Forum Comput. Sci. Technol. Appl., 2009,
pp. 232–234, doi: 10.1109/IFCSTA.2009.296.
```
[15] I. Lee and K. Lee, “The Internet of Things (IoT): Applications, invest-
```
ments, and challenges for enterprises,” Business Horizons, vol. 58,
no. 4, pp. 431–440, Jul./Aug. 2015, doi: 10.1016/j.bushor.2015.03.008.
[16] A. Aziz, O. Schelén, and U. Bodin, “A study on industrial
IoT for the mining industry: Synthesized architecture and open
research directions,” IoT, vol. 1, no. 2, pp. 529–550, Dec. 2020,
```
doi: 10.3390/iot1020029.
```
[17] C. Zhou, N. Damiano, B. Whisner, and M. Reyes, “Industrial Internet
```
of Things (IIoT) applications in underground coal mines,” Min. Eng.,
```
vol. 69, no. 12, pp. 50–56, Dec. 2017, doi: 10.19150/me.7919.
[18] Y. Gao et al., “Parallel end-to-end autonomous mining: An IoT-oriented
approach,” IEEE Internet Things J., vol. 7, no. 2, pp. 1011–1023,
Feb. 2020, doi: 10.1109/JIOT.2019.2948470.
[19] S. Chen, H. Xu, D. Liu, B. Hu, and H. Wang, “A vision of IoT:
applications, challenges, and opportunities with China perspective,”
IEEE Internet Things J., vol. 1, no. 4, pp. 349–359, Aug. 2014,
```
doi: 10.1109/JIOT.2014.2337336.
```
[20] N. Saeed, M.-S. Alouini, and T. Y. Al-Naffouri, “Toward the
Internet of Underground Things: A systematic survey,” IEEE Commun.
Surveys Tuts., vol. 21, no. 4, pp. 3443–3466, 4th Quart., 2019,
```
doi: 10.1109/COMST.2019.2934365.
```
[21] S. Yarkan, S. Guzelgoz, H. Arslan, and R. R. Murphy,
“Underground mine communications: A survey,” IEEE Commun.
Surveys Tuts., vol. 11, no. 3, pp. 125–142, 3rd Quart., 2009,
```
doi: 10.1109/SURV.2009.090309.
```
[22] A. E. Forooshani, S. Bashir, D. G. Michelson, and S. Noghanian,
“A survey of wireless communications and propagation
modeling in underground mines,” IEEE Commun. Surveys
Tuts., vol. 15, no. 4, pp. 1524–1545, 4th Quart., 2013,
```
doi: 10.1109/SURV.2013.031413.00130.
```
[23] A. Singh, D. Kumar, and J. Hötzel, “IoT based information and
communication system for enhancing underground mines safety and
```
productivity: Genesis, taxonomy and open issues,” Ad Hoc Netw.,
```
vol. 78, pp. 115–129, Sep. 2018, doi: 10.1016/j.adhoc.2018.06.008.
[24] F. Molaei, E. Rahimi, H. Siavoshi, S. G. Afrouz, and V. Tenorio, “A
```
comprehensive review on Internet of Things (IoT) and its implications
```
in the mining industry,” Amer. J. Eng. Appl. Sci., vol. 13, pp. 499–515,
Sep. 2020, doi: 10.3844/ajeassp.2020.499.515.
[25] M. Yun and B. Yuxin, “Research on the architecture and key
```
technology of Internet of Things (IoT) applied on smart grid,”
```
in Proc. Int. Conf. Adv. Energy Eng., Jun. 2010, pp. 69–72.
```
doi: 10.1109/ICAEE.2010.5557611.
```
[26] Q. Qi and F. Tao, “A smart manufacturing service system based on
edge computing, fog computing, and cloud computing,” IEEE Access,
vol. 7, pp. 86769–86777, 2019, doi: 10.1109/ACCESS.2019.2923610.
ZHANG et al.: RECENT ADVANCEMENTS IN IoT IMPLEMENTATION 14523
[27] T. Qiu, J. Chi, X. Zhou, Z. Ning, M. Atiquzzaman, and D. O. Wu,
“Edge computing in industrial Internet of Things: architecture,
advances and challenges,” IEEE Commun. Surveys Tuts., vol. 22, no. 4,
pp. 2462–2488, 4th Quart., 2020, doi: 10.1109/COMST.2020.3009103.
[28] L. Muduli, D. P. Mishra, and P. K. Jana, “Wireless sensor network
based underground coal mine environmental monitoring using machine
learning approach,” in Proc. 11th Int. Mine Ventilation Congr., 2019,
pp. 776–786, doi: 10.1007/978-981-13-1420-9_66.
[29] Y. Zhang, H. Guo, Z. Lu, L. Zhan, and P. C. K. Hung, “Distributed
gas concentration prediction with intelligent edge devices in coal
mine,” Eng. Appl. Artif. Intell., vol. 92, Jun. 2020, Art. no. 103643,
```
doi: 10.1016/j.engappai.2020.103643.
```
[30] S. Sanyal and A. Chattopadhyay, “DeepMines: A fog enabled
prediction platform for underground coal mines,” in Proc. Int.
```
Conf. Commun. Syst. Netw. (COMSNETS), Jan. 2020, pp. 726–730,
```
```
doi: 10.1109/COMSNETS48256.2020.9027454.
```
[31] F. Zhang, J. Tian, J. Wang, G. Liu, and Y. Liu, “ECViST: Mine
intelligent monitoring based on edge computing and vision swin
transformer-YOLOv5,” Energies, vol. 15, no. 23, p. 9015, Jan. 2022,
```
doi: 10.3390/en15239015.
```
[32] D. Ali and S. Frimpong, “Artificial intelligence, machine learning
and process automation: Existing knowledge frontier and way forward
for mining sector,” Artif. Intell. Rev., vol. 53, no. 8, pp. 6025–6042,
Dec. 2020, doi: 10.1007/s10462-020-09841-6.
[33] Farnell Element14. “Smart Sensors—Overview and Latest
Technology—Element14.” 2017. Accessed: Apr. 5, 2022. [Online].
```
Available: https://au.element14.com/smart-sensors-overview-and-
```
latest-technology
[34] GeeksforGeeks. “Actuators in IoT.” Feb. 20, 2021. Accessed: Apr. 5,
2022. [Online]. Available: https://www.geeksforgeeks.org/actuators-in-
iot/
[35] B. W. Jo and R. M. A. Khan, “An event reporting and early-warning
safety system based on the Internet of Things for underground coal
```
mines: A case study,” Appl. Sci., vol. 7, no. 9, p. 925, Sep. 2017,
```
```
doi: 10.3390/app7090925.
```
[36] M. Shriwas and C. Pritchard, “Ventilation monitoring and control
in mines,” Min. Metallurgy Explor., vol. 37, no. 4, pp. 1015–1021,
Aug. 2020, doi: 10.1007/s42461-020-00231-8.
[37] K. Zhang, S. Ji, Y. Zhang, J. Zhang, and R. Pan, “MEMS inertial
sensor for strata stability monitoring in underground mining: An exper-
imental study,” Shock Vib., vol. 2018, Jun. 2018, Art. no. e4895862,
```
doi: 10.1155/2018/4895862.
```
[38] N. Chaamwe, W. Liu, and H. Jiang, “Seismic monitoring in under-
ground mines: A case of mufulira mine in Zambia: Using wireless
sensor networks for seismic monitoring,” in Proc. Int. Conf. Electron.
Inf. Eng., Aug. 2010, pp. 310–314, doi: 10.1109/ICEIE.2010.5559868.
[39] L. Bo, Y. Liu, Z. Zhang, D. Zhu, and Y. Wang, “Research on
an online monitoring system for efficient and accurate monitor-
ing of mine water,” IEEE Access, vol. 10, pp. 18743–18756, 2022,
```
doi: 10.1109/ACCESS.2022.3151244.
```
[40] T. Liu et al., “Fibre optic sensors for coal mine hazard
detection,” Measurement, vol. 124, pp. 211–223, Aug. 2018,
```
doi: 10.1016/j.measurement.2018.03.046.
```
[41] H. Wang, “Coal mine disaster rescue life sign monitoring technol-
ogy based on FBG and acceleration sensor,” Procedia Eng., vol. 26,
pp. 2294–2300, Jan. 2011, doi: 10.1016/j.proeng.2011.11.2437.
[42] G. P. Hancke and B. J. Silva, “Wireless positioning in underground
```
mines: Challenges and recent advances,” IEEE Ind. Electron. Mag.,
```
vol. 15, no. 3, pp. 39–48, Sep. 2021, doi: 10.1109/MIE.2020.3036622.
[43] Polytechnic Hub. “What is Fiber Optic Communication?” Apr. 18,
2017. Accessed: Mar. 7, 2022. [Online]. Available: https://www.
polytechnichub.com/fiber-optic-communication/
[44] C. Stratton. “Fibre Optics in Underground Mines.” 2016. Accessed:
Apr. 5, 2022. [Online]. Available: http://ecdonline.com.au/content/data-
networking-communications/article/fibre-optics-in-underground-mines-
298649690
[45] Z. Qian, Y. Yuan, S. Zhang, and G. Ren, “Design of online mine safety
detection system based on Internet of Things,” Int. J. Online Eng.,
vol. 12, no. 12, p. 60, Dec. 2016, doi: 10.3991/ijoe.v12i12.6449.
[46] M. D. Bedford, A. J. A. Rodríguez López, and P. J. Foster, “Low-cost
leaky feeder communication for mines rescue,” Min. Technol., vol. 129,
no. 4, pp. 217–227, Oct. 2020, doi: 10.1080/25726668.2020.1838110.
[47] V. Chawla and D. S. Ha, “An overview of passive RFID,”
IEEE Commun. Mag., vol. 45, no. 9, pp. 11–17, Sep. 2007,
```
doi: 10.1109/MCOM.2007.4342873.
```
[48] M. K. N. Mahmad, M. R. M. A. Z. Rozainy, and N. Baharun,
```
“Applications of radio frequency identification (RFID) in mining indus-
```
tries,” IOP Conf. Mater. Sci. Eng., vol. 133, Jun. 2016, Art. no. 012050,
```
doi: 10.1088/1757-899X/133/1/012050.
```
[49] A. Atkins, L. Zhang, and H. Yu, “Applications of RFID and mobile
technology in tracking of equipment for maintenance in the mining
industry,” in Proc. Aust. Inst. Min. Metallurgy, 2010, p. 10.
[50] P. K. Mishra, R. F. Stewart, M. Bolic, and M. C. E. Yagoub,
“RFID in underground-mining service applications,” IEEE
Pervasive Comput., vol. 13, no. 1, pp. 72–79, Jan.–Mar. 2014,
```
doi: 10.1109/MPRV.2014.14.
```
[51] K. Mekki, E. Bajic, F. Chaxel, and F. Meyer, “A comparative study
of LPWAN technologies for large-scale IoT deployment,” ICT Exp.,
vol. 5, no. 1, pp. 1–7, Mar. 2019, doi: 10.1016/j.icte.2017.12.005.
[52] L. Ma, “Study on intelligent mine based on the applica-
tion of 5G wireless communication system,” IOP Conf. Earth
Environ. Sci., vol. 558, no. 3, Aug. 2020, Art. no. 032050,
```
doi: 10.1088/1755-1315/558/3/032050.
```
[53] L. Oliveira, J. Rodrigues, S. Kozlov, R. Rabêlo, and V. Albuquerque,
“MAC layer protocols for Internet of Things: A survey,” Future
Internet, vol. 11, no. 1, p. 16, Jan. 2019, doi: 10.3390/fi11010016.
[54] A. G. Mohapatra et al., “Precision local positioning mecha-
nism in underground mining using IoT-enabled WiFi platform,”
Int. J. Comput. Appl., vol. 42, no. 3, pp. 266–277, Apr. 2020,
```
doi: 10.1080/1206212X.2018.1551178.
```
[55] W. Zhou, “Design of video surveillance system based on 3G
wireless network in underground coal mine,” in Proc. Int.
Conf. Uncertainty Reason. Knowl. Eng., 2011, pp. 248–250,
```
doi: 10.1109/URKE.2011.6007809.
```
[56] S. Wang, S. Wang, W. Liu, and Y. Tian, “A study on the optimization
nodes arrangement in UWB localization,” Measurement, vol. 163,
Oct. 2020, Art. no. 108056, doi: 10.1016/j.measurement.2020.108056.
[57] M. M. Ali et al., “Development of underground mine monitor-
ing and communication system integrated ZigBee and GIS,” Int.
J. Min. Sci. Technol., vol. 25, no. 5, pp. 811–818, Sep. 2015,
```
doi: 10.1016/j.ijmst.2015.07.017.
```
[58] V. Gomathi, “Design of an adaptive coal mine rescue robot using
wireless sensor networks,” in Proc. NCIPRC, 2015, p. 4.
[59] S. Park and Y. Choi, “Bluetooth beacon-based mine production
management application to support ore haulage operations in under-
ground mines,” Sustainability, vol. 13, no. 4, p. 2281, Feb. 2021,
```
doi: 10.3390/su13042281.
```
[60] P. Branch and T. Cricenti, “A LoRa relay based system for
detonating explosives in underground mines,” in Proc. IEEE
```
Int. Conf. Ind. Technol. (ICIT), Feb. 2020, pp. 259–264,
```
```
doi: 10.1109/ICIT45562.2020.9067213.
```
[61] P. Branch, B. Li, and K. Zhao, “A LoRa-based linear sensor network
for location data in underground mining,” Telecom, vol. 1, no. 2,
pp. 68–79, Sep. 2020, doi: 10.3390/telecom1020006.
[62] A. Khalifeh, K. A. Aldahdouh, K. A. Darabkh, and W. Al-Sit, “A
survey of 5G emerging wireless technologies featuring LoRaWAN,
Sigfox, NB-IoT and LTE-M,” in Proc. Int. Conf. Wireless
```
Commun. Signal Process. Netw. (WiSPNET), Mar. 2019, pp. 561–566.
```
```
doi: 10.1109/WiSPNET45539.2019.9032817.
```
[63] K. S. More, C. Wolkersdorfer, N. Kang, and A. S. Elmaghraby,
“Automated measurement systems in mine water management and
mine workings—A review of potential methods,” Water Resource Ind.,
vol. 24, Dec. 2020, Art. no. 100136, doi: 10.1016/j.wri.2020.100136.
[64] “3GPP.” Accessed: Mar. 7, 2022. [Online]. Available: https://www.
3gpp.org/
[65] X. Wang, X. Zhao, Z. Liang, and M. Tan, “Deploying a wireless sen-
sor network on the coal mines,” in Proc. IEEE Int. Conf. Netw. Sens.
Control, Apr. 2007, pp. 324–328, doi: 10.1109/ICNSC.2007.372799.
[66] N. Bisht and S. Singh, “Analytical study of different netwrk topolo-
gies,” Int. Res. J. Eng. Technol., vol. 2, no. 1, p. 3, 2015.
[67] S. Santra and P. P. Acharjya, “A study and analysis on computer
network topology for data communication,” Int. J. Emerg. Technol.
Adv. Eng., vol. 3, no. 1, pp. 88–90, Jan. 2013.
[68] J. Shemshad, S. M. Aminossadati, W. P. Bowen, and M. S. Kizil,
“Effects of pressure and temperature fluctuations on near-
infrared measurements of methane in underground coal mines,”
Appl. Phys. B, vol. 106, no. 4, pp. 979–986, Mar. 2012,
```
doi: 10.1007/s00340-011-4801-z.
```
[69] M. Anas, S. M. Haider, and P. Sharma, “Gas monitoring and testing in
underground mines using wireless technology,” Int. J. Eng. Res., vol. 6,
no. 1, pp. 1–5, Jan. 2017, doi: 10.17577/IJERTV6IS010306.
14524 IEEE INTERNET OF THINGS JOURNAL, VOL. 10, NO. 16, 15 AUGUST 2023
[70] S. K. Chaulya and G. M. Prasad, “Chapter 3—Gas sensors for
underground mines and hazardous areas,” in Sensing and Monitoring
Technologies for Mines and Hazardous Areas, S. K. Chaulya and
G. M. Prasad, Eds., Amsterdam, The Netherlands: Elsevier, 2016,
pp. 161–212. doi: 10.1016/B978-0-12-803194-0.00003-9.
[71] A. Hursthouse, F. Allan, L. Rowley, and F. Smith, “A pilot study of
personal exposure to respirable and inhalable dust during the sand-
```
ing and sawing of medium density fibreboard (MDF) and soft wood,”
```
Int. J. Environ. Health Res., vol. 14, no. 4, pp. 323–326, Aug. 2004,
```
doi: 10.1080/09603120410001725667.
```
[72] M. U. Khan, K. O. Homan, S. A. Saki, M. Z. Emad, and M. A. Raza,
“Real-time diesel particulate matter monitoring in underground mines:
Evolution and applications,” Int. J. Min. Reclamation Environ., vol. 35,
no. 4, pp. 291–305, Apr. 2021, doi: 10.1080/17480930.2020.1818937.
[73] X. Qin, M. Fu, and B. Shen, “Coal mine gas wireless monitoring
system based on WSNs,” in Proc. 2nd Int. Conf. Digit. Manuf. Autom.,
Aug. 2011, pp. 309–312, doi: 10.1109/ICDMA.2011.82.
[74] I. O. Osunmakinde, “Towards safety from toxic gases in underground
mines using wireless sensor networks and ambient intelligence,” Int.
J. Distrib. Sens. Netw., vol. 9, no. 2, Feb. 2013, Art. no. 159273,
```
doi: 10.1155/2013/159273.
```
[75] P. Hazarika, “Implementation of smart safety helmet for coal
mine workers,” in Proc. IEEE 1st Int. Conf. Power Electron.
```
Intell. Control Energy Syst. (ICPEICES), Jul. 2016, pp. 1–3.
```
```
doi: 10.1109/ICPEICES.2016.7853311.
```
[76] M. Sharma and T. Maity, “Low cost low power smart helmet
for real-time remote underground mine environment monitoring,”
Wireless Pers. Commun., vol. 102, no. 1, pp. 149–162, Sep. 2018,
```
doi: 10.1007/s11277-018-5831-1.
```
[77] C. Qiang, S. Ji-Ping, Z. Zhe, and Z. Fan, “ZigBee based intelligent
helmet for coal miners,” in Proc. WRI World Congr. Comput. Sci. Inf.
Eng., Mar. 2009, pp. 433–435, doi: 10.1109/CSIE.2009.653.
[78] A. Mishra, S. Malhotra, Ruchira, P. Choudekar, and H. P. Singh,
“Real time monitoring & analyzation of hazardous parameters in under-
ground coal mines using intelligent helmet system,” in Proc. 4th Int.
```
Conf. Comput. Intell. Commun. Technol. (CICT), Feb. 2018, pp. 1–5.
```
```
doi: 10.1109/CIACT.2018.8480177.
```
[79] B. Zie¸tek, A. Banasiewicz, R. Zimroz, J. Szrek, and S. Gola, “A
portable environmental data-monitoring system for air hazard evalu-
ation in deep underground mines,” Energies, vol. 13, no. 23, p. 6331,
Jan. 2020, doi: 10.3390/en13236331.
[80] O. Mahdavipour et al., “Wireless sensors for automated control
```
of total incombustible content (TIC) of dust deposited in under-
```
ground coal mines,” in Proc. IEEE SENSORS, Nov. 2015, pp. 1–4.
```
doi: 10.1109/ICSENS.2015.7370353.
```
[81] K. Lebecki, M. Małachowski, and T. Sołtysiak, “Continuous dust moni-
toring in headings in underground coal mines,” J. Sustain. Min., vol. 15,
no. 4, pp. 125–132, Jan. 2016, doi: 10.1016/j.jsm.2017.01.001.
[82] T. Maurya, K. Karena, H. Vardhan, M. Aruna, and M. G. Raj, “Effect
of heat on underground mine workers,” Procedia Earth Planet. Sci.,
vol. 11, pp. 491–498, Jan. 2015, doi: 10.1016/j.proeps.2015.06.049.
[83] P. F. da Conceição Pereira and E. E. Broday, “Determination of thermal
comfort zones through comparative analysis between different charac-
terization methods of thermally dissatisfied people,” Buildings, vol. 11,
no. 8, p. 320, Aug. 2021, doi: 10.3390/buildings11080320.
[84] M. Qin, P. Hou, Z. Wu, and J. Wang, “Precise humidity
control materials for autonomous regulation of indoor mois-
ture,” Build. Environ., vol. 169, Feb. 2020, Art. no. 106581,
```
doi: 10.1016/j.buildenv.2019.106581.
```
[85] P. Roghanchi, K. C. Kocsis, and M. Sunkpal, “Sensitivity analysis
of the effect of airflow velocity on the thermal comfort in under-
ground mines,” J. Sustain. Min., vol. 15, no. 4, pp. 175–180, Jan. 2016,
```
doi: 10.1016/j.jsm.2017.03.005.
```
[86] N. Muller. “Mongolia’s New Mining Boom.” 2019. Accessed: Mar. 11,
2022. [Online]. Available: https://thediplomat.com/2019/10/mongolias-
new-mining-boom/
[87] ABC News. “Mine Site in the Pilbara Hits 50 Degrees.” Jan. 10, 2014.
```
Accessed: Mar. 11, 2022. [Online]. Available: https://www.abc.net.au/
```
news/rural/2014-01-10/hot-50degrees/5193850
[88] Q.-F. Ge, W.-G. Zhu, W.-G. Zhang, Q.-G. Chen, and Z.-M. Yang,
“Ventilation-on-demand system in pulang copper mine,” in
Proc. 11th Int. Mine Ventilation Congr., 2019, pp. 116–125,
```
doi: 10.1007/978-981-13-1420-9_11.
```
[89] H. W. Wu and A. D. S. Gillies, “Real-time airflow monitoring and
control within the mine production system,” in Proc. 8th Int. Mine
Vent. Congr., 2005, p. 7.
[90] L. Zhou, R. A. Thomas, L. Yuan, and D. Bahrami, “Experimental study
of improving a mine ventilation network model using continuously
monitored airflow,” Min. Metallurgy Explor., vol. 39, pp. 887–895,
Mar. 2022, doi: 10.1007/s42461-022-00574-4.
[91] X. Wang, Z. Xu, Y. Sun, J. Zheng, C. Zhang, and Z. Duan,
“Construction of multi-factor identification model for real-time
monitoring and early warning of mine water inrush,” Int. J.
Min. Sci. Technol., vol. 31, no. 5, pp. 853–866, Sep. 2021,
```
doi: 10.1016/j.ijmst.2021.07.012.
```
[92] Z. Yan, J. Han, J. Yu, and Y. Yang, “Water inrush sources monitoring
and identification based on mine IoT,” Concurrency Comput. Pract.
Exp., vol. 31, no. 10, 2019, Art. no. e4843, doi: 10.1002/cpe.4843.
[93] M. K. Samuel and W. Christian, Disruptive Technologies in Mine Water
Management—The Future, IMWA, Wendelstein, Germany, 2019.
[94] M. Li and Y. Liu, “Underground coal mine monitoring with wireless
sensor networks,” ACM Trans. Sens. Netw., vol. 5, no. 2, pp. 1–29,
Apr. 2009, doi: 10.1145/1498915.1498916.
[95] S. Hu, H. Shu, and X. Song, “Fisher information of mine col-
lapse hole detection based on sensor nodes connectivity,” Int. J.
Distrib. Sens. Netw., vol. 9, no. 9, Sep. 2013, Art. no. 306496,
```
doi: 10.1155/2013/306496.
```
[96] B. W. Jo, R. M. A. Khan, Y. S. Lee, J. H. Jo, and N. Saleem, “A fiber
Bragg grating-based condition monitoring and early damage detection
system for the structural safety of underground coal mines using the
Internet of Things,” J. Sens., vol. 2018, Apr. 2018, Art. no. e9301873,
```
doi: 10.1155/2018/9301873.
```
[97] Y. Zhao, N. Zhang, and G. Si, “A fiber bragg grating-based monitoring
system for roof safety control in underground coal mining,” Sensors,
vol. 16, no. 10, p. 1759, Oct. 2016, doi: 10.3390/s16101759.
[98] L. Muduli, P. K. Jana, and D. P. Mishra, “Wireless sensor network based
fire monitoring in underground coal mines: A fuzzy logic approach,”
Process Safety Environ. Protect., vol. 113, pp. 435–447, Jan. 2018,
```
doi: 10.1016/j.psep.2017.11.003.
```
[99] H.-T. Su, F.-B. Zhou, B.-B. Shi, H.-N. Qi, and J.-C. Deng, “Causes
and detection of coalfield fires, control techniques, and heat energy
```
recovery: A review,” Int. J. Minerals Metallurgy Mater., vol. 27, no. 3,
```
pp. 275–291, Mar. 2020, doi: 10.1007/s12613-019-1947-x.
[100] L. Zhuang and W. Ji-Ren, “The technology of forecasting and
predicting the hidden danger of underground coal spontaneous
combustion,” Procedia Eng., vol. 26, pp. 2301–2305, Dec. 2011,
```
doi: 10.1016/j.proeng.2011.11.2438.
```
[101] S. Bhattacharjee, P. Roy, S. Ghosh, S. Misra, and M. S. Obaidat,
“Wireless sensor network-based fire detection, alarming, monitoring
and prevention system for bord-and-pillar coal mines,” J. Syst. Softw.,
vol. 85, no. 3, pp. 571–581, 2012, doi: 10.1016/j.jss.2011.09.015.
[102] F. Seguel, P. Palacios-Játiva, C. A. Azurdia-Meza, N. Krommenacker,
P. Charpentier, and I. Soto, “Underground mine positioning: A
review,” IEEE Sensors J., vol. 22, no. 6, pp. 4755–4771, Mar. 2022,
```
doi: 10.1109/JSEN.2021.3112547.
```
[103] M. Zare, R. Battulwar, J. Seamons, and J. Sattarvand, “Applications
of wireless indoor positioning systems and technologies in under-
ground mining: A review,” Min. Metallurgy Explor., vol. 38, no. 6,
pp. 2307–2322, Dec. 2021, doi: 10.1007/s42461-021-00476-x.
[104] F. Zafari, A. Gkelias, and K. K. Leung, “A survey of
indoor localization systems and technologies,” IEEE Commun.
Surveys Tuts., vol. 21, no. 3, pp. 2568–2599, 3rd Quart., 2019,
```
doi: 10.1109/COMST.2019.2911558.
```
[105] A. Moschevikin, M. Serezhina, and A. Sikora, “On the possi-
bility to use leaky feeders for positioning in chirp spread spec-
trum technologies,” in Proc. 2nd Int. Symp. Wireless Syst. Conf.
Intell. Data Acq. Adv. Comput. Syst., Sep. 2014, pp. 56–65,
```
doi: 10.1109/IDAACS-SWS.2014.6954624.
```
[106] A. Fink and H. Beikirch, “MineLoc—Personnel tracking system for
longwall coal mining sites,” IFAC PapersOnline, vol. 48, no. 10,
pp. 215–221, Jan. 2015, doi: 10.1016/j.ifacol.2015.08.134.
[107] Z. Liu, C. Li, Q. Ding, and D. Wu, “A coal mine personnel global
positioning system based on wireless sensor networks,” in Proc.
8th World Congr. Intell. Control Autom., Jul. 2010, pp. 7026–7031,
```
doi: 10.1109/WCICA.2010.5554279.
```
[108] J. Baek, Y. Choi, C. Lee, J. Suh, and S. Lee, “BBUNS:
Bluetooth beacon-based underground navigation system to support
mine haulage operations,” Minerals, vol. 7, no. 11, p. 228, Nov. 2017,
```
doi: 10.3390/min7110228.
```
[109] M. Bolic, M. Rostamian, and P. M. Djuric, “Proximity detection with
```
RFID: A step toward the Internet of Things,” IEEE Pervasive Comput.,
```
vol. 14, no. 2, pp. 70–76, Apr. 2015, doi: 10.1109/MPRV.2015.39.
ZHANG et al.: RECENT ADVANCEMENTS IN IoT IMPLEMENTATION 14525
[110] A. E. Kianfar, F. Uth, R. Baltes, and E. Clausen, “Development
of a robust ultra-wideband module for underground positioning
and collision avoidance,” Min. Metallurgy Explor., vol. 37, no. 6,
pp. 1821–1825, Dec. 2020, doi: 10.1007/s42461-020-00279-6.
[111] Y. Kim, J. Baek, and Y. Choi, “Smart helmet-based personnel proximity
warning system for improving underground mine safety,” Appl. Sci.,
vol. 11, no. 10, p. 4342, Jan. 2021, doi: 10.3390/app11104342.
[112] H. Ullah, N. G. Nair, A. Moore, C. Nugent, P. Muschamp,
and M. Cuevas, “5G communication: An overview of vehicle-to-
everything, drones, and healthcare use-cases,” IEEE Access, vol. 7,
pp. 37251–37268, 2019, doi: 10.1109/ACCESS.2019.2905347.
[113] M. Cavur and E. Demir, “RSSI-based hybrid algorithm for real-
time tracking in underground mining by using RFID technol-
ogy,” Phys. Commun., vol. 55, Dec. 2022, Art. no. 101863,
```
doi: 10.1016/j.phycom.2022.101863.
```
[114] K. Nishikawa, T. Higashino, K. Tsukamoto, and S. Komaki, “Two
dimensional position detection method using bi-directional leaky
coaxial cable based on TDOA,” in Proc. IEEE 20th Int. Symp.
Pers. Indoor Mobile Radio Commun., Sep. 2009, pp. 2167–2170.
```
doi: 10.1109/PIMRC.2009.5450156.
```
[115] V. Ramya, N. Kavya, N. Kavana, G. Kavya, and K. V. Kavya,
“Intelligent helmet for miners,” in Proc. Int. Conf. Design Innov.
```
3Cs Compute Commun.Control (ICDI3C), Jun. 2021, pp. 234–238.
```
```
doi: 10.1109/ICDI3C53598.2021.00054.
```
[116] T. Eldemerdash, R. Abdulla, V. Jayapal, C. Nataraj, and K. Abbas,
“IoT based smart helmet for mining industry application,” Int. J. Adv.
Sci. Technol., vol. 29, no. 1, p. 16, 2020.
[117] A. Geetha, “Intelligent helmet for coal miners with voice over ZigBee
and environmental monitoring,” Middle-East J. Sci. Res., vol. 20, no. 7,
pp. 1–4, 2014, doi: 10.5829/idosi.mejsr.2014.20.07.243.
[118] T. Porselvi, C. S. S. Ganesh, B. Janaki, K. Priyadarshini, and
S. S. Begam, “IoT based coal mine safety and health mon-
itoring system using LoRaWAN,” in Proc. 3rd Int. Conf.
```
Signal Process. Commun. (ICPSC), May 2021, pp. 49–53,
```
```
doi: 10.1109/ICSPC51351.2021.9451673.
```
[119] H. Wen, W. Wu, X. Zheng, and J. Guo, “Application and devel-
opment trend of radar detection technology in mine rescue,”
in Proc. 11th Int. Mine Ventilation Congr., 2019, pp. 942–950,
```
doi: 10.1007/978-981-13-1420-9_80.
```
[120] A. H. Reddy, B. Kalyan, and C. S. N. Murthy, “Mine rescue robot
system—A review,” Procedia Earth Planet. Sci., vol. 11, pp. 457–462,
Jan. 2015, doi: 10.1016/j.proeps.2015.06.045.
[121] S. Saydam, B. Hebblewhite, M. Karmis, and M. Hitch. “Mines of the
Future.” 2019. [Online]. Available: https://miningprofs.org/
[122] M. Kozielski, M. Sikora, and Ł. Wróbel, “Data on methane concentra-
tion collected by underground coal mine sensors,” Data Brief, vol. 39,
Dec. 2021, Art. no. 107457, doi: 10.1016/j.dib.2021.107457.
[123] D. ´Sle¸zak et al., “A framework for learning and embedding multi-
sensor forecasting models into a decision support system: A case study
of methane concentration in coal mines,” Inf. Sci., vols. 451–452,
pp. 112–133, Jul. 2018, doi: 10.1016/j.ins.2018.04.026.
[124] P. Lyu, N. Chen, S. Mao, and M. Li, “LSTM based encoder–decoder for
short-term predictions of gas concentration using multi-sensor fusion,”
Process Safety Environ. Protect., vol. 137, pp. 93–105, May 2020,
```
doi: 10.1016/j.psep.2020.02.021.
```
[125] H. Liu, J. Zhong, C. Lee, S.-W. Lee, and L. Lin, “A comprehensive
review on piezoelectric energy harvesting technology: Materials, mech-
anisms, and applications,” Appl. Phys. Rev., vol. 5, no. 4, Dec. 2018,
Art. no. 041306, doi: 10.1063/1.5074184.
[126] A. Mouapi, N. Hakem, and N. Kandil, “Cantilevered piezoelectric
micro generator design issues and application to the mining
locomotive,” Energies, vol. 13, no. 1, p. 63, Dec. 2019,
```
doi: 10.3390/en13010063.
```
[127] M. Khazaee, A. Rezaniakolaie, A. Moosavian, and L. Rosendahl,
“A novel method for autonomous remote condition monitor-
ing of rotating machines using piezoelectric energy harvesting
approach,” Sens. Actuators A Phys., vol. 295, pp. 37–50, Aug. 2019,
```
doi: 10.1016/j.sna.2019.05.016.
```
[128] J. Le Scornec, B. Guiffard, R. Seveno, V. Le Cam, and
S. Ginestar, “Self-powered communicating wireless sensor with flex-
ible aero-piezoelectric energy harvester,” Renew. Energy, vol. 184,
pp. 551–563, Jan. 2022, doi: 10.1016/j.renene.2021.11.113.
[129] J. C. Rodriguez, V. Nico, and J. Punch, “A vibration energy har-
vester and power management solution for battery-free operation of
wireless sensor nodes,” Sensors, vol. 19, no. 17, p. 3776, Jan. 2019,
```
doi: 10.3390/s19173776.
```
[130] K. Z. Ghafoor et al., “Millimeter-wave communication for
Internet of Vehicles: Status, challenges, and perspectives,” IEEE
Internet Things J., vol. 7, no. 9, pp. 8525–8546, Sep. 2020,
```
doi: 10.1109/JIOT.2020.2992449.
```
[131] D. M. Vavriv, O. O. Bezvesilniy, V. A. Volkov, A. A. Kravtsov,
and E. V. Bulakh, “Recent advances in millimeter-wave radars,” in
```
Proc. Int. Conf. Antenna Theory Techn. (ICATT), Apr. 2015, pp. 1–6.
```
```
doi: 10.1109/ICATT.2015.7136774.
```
[132] J. Pegoraro, F. Meneghello, and M. Rossi, “Multiperson continuous
tracking and identification from mm-Wave micro-doppler signatures,”
IEEE Trans. Geosci. Remote Sens., vol. 59, no. 4, pp. 2994–3009,
Apr. 2021, doi: 10.1109/TGRS.2020.3019915.
[133] F. Wang, X. Zeng, C. Wu, B. Wang, and K. J. R. Liu,
“Driver vital signs monitoring using millimeter wave radio,” IEEE
Internet Things J., vol. 9, no. 13, pp. 11283–11298, Jul. 2022,
```
doi: 10.1109/JIOT.2021.3128548.
```
[134] K. Yoneda, N. Hashimoto, R. Yanase, M. Aldibaja, and N. Suganuma,
“Vehicle localization using 76GHz omnidirectional millimeter-wave
radar for winter automated driving,” in Proc. IEEE Intell. Veh. Symp.
```
(IV), Jun. 2018, pp. 971–977. doi: 10.1109/IVS.2018.8500378.
```
[135] M. Geiger and C. Waldschmidt, “160-GHz radar proximity sensor with
distributed and flexible antennas for collaborative robots,” IEEE Access,
vol. 7, pp. 14977–14984, 2019, doi: 10.1109/ACCESS.2019.2891909.
[136] Z. Lin, T. Lv, and P. T. Mathiopoulos, “3-D indoor posi-
tioning for millimeter-wave massive MIMO systems,” IEEE
Trans. Commun., vol. 66, no. 6, pp. 2472–2486, Jun. 2018,
```
doi: 10.1109/TCOMM.2018.2797993.
```
[137] J. Gante, G. Falcão, and L. Sousa, “Beamformed fingerprint
learning for accurate millimeter wave positioning,” in Proc.
```
IEEE 88th Veh. Technol. Conf. (VTC-Fall), Aug. 2018, pp. 1–5,
```
```
doi: 10.1109/VTCFall.2018.8690987.
```
[138] X. Tan, Z. Sun, D. Koutsonikolas, and J. M. Jornet, “Enabling indoor
mobile millimeter-wave networks based on smart reflect-arrays,” in
```
Proc. IEEE Conf. Comput. Commun. (IEEE INFOCOM), Apr. 2018,
```
pp. 270–278, doi: 10.1109/INFOCOM.2018.8485924.
[139] Y. Chen et al., “Downlink performance analysis of intelligent reflecting
surface-enabled networks,” IEEE Trans. Veh. Technol., vol. 72, no. 2,
pp. 2082–2097, Feb. 2023, doi: 10.1109/TVT.2022.3211545.
[140] O. Kolade and L. Cheng, “Memory channel models of a
hybrid PLC-VLC link for a smart underground mine,” IEEE
Internet Things J., vol. 9, no. 14, pp. 11893–11903, Jul. 2022,
```
doi: 10.1109/JIOT.2021.3132129.
```
[141] F. Seguel, I. Soto, P. Adasme, N. Krommenacker, and P. Charpentier,
“Potential and challenges of VLC based IPS in underground mines,” in
```
Proc. 1st South Amer. Colloquium Visible Light Commun. (SACVLC),
```
Nov. 2017, pp. 1–6, doi: 10.1109/SACVLC.2017.8267610.
[142] A. Memedi and F. Dressler, “Vehicular visible light communications:
A survey,” IEEE Commun. Surveys Tuts., vol. 23, no. 1, pp. 161–181,
1st Quart., 2021, doi: 10.1109/COMST.2020.3034224..
Huili Zhang received the B.Sc. degree in energy and
power engineering from the University of Science
and Technology Beijing, Beijing, China, in 2019,
and the M.Sc. degree in renewable energy engi-
neering from the University of New South Wales,
Sydney, NSW, Australia, in 2021, where she is cur-
rently pursuing the Ph.D. degree with the School of
Minerals and Energy Resources Engineering.
Her research interests mainly focus on vibration
energy harvesting and sensing for mine Internet of
Things.
```
Binghao Li (Senior Member, IEEE) received the
```
B.Sc. degree in electrical and mechanical engi-
neering from Beijing Jiaotong University, Beijing,
China, in 1994, the M.Sc. degree in civil engineer-
ing from Tsinghua University, Beijing, in 2001, and
the Ph.D. degree in spatial information systems from
the University of New South Wales, Sydney, NSW,
Australia, in 2006.
He is currently an Associate Professor and
a Leader with the MIoT & IPIN Lab, School
of Minerals and Energy Resources Engineering,
University of New South Wales. His research interests include indoor
positioning, pedestrian navigation, satellite positioning and navigation, and
mine Internet of Things.
14526 IEEE INTERNET OF THINGS JOURNAL, VOL. 10, NO. 16, 15 AUGUST 2023
Mahmoud Karimi received the B.Sc. degree
in mechanical engineering from Azad University,
Karaj, Iran, in 2006, the M.Sc. degree in mechan-
ical engineering from Iran University of Science
and Technology, Tehran, Iran, in 2010, and the
Ph.D. degree in mechanical engineering from the
University of New South Wales, Sydney, NSW,
Australia, in 2016.
He is currently an ARC DECRA Fellow and a
Senior Lecturer with the Centre for Audio, Acoustics
and Vibration, University of Technology Sydney,
Sydney. His research interests include computational vibration and acoustics,
flow-induced noise and vibrations, uncertainty quantifications in mechanical
systems, and identification of stochastic vibration forces.
Serkan Saydam received the B.Sc., M.Sc., and
Ph.D. degrees in mining engineering from Dokuz
Eylul University, Izmir, Turkey, in 1992, 1995, and
2000, respectively.
He was a Postdoctoral Fellow with the University
of Witwatersrand, Johannesburg, South Africa.
He is currently a Professor and a Chair of
Mining Engineering with the School of Minerals
and Energy Resources Engineering, University of
New South Wales, Sydney, NSW, Australia. His
research interests include space resources engineer-
ing, ground control, mine systems design, mine Internet of Things, and
technology integration and management.
```
Prof. Saydam is currently a Fellow Member of AusIMM; the President of
```
```
the ISRM Commission on Planetary Rock Mechanics; the Deputy Director
```
```
of the Australian Centre for Space Engineering Research at UNSW; and the
```
Deputy Secretary-General and a Council Member of The Society of Mining
Professors.
```
Mahbub Hassan (Senior Member, IEEE) received
```
the B.Sc. degree in computer engineering from
Middle East Technical University, Ankara, Turkey,
in 1989, the M.Sc. degree in computer science from
the University of Victoria, Victoria, BC, Canada,
in 1991, and the Ph.D. degree in computer sci-
ence from Monash University, Melbourne, VIC,
Australia, in 1998.
He is currently a Professor with the School of
Computer Science and Engineering, University of
New South Wales, Sydney, NSW, Australia. His
research interests include mobile networks, nanoscale wireless sensor network,
self-powered and energy-harvesting wireless networks, Internet of Things, and
wearable computing.
```
Prof. Hassan was a Distinguished Lecturer of IEEE (COMSOC) from 2013
```
to 2016. He is currently an Editor of IEEE C OMMUNICATIONS S URVEYS
AND T UTORIALS and has previously served as a Guest Editor for IEEE
N ETWORK and an Associate Technical Editor for the IEEE Communications
Magazine.