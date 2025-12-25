

Reliability Engineering and System Safety 256 (2025) 110760
Available online 13 December 2024
0951-8320/© 2024 Published by Elsevier Ltd.
IoT-Bayes fusion: Advancing real-time environmental safety risk
monitoring in underground mining and construction
## Milad Mousavi
a
## , Xuesong Shen
a,*
## , Zhigang Zhang
b
## , Khalegh Barati
a
## , Binghao Li
c
a
School of Civil and Environmental Engineering, UNSW, Sydney, NSW 2052, Australia
b
Chongqing Research Institute of China Coal Technology & Engineering Group, Chongqing, China
c
School of Mineral and Energy Resources Engineering, UNSW, Sydney, NSW 2052, Australia
## ARTICLE INFO
## Keywords:
Real-time safety risk monitoring
Underground mining and construction
Bayesian networks
Internet of Things
Environmental safety knowledge modeling
Coal mining
## ABSTRACT
Effectively managing environmental hazards in  underground mining and  construction sites is  a  formidable
challenge for project managers and site engineers. These complex underground systems are characterized by
inadequate ventilation, hazardous gases, and elevated levels of heat and humidity. However, conventional ap-
proaches to underground risk management often rely on static and oversimplified methodologies, which limit the
ability to accurately predict and control these multifaceted hazards. This research aims to develop an innovative
real-time safety risk monitoring system tailored to underground environments. The proposed system facilitates
dynamic and  remote monitoring, analysis, and  control of  safety risks within underground workspaces. The
methodology integrates data streams from Internet of Things (IoT) sensors to perceptively capture the under-
ground environment, combined with the application of Bayesian networks (BNs) as a robust probabilistic risk
modeling engine. To demonstrate the practicality of the proposed system, two proof-of-concept examples using
real datasets collected from underground coal mines in Poland and China are presented. The demonstration
effectively showcases the  system’s  applicability and  potential benefits. Upon implementation, the  proposed
system will enable real-time and remote monitoring of underground ecosystems, significantly enhancing the
safety and reliability of underground operations.
## 1. Introduction
In recent years, the global economy and mineral prices have expe-
rienced substantial fluctuations, coupled with persistent political un-
certainties. These challenges have significantly impacted the
underground sector, raising concerns not only about economic viability
but also about the safety and well-being of the workforce operating in
these environments. The  industry faces numerous issues, including
declining productivity, a  shortage of skilled workers, and  increasing
concerns about its social and environmental impacts [1]. As shallow coal
seams become unsustainable, underground coal mining ventures deeper
in search of viable deposits [2]. However, deeper mining brings wors-
ening environmental conditions that directly affect worker safety,
including poor ventilation, hazardous gas releases, and high heat levels
## [3].
Despite technological advancements, historical assessments of coal
mine accidents show that major explosions and safety incidents remain
difficult to prevent, and current safety measures are often inadequate
[4]. The complex nature of coal mine accidents, influenced by a com-
bination of factors rather than a single cause, adds layers of complexity
to  risk  management in  this  industry [5].  Additionally, underground
construction environments pose further safety hazards, such as  wall
inclination, water level fluctuations, ground surface settlement, and
pillar settlement [6], which significantly threaten worker safety and
well-being. Given these complex and  multifaceted risks, accurately
predicting and  managing them effectively is  a  significant challenge.
Therefore, adopting innovative approaches, promoting best practices,
and implementing additional safety measures are crucial to ensuring
worker safety and maintaining productivity in underground operations.
In underground environments, real-time processing capabilities are
crucial due to concerns about environmental hazards. To address this,
the widespread use of sensing devices, such as environmental sensors,
has become prevalent [7]. These sensors provide immediate measure-
ments of key environmental indicators, allowing for the identification
and  monitoring of  potential dangers [8].  In  coal mines, integrating
monitoring, supervision, and  dispatching systems with machinery,
*Corresponding author.
E-mail address: x.shen@unsw.edu.au(X. Shen).
Contents lists available at ScienceDirect
Reliability Engineering and System Safety
journal homepage: www.elsevier.com/locate/ress
https://doi.org/10.1016/j.ress.2024.110760
Received 20 March 2024; Received in revised form 15 September 2024; Accepted 12 December 2024

Reliability Engineering and System Safety 256 (2025) 110760
## 2
devices, and transportation networks is a common practice. These sys-
tems primarily monitor natural hazards such as methane levels, seismic
activity, and fires. However, the data collected from these systems is
typically used for visual purposes and lacks the in-depth analysis needed
to enhance various coal mining processes [9]. Often, the expertise of
safety managers and site engineers is relied upon to monitor and inter-
pret real-time sensing data. However, this expertise is often subjective
and  heavily dependent on  individual experiences. Additionally, its
transient nature, combined with the potential turnover of these experts,
makes it an unreliable and insufficient long-term organizational asset.
In many regions worldwide, the mining and construction industries
still rely on manual methods to evaluate safety risks [10]. However,
numerous studies have highlighted the limitations of traditional analysis
techniques in quantitatively assessing risks, managing uncertainty, and
implementing dynamic control measures [11]. In the highly competitive
construction and mining sectors, any disruption in production can lead
to  missed targets, increased costs, and  reduced profitability. Abnor-
malities or deviations in environmental conditions can hinder smooth
underground operations, resulting in productivity losses and financial
setbacks. Similarly, delays or inefficiencies in sensor data processing
within underground spaces can have the same detrimental effects [
## 12].
Conventional data analysis methods often struggle to manage the large
volume, high speed, and diverse nature of data generated in under-
ground environments [13].  Most existing advanced risk  assessment
methods are predominantly offline and static, making them inadequate
for addressing the dynamic nature of underground risks and failing to
explore the non-linear relationships within safety data [
## 14,15]. There-
fore, it is crucial to develop efficient and timely processing methods for
the continuous influx of sensor data to ensure optimal safety and pro-
ductivity in underground operations.
Despite advancements in sensing technologies and data collection in
underground environments, several critical gaps remain. Current
monitoring systems mainly focus on visual data representation and lack
the analytical depth needed to provide actionable, real-time insights.
The reliance on human expertise to interpret sensor data introduces
subjectivity and inconsistency, undermining long-term safety manage-
ment. Furthermore, conventional risk assessment methods are largely
static and offline, making them ill-suited for the dynamic and complex
nature of underground risks. These methods struggle to handle the vast,
rapidly changing, and diverse data generated in underground operations
and fail to explore the non-linear relationships inherent in safety data.
As a result, there is a clear need for an integrated, data-driven approach
that enables proactive, real-time monitoring, assessment, and control of
safety risks.
This paper aims to develop a real-time safety risk monitoring and
assessment system tailored for underground working environments. The
system seeks to address the limitations of conventional static methods by
enabling dynamic, remote monitoring, analysis, and control of safety
risks in  underground spaces. To  achieve this, the  study employs
Bayesian Networks (BNs), renowned for their robust risk assessment
capabilities, to effectively represent the complex and probabilistic na-
ture of safety risks in underground mining and construction environ-
ments. The system integrates real-time data streams from Internet of
Things (IoT) sensors as  inputs to  the  BNs, facilitating continuous
monitoring of safety risks. The practicality of the proposed system is
demonstrated through two proof-of-concept examples using real data
collected from underground coal mines in Poland and China. By meeting
these objectives, the research aims to enhance underground safety by
providing a comprehensive and efficient approach to real-time envi
## -
ronmental safety risk  monitoring, empowering safety decisions, and
mitigating potential hazards.
The paper is structured as follows: Section 2offers a comprehensive
review of  the  relevant literature. Section 3introduces the  proposed
methodology, highlights its  key  components, and  outlines the  steps
involved. Section 4presents two proof-of-concept case studies, demon-
strating the  significance and  practical implications of  the  proposed
framework. Finally, Section 5concludes the paper by summarizing the
main findings, highlighting their contributions, and providing sugges-
tions for future research directions.
- Background and context
This section reviews the latest methods and techniques for enhancing
safety in underground construction and mining operations.
2.1. Underground safety challenges and risk assessment methods
Li, et al. [16] established a comprehensive database of underground
construction safety risks by integrating knowledge structuring, ques
## -
tionnaires, interviews, and group decision-making. They highlighted the
complexity of underground construction risks, which are influenced by
factors such as architectural forms, construction techniques, geological
conditions, and surroundings. In underground mines, ventilation sys-
tems that address gases like CH
## 4
## , NO
x
## , SO
## 2
, CO, and CO
## 2
significantly
impact energy expenditure [1]. Gas accidents are common in coal mines,
with methane-related incidents occurring frequently [11]. Mine fires
and explosions are typical hazards in underground coal mining, often
caused by  the  spontaneous combustion of  coal, ignited firedamp
(methane-air mixture), and coal dust [17].
Risk analysis techniques in underground engineering include both
qualitative methods (e.g., safety checklists, Delphi technique, in-
terviews) and quantitative approaches (e.g., event tree analysis, fault
tree analysis, neural networks) [
11]. In the mining industry, there has
been increasing emphasis on risk assessment and management, consid-
ering ecological, social, and  economic factors, as  reflected in  the
growing number of publications and reports on these topics. Given the
extensive nature of mining operations and their interactions with the
environment, thorough risk analysis is essential for ensuring operational
accuracy, equipment safety, and  minimizing environmental impact
## [18].
Cascading hazards in underground projects present significant risks
due to the interconnected nature of various infrastructure systems and
the  complexity of  the  environment. Zhang, et  al.  [19]  proposed an
improved risk assessment methodology that integrated Failure Mode
and  Effects Analysis (FMEA) with normal wiggly hesitant fuzzy sets
(NWHFSs) to enhance expert evaluations of risk factors. The approach
gathered insights from experts, grouped them effectively, and ranked
the potential risks to identify the most critical ones. This helped improve
safety and decision-making in utility tunnel construction projects. Bai,
et al. [
20] proposed an innovative energy-based coupling risk assess-
ment (CRA) model to quantitatively analyze the risks associated with
utility tunnels, which housed various hazardous pipelines. They iden-
tified six types of energy and numerous cascading accident scenarios,
emphasizing the  generalized coupling effect, where changes in  one
component impacted another. The case studies demonstrated significant
fatality and economic risks from natural gas explosions, cable fires, and
rain-triggered ponding, underscoring the need for improved preventive
measures. Hai, et al. [21] identified several limitations in existing risk
assessment methods for cascading underground hazards. They pointed
out that many studies focused on static analyses of individual risk fac-
tors, neglecting the dynamic interactions between multiple risks. Addi-
tionally, there was a  lack of  dynamic models that accounted for
multifactor conditions. To address these issues, the authors called for
improved risk indicator systems to enhance efficiency and objectivity, as
well as the incorporation of coupling effects between risk factors in risk
management practices to ensure comprehensive assessments.
2.2. Leveraging Bayesian networks for underground risk assessment
BNs  are  graphical models that  analyze probabilistic relationships
among variables using directed acyclic graphs (DAGs). These models
consist of  nodes representing variables, connected by  arrows that
M. Mousavi et al.

Reliability Engineering and System Safety 256 (2025) 110760
## 3
indicate causality. Since their initial adoption in the late 1990s, BNs
have been widely used in risk assessment, reliability analysis, accident
modeling, diagnostics, and prognostics [14]. Typically, both the struc-
ture and parameters of a BN are determined by learning from sufficient
data. For example, Li, et al. [22] used BNs to predict rockburst risks in
underground spaces. They estimated conditional probabilities from a
dataset of 135 rockburst case histories, including 83 rockburst cases and
52 non-rockburst cases.
In some research areas, data collection can be challenging. In such
cases, expert knowledge can be used to determine the BN structure. Wu,
et al. [23] presented a quantitative risk assessment method for urban
underground utility tunnels using BN modeling. The study identified the
worst-case accident scenario involving gas pipeline leakage and incor-
porated domino effects into the risk analysis. Due to the scarcity of
utility tunnel accident data, expert elicitation and traditional data were
used to determine conditional probability tables (CPTs). The proposed
method was able to quantitatively evaluate risks, support safety man-
agement, and  assist in  emergency decision-making for  urban utility
tunnel accidents. Tong, et al. [
24] developed a BN to explore factors
contributing to  mine gas  explosions. The  model integrated expert
knowledge and probabilities derived from the Delphi method, address-
ing the complex interplay of multiple gas sources and their impacts. The
model effectively represented influential factors, accounted for  un
## -
certainties during disaster evolution, and allowed for dynamic proba-
bility updates. Wu, et al. [25] introduced a Dynamic Bayesian Network
(DBN) to  analyze the  gradual damage to  road surfaces caused by
tunneling activities over time. The  authors used relevant standards,
technical reports, expert experiences, and fault trees to construct the
DBN and establish relationships.
Recent advancements in  integrating BNs  with various tools and
modeling frameworks were comprehensively examined by Marcot and
Penman [26]. Notably, the literature reflects a growing trend of incor-
porating BN  models into management decision networks, causal
network modeling through structural equation modeling, Bayesian
neural networks, hybrid discrete and  continuous variable models,
object-oriented and  agent-based models, state-and-transition models,
geographic information systems, and even quantum probability. The
authors highlight a significant research gap, emphasizing the need for
self-updating and self-improving BNs capable of learning from real-time
continuous inputs derived from monitoring data.
2.3. IoT for enhanced underground safety monitoring
The IoT technology has been extensively used in various sectors,
including manufacturing and transportation, offering effective solutions
[27]. Recently, IoT integration has led to positive changes in under-
ground safety, resulting in improved safety protocols and operational
efficiency. Wu, et al. [4] conducted a study on an IoT-based dynamic
information platform specifically designed for underground coal mines.
This platform used IoT technology to monitor and record operational
data related to coal mine production systems and track the locations of
underground equipment and miners. Key components of the platform
included a 3D virtual mine system, a safety diagnosis system, a safety
inspection system, and an emergency rescue system. In a separate study,
Zhang, et al. [28] proposed an Artificial Intelligence Internet of Things
(AIoT) system for  real-time monitoring of  tunnel construction. IoT
sensors were effectively deployed to capture real-time shield data pa
## -
rameters. Before tunnel construction, a detailed determination of geo-
metric and geological parameters was carried out. The authors used
Random Forest models to achieve accurate predictions of operational
parameters for successive rings and resulting settlement.
Ye, et al. [29] emphasized the critical role of IoT in enhancing safety
management and early warning systems in tunnel construction, which
often faces accidents due to challenging geological conditions. Their
proposed digital twin (DT) platform utilized IoT technologies to facili-
tate real-time data collection and monitoring through wireless sensor
networks, enabling dynamic interaction between physical and virtual
environments. By integrating multi-source data, the platform improved
safety management accuracy and allowed for timely responses to po-
tential hazards. Liu, et al. [30] focused on optimizing fire emergency
response in metro systems, using the Simenkou metro station in Wuhan
as a case study. The authors developed a multi-objective optimization
model to minimize both the number of firefighters deployed and the
total emergency response time during a fire. A key element of their
approach was the integration of IoT, which allowed commanders to
make informed decisions based on real-time data from sensors. This
method improved the coordination of firefighting teams and ensured a
more efficient allocation of resources during emergencies. The study
highlighted that IoT’s ability to provide immediate feedback was crucial
for enhancing the overall effectiveness of emergency response strategies
in urban environments.
Zhou, et al. [31] examined the technical challenges associated with
deep underground activities, particularly focusing on rockburst risks
and  rock mass instability. The  authors reviewed various assessment
methods, including empirical approaches, simulations, mathematical
modeling, and microseismic monitoring, while emphasizing the impor-
tance of control strategies for effective energy utilization within rock
masses. The paper suggested six directions for implementing intelligent
management techniques to mitigate hazards during underground oper-
ations. It highlighted the role of IoT technology in mine monitoring and
management, which enabled equipment connectivity and real-time data
collection, thereby enhancing the accuracy and efficiency of rockburst
prediction and prevention. Zhang, et al. [
32] introduced the concept of
the Mine Internet of Things (MIoT) and discussed its potential contri
## -
butions to enhancing mine safety. MIoT was described as a network of
interconnected sensors and actuators installed at mine sites, designed to
enable real-time monitoring, accident prediction, process optimization,
and effective personnel and equipment management. The authors out-
lined the fundamental structure of MIoT systems, which consists of three
layers: the perception and control layer, the network layer, and the
application layer. The  study highlighted various MIoT applications,
including environmental monitoring, fire  detection, personnel and
equipment positioning, and production safety management.
2.4. Research gaps
State-of-the-art literature highlights significant progress in
enhancing underground safety monitoring and risk assessment through
advanced probabilistic models and  IoT  technologies. BNs  have been
widely adopted for modeling complex underground risk scenarios, using
both data-driven and expert-based approaches to establish probabilistic
relationships among critical variables. These models have proven
effective in analyzing accident causes, predicting risks like gas explo
## -
sions, and  supporting decision-making processes. Additionally, IoT
technologies have revolutionized underground safety by enabling real-
time monitoring of  environmental conditions, equipment, and
personnel. Integrated platforms now offer a  comprehensive view of
operational data, enhancing situational awareness and facilitating better
emergency response and resource allocation. The incorporation of AI
algorithms, such as  machine learning models, has  further improved
predictive accuracy, allowing for  timely interventions to  prevent
accidents.
Despite these advancements, current systems often struggle to pro-
vide real-time, actionable insights essential for effective risk manage-
ment in dynamic underground environments. Most existing BN-based
risk  assessment models rely  on  static data or  human interpretation,
limiting their ability to adapt dynamically to real-time changes. This
lack of adaptability reduces their effectiveness in rapidly evolving con-
ditions, where timely risk predictions are crucial. Moreover, while IoT
systems have significantly enhanced data availability, their integration
with advanced probabilistic models like BNs remains underexplored,
particularly in real-time risk prediction and decision-making contexts.
M. Mousavi et al.

Reliability Engineering and System Safety 256 (2025) 110760
## 4
Fig. 1.Proposed IoT-Bayes framework for real-time underground environmental safety risk management.
Fig. 2.The cause-consequence correlation and CPTs in a BN for environmental safety accidents.
M. Mousavi et al.

Reliability Engineering and System Safety 256 (2025) 110760
## 5
Addressing these gaps could lead to more dynamic and responsive risk
management systems, paving the way for safer underground operations.
- Proposed framework
Fig. 1presents an overview of the research framework, which con-
sists of  four interconnected modules. The first module involves
deploying IoT sensors in the underground environment to collect data
on environmental factors such as methane levels, wind speed, temper-
ature, and  atmospheric pressure. This environmental data is  then
cleaned and labeled based on specified thresholds in the data prepara-
tion module, before being used as input for the developed BN. The BN
assesses safety incidents in  real-time, updating the  probabilities and
outcomes of  accidents based on  interrelated causes. The  BN’s risk
evaluation results are displayed graphically to compare different sce-
narios, aiding safety operators in decision-making. Detailed explana-
tions of each framework module are provided in the following sections.
3.1. Environmental perception
The IoT is defined as a multi-layered system that enables the inter-
connection of devices and real-time data visualization through three key
layers: sensing, transmission, and application. The sensing layer consists
of various sensors that collect critical environmental data, forming the
foundation of IoT. The transmission layer ensures the reliable transfer of
these data packets from the sensing devices to a centralized data pro-
cessing center, often requiring relay nodes such as  base stations to
maintain efficient communication. Lastly, the  application layer pro-
cesses and  analyzes the  collected data, enabling improved decision-
making and  service delivery—crucial for  enhancing system control
and risk management in industrial environments [
33]. IoT is  distin-
guished by  its  ability to  connect all  equipment within an  industrial
system, facilitating the sharing of accurate, timely information essential
for effective risk management. By integrating IoT, the system achieves
real-time centralized control, minimizing decision-making errors and
improving responsiveness to emergencies, thereby reducing the spread
of risk. This comprehensive and integrated IoT network significantly
enhances the  system’s ability to  manage, avoid, and  mitigate risks,
addressing the critical need for information integrity in industrial en-
vironments [34].
The first module of the proposed framework utilizes IoT sensors to
gather real-time underground environmental data. These sensors mea
## -
sure parameters such as gas concentration, wind speed, air pressure,
temperature, and humidity. Therefore, the sensors must be strategically
installed throughout the underground space, following a deployment
strategy that ensures comprehensive coverage of  environmental
conditions. Key  locations requiring continuous monitoring in  under-
ground environments include the working face, ventilation gates, and
roadways. The data collection interval varies, ranging from seconds to
hours, depending on the specific hazards being investigated, the envi
## -
ronmental factors under consideration, regulatory requirements, the
type of  underground environment, and  its  inherent characteristics.
Careful planning of the deployment strategy is essential to accommodate
these factors.
The collected data must be transmitted to a designated data storage
system for subsequent use in the following modules of the proposed
framework. In coal mining applications, industry standards and com-
mon practices recommend Wi-Fi as the primary wireless technology for
data transmission, followed by  LTE  and  5  G  [
35].  Therefore, when
selecting data transmission tools, careful consideration should be given
## Table 1
Causes and consequences of methane explosions in underground coal mines.
CategoryInfluenced ByInfluencing On
## Causes
Ignition sourcesFriction spark; Open fire; Electric spark;
Spontaneous heating
## Methane
explosion
Methane overrunMethane emission from goaf; Leakage of
methane drainage pipe; Methane
discharge from coal seam; Ventilation
conditions; Preventive measures
## Methane
explosion
Concentration of
oxygen
NoneMethane
explosion
## Ventilation
conditions
Atmospheric pressure change; Wind
speed
## Methane
overrun
## Consequences
## Successive
explosions
Methane explosion; Mitigative measuresCasualties;
Economic loss
CasualtiesMethane explosion; Successive
explosions; Mitigative measures
## None
Economic lossMethane explosion; Successive
explosions; Mitigative measures
## None
## Table 2
Experts’ opinions for enhancing the developed BN.
## Modification
## Type
Subject Variable(s)Experts Commentary
Remove a
variable
Atmospheric pressure changeChanges in air pressure can
cause an increase in the
methane emission rate,
especially from the extracted
areas, and can also alter the
explosive range of methane.
Since this study measures the
final concentration of methane
in the mine roadways through
sensors, the methane emission
rate is not a determining factor.
Therefore, changes in air
pressure cannot be considered
as a direct influencing factor on
ventilation conditions.
Remove a
variable
Concentration of oxygenThe level of oxygen available
in roadways, considering its
direct relationship with the
quality of the air necessary for
personnel respiration, is not a
factor that can be altered to
control explosions. Therefore,
in most cases, the available
oxygen level will always
remain within a constant and
safe range.
Add an
assumption
Wind speedThe wind speed itself cannot
determine the ventilation
status; instead, the quantity of
air indicates the required air
volume to dilute the flammable
gases. However, considering
that this study takes place in a
specific location in the mine
and assuming a constant
roadway geometry, the wind
speed can be considered to
represent the quantity of air.
Add a variableInflow qualityIn addition to the air quantity,
the level of methane in the
incoming air also affects the
ventilation conditions. This
methane level can be measured
using sensors installed in the
maingate.
Add a
relationship
Preventive Measures; IgnitionPreventive measures can be
used not only to reduce the
methane concentration in the
atmosphere but also to
eliminate or mitigate the
ignition sources.
## Combine
variables
Methane emission from goaf;
Leakage of methane drainage
pipe; Methane discharge from
coal seam
Since the final methane
concentration in the tailgate is
determined using sensors, it is
not necessary to break it down
into its emission sources.
M. Mousavi et al.

Reliability Engineering and System Safety 256 (2025) 110760
## 6
to these wireless technologies based on their suitability for the under-
ground environment. Further insights into the use of communication
technologies in underground settings can be found in the study by Li and
## Saydam [36].
3.2. Data preparation
The likelihood of generating flawed data is minimized when sensors
are  accurately installed and  calibrated. However, since IoT  data is
collected and transmitted in real-time, missing data may still occur in
the collected dataset. Several factors contribute to missing data in in-
dustrial monitoring systems like IoT sensors, including sensor inactivity,
data transmission dropouts, and data storage failures [37]. These issues
can create gaps in data collection, complicating accurate real-time risk
analysis. Addressing missing data is essential for maintaining the reli-
ability and effectiveness of the proposed risk monitoring system. For
real- time series data, one effective method for handling missing data is
to fill gaps using the most recent meaningful data [38].
The data collected from IoT sensors initially exists as numerical time-
series data, while the BN requires categorical data as input. Therefore, a
crucial data cleaning and thresholding process is necessary to transform
the raw data into a suitable format for the BN. The cleaned data must
undergo thresholding based on the specific requirements of the BN. At
this stage, a review of existing regulations and relevant documents is
needed to  establish appropriate thresholds for  categorizing the  data
generated by each type of sensor. For example, if methane concentration
exceeds one  percent in  certain locations within a  coal mine, it  can
disrupt mining operations and cause concern among workers [39]. As a
result, the one percent threshold can be defined to classify methane
concentration levels as  serious or  slight. Concentrations below this
threshold are labeled as slight, while values exceeding it are classified as
serious. These discrete categories then serve as evidence within the BN
model to update the risk assessment of other nodes in the network. This
logical approach can also be applied to raw environmental data gener-
ated by other sensor types.
3.3. Bayesian network development
The proposed framework incorporates BNs as robust tools for risk
assessment. BNs are DAGs that effectively represent probabilistic re-
lationships among variables. A DAG does not contain cycles, meaning
there is no way to start at one node and follow the directed edges back to
the same node. This structure is essential for modeling causal relation-
ships, as it prevents circular dependencies. The acyclic nature of a DAG
ensures that relationships can be analyzed clearly, enabling efficient
probability computations and a better understanding of complex sys-
tems [40]. In a BN, nodes represent random variables, and directed
edges indicate probabilistic dependencies or  causal relationships be-
tween these variables. Each node can take values from a finite set of
mutually exclusive and collectively exhaustive states [41]. An edge from
node X
j
to node X
i
indicates that X
j
has a direct influence on X
i
## . This
relationship is often interpreted as X
j
being a parent of X
i
, and X
i
being a
child of X
j
. Each node X
i
has an associated conditional probability dis-
tribution P(X
i
|Parents(X
i
)),  which quantifies the  effect of  the  parent
nodes on the child node. If a node has no parents, its distribution is
simply P(X
i
## )[42].
To begin BN modeling, the network structure must be established.
This involves specifying the directed edges to represent dependencies
and conditional independence among the input variables. The structure
is  typically determined using domain knowledge or  data-driven
learning. In the context of safety and disaster risk management, each
node in the BN can represent a potential cause or consequence of acci-
dents [43]. Following this approach, the proposed framework adopts a
similar method for determining the structure of the BN. Fig. 2provides
an example of a cause-consequence relationship selected for investi-
gating environmental safety accidents in this study.
Once the  BN  structure is  defined, it  is  essential to  quantify the
strength of the relationships among variables using CPTs. CPTs specify
the conditional probabilities for each variable, given its parent variables
in the network [44]. Fig. 2shows sample CPTs for three nodes in the
network. Since the preventive measures node has no parent nodes, its
Fig. 3.Final BN for methane explosions in underground coal mines.
M. Mousavi et al.

Reliability Engineering and System Safety 256 (2025) 110760
## 7
CPT defines the prior probability of these measures. The causes node
represents factors that can lead to an accident, such as equipment fail-
ures or unsafe conditions, and it depends on the preventive measures
node. Its  CPT  shows the  probability of  causes occurring, given that
preventive measures are in place. The accidents node depends on the
causes node, and  its  CPT indicates the  probability of  an  accident
occurring, given the presence of causes. Assuming the BN consists of n
nodes, the joint probability distribution over all variables in the network
is expressed by Eq. (1).
## P(U)=P(X
## 1
## ,...,X
n
## )=
## ∏
n
i=1
## P(X
i
## |
π
## (X
i
## ))(1)
where X
i
denotes the i
th
random variable, and π(X
i
)represents the set of
parent nodes of X
i
## .
In  an  ideal scenario, acquiring a  BN’s  structure and  conditional
probabilities can  be  facilitated by  the  availability of  historical data.
However, in the case of environmental safety accidents, particularly
those in underground environments, comprehensive and reliable his-
torical datasets are often limited. As a result, alternative methods must
be employed to construct the BN. A practical approach is to consult
various resources, such as standards, regulations, technical and accident
reports, and scholarly publications, to obtain the structure and condi-
tional probabilities needed for the BN when such datasets are lacking. In
these cases, it  is  crucial to  involve domain experts to  validate the
structure and conditional probabilities of the BN and ensure the accu-
racy of its inference outcomes [25,45].
3.4. Real-Time risk assessment and monitoring
After constructing the BN, the next step is to introduce real-time IoT
data as new evidence into the network. This dynamic process triggers
the belief updating mechanism within the BN. Belief updating recalcu-
lates the probabilities of the nodes (variables) in the BN when new ev-
idence or data is introduced. This involves adjusting the network’s CPTs
to reflect the impact of the new information, ensuring that the posterior
distributions of the variables accurately represent the current state of
knowledge. Essentially, belief updating enables the network to dynam-
ically incorporate observations from sources like inspection measure-
ments or continuous monitoring systems, refining the risk assessment or
prediction based on the most recent data [46]. As new data streams into
the network, the probabilities associated with the accident node are
recalculated considering the  latest information. For  a  variable A
dependent on a variable B, the updated probability is computed using
Bayes’ Theorem as shown in Eq. (2):
## P(a
i
## |b)=
## P(b|a
i
)P(a
i
## )
## P(b)
## (2)
where a
i
denotes the i
th
state of variable A, b is a state of variable B
observed as evidence, P(a
i
|b)is the posterior probability of a
i
given the
evidence b, P(a
i
)is the prior probability of a
i
## , P(b|a
i
)is the likelihood of
observing evidence b given a
i
, and P(b)is the marginal probability of the
evidence b. Inference in BNs involves computing the posterior distri-
bution of a subset of variables given evidence about other variables [42].
Additionally, the probabilities associated with the various causes and
consequences linked to the accident node are also updated. This process
is repeated whenever additional evidence is observed. This continuous
refinement of probabilities allows the BN to provide real-time insights,
adapting to changing conditions and enhancing the accuracy of risk
assessments and predictions.
Based on the risk assessment results obtained from the BN developed
in the previous module, a real-time risk progression chart is generated
for the target nodes, providing decision-makers and safety managers
with valuable insights. This chart helps anticipate safety accidents,
identify probable causes, and implement preventive measures to
## Table 3
An overview of the final BN variables.
TypeVariableDescriptionStatesMode
CauseIgnitionPresence of an
ignition source.
Yes/NoDependent
Open firePresence of open
fire sources such
as smoke, cutting
or welding, or
blasting flame.
Yes/NoOffline
Electric sparkPresence of
electric spark
sources such as
static electricity or
electrical failure.
Yes/NoOffline
## Spontaneous
heating
Presence of
spontaneous
heating sources
such as coal
spontaneous
combustion or
self-ignition of
macromolecular
materials.
Yes/NoOffline
## Friction
spark
Presence of
friction spark
sources such as
friction between
metal and rock.
Yes/NoOffline
## Methane
overrun
Exceedance of
methane
concentration in
the tailgate, which
may result from
gas leakage from
drainage pipes,
emissions from
goaf, and
discharge from the
coal seam.
## Serious/
## Negligible
## Online/
## Dependent
## Ventilation
conditions
Performance of
the ventilation
system.
## Poor/
## Acceptable
## Dependent
Wind speedSpeed of the
airflow within the
tailgate.
## Inadequate/
## Adequate
## Offline/
## Online
## Inflow
quality
## Methane
concentration in
the maingate.
## Poor/
## Acceptable
## Offline/
## Online
AccidentMethane
explosion
Risk of methane
explosion.
Yes/NoDependent
ConsequenceCasualtiesThe severity of the
methane
explosion’s
casualties.
## Severe/
Slight/None
## Dependent
## Economic
loss
The severity of the
methane
explosion’s
economic loss.
## Severe/
Slight/None
## Dependent
## Successive
explosions
The severity of the
methane
explosion’s
successive
explosions.
## Severe/
Slight/None
## Dependent
## Preventive
measures
## Preventive
measures
Control measures
for causes like
shearer slowdown,
power cut off, or
water barriers.
## Poor/
## Effective
## Offline
## Mitigative
measures
## Mitigative
measures
Control measures
for consequences
such as post-
drainage or
emergency
responses.
## Poor/
## Effective
## Offline
M. Mousavi et al.

Reliability Engineering and System Safety 256 (2025) 110760
## 8
manage and mitigate the impact of accidents and their outcomes. Safety
managers responsible for underground environments can adjust the BN
variables to simulate various scenarios and promptly observe how these
changes affect the dynamic risk progression charts.
- Case studies on underground coal mines
Coal mining generates methane as a by-product, with the gas being
trapped under pressure within coal seams and gradually released into
the mining site as coal extraction progresses [47]. Beyond its flamma-
bility, even at low concentrations, methane levels ranging from 5 % to
15 % are considered explosive [48]. Methane explosions have consis-
tently been a major hazard in underground coal mines worldwide [49].
Despite recent technological advancements, methane explosions remain
the leading cause of fatal accidents in the mining industry [50]. Addi-
tionally, these explosions damage mining machinery and equipment,
resulting in  significant economic and  productivity losses for  mining
companies. Methane explosions also make existing coal dust flammable,
leading to subsequent explosions [24]. To mitigate these hazards, mine
operators typically shut down all mining activities when methane con-
centrations exceed 1 % in designated areas. This precaution significantly
slows down mining activities and imposes substantial financial losses,
amounting to millions of dollars, on affected companies [50]. Given the
critical importance of  addressing methane explosions and the
complexity of such incidents, further research is crucial to improve the
prediction of methane explosions and implement effective preventive
and mitigative measures. To demonstrate the applicability of the pro-
posed framework, two  case studies were conducted to  predict the
real-time progression of methane explosion risk in underground coal
mines in Poland and China. The following sections provide a detailed
breakdown of the framework implementation for these proof-of-concept
cases.
4.1. BN instantiation for methane explosions
As a key part of the case study implementation, a BN was developed
to assess the risk of methane explosion incidents in underground coal
mines. Due to the lack of a reliable dataset on historical methane ex-
plosions, an extensive review of relevant literature was conducted to
Fig. 4.IoT-Bayes fusion system architecture.
## Table 4
An overview of the characteristics of the utilized sensors from the Polish mine.
Sensor TypeUnitCodeMinMaxMeanSD
Methane meter MM-
2PWk
## % CH
## 4
## MM2610300.0490.125
## MM262 0.2300.0510.136
## MM263 2300.2480.197
## MM264 2400.3270.206
## MM2560300.430.204
Anemometer [ 5, 5]m/sAN42202.41.6550.128
Fig. 5.Spatial distribution of the utilized sensors within the Polish coal mine area map.
M. Mousavi et al.

Reliability Engineering and System Safety 256 (2025) 110760
## 9
construct the preliminary network structure and determine the prior
probabilities for each root node. The conditional probabilities for in-
termediate nodes were then estimated based on reasonable assumptions
and established relationships documented in the literature. A detailed
literature-based BN is presented in the paper by Mousavi, et al. [51].
Table 1provides a summary of the most significant causes and conse-
quences of methane explosions in underground coal mines, derived from
a review of similar studies. The variables listed in Table 1were collected
from studies by He, et al. [3], Li, et al. [11], You, et al. [15], Muduli,
et al. [17], Tong, et al. [24], Mottahedi, et al. [52]. In selecting the
variables for Table 1, the focus was on those most likely to change over
time during operation. Consequently, factors such as the quality of the
ventilation system design or  the  type of  coal  seam being exploited,
which are likely to remain constant, were excluded from this study.
Three experts were consulted to verify the constructed structure and
validate the reliability of the BN outcomes. First, two experienced aca-
demics, renowned for their expertise in underground mine ventilation
systems, mine explosives, and  gas  management, were individually
approached to review the network’s structure and the causal relation-
ships between nodes. Their input helped refine the network’s structure,
ensuring that the identified causes and consequences were accurately
connected. Next, a  ventilation officer with substantial experience in
underground coal mines was invited to validate the final structure and
confirm the reliability of the risk assessment results. Drawing on years of
practical experience with ventilation systems, this expert provided a
valuable practical perspective and validation of the model.
The consultations were conducted in one- to two-hour sessions using
a semi-structured format. The interviews began with an overview of
existing methane concentration datasets and  an  introduction to  the
available sensors and their locations in the coal mine cases. The experts
were then asked to evaluate the overall structure of the preliminary
network, focusing on identifying any potential redundancies or missing
factors. They assessed the structure and conditional probabilities of each
section of the BN, providing detailed analysis and recommending im-
provements based on their expertise and experience. The research team
carefully considered the experts’ recommendations and incorporated
the necessary adjustments into the network to refine the model. The
insights and  feedback provided by  the  experts were compiled and
summarized in Table 2.
Fig. 3displays the updated BN, which includes eight distinct node
categories: methane overrun, ignition, ventilation, accident, conse-
quences, preventive measures, and mitigative measures. Each category
is visually differentiated by a distinct color scheme. Table 3provides a
comprehensive explanation of the variables present in the updated BN.
The BN was constructed using BayesFusion’s GeNIe Modeler [53].
The mode assigned to each variable is specified in the last column of
Table 3.  Variables are  categorized as  offline, online, or  dependent.
Offline variables serve as root nodes, where users directly input evi-
dence. These variables do not receive real-time data from IoT sensors.
For example, if ignition sources are detected at a specified location, users
must set  the  state to  "yes," and  the  model will  then adjust the  risk
assessment for all other nodes accordingly. Online variables, in contrast,
automatically receive real-time values without user intervention. These
nodes represent dynamic variables that change over time. Dependent
variables do  not  receive direct input from users or  real-time data;
instead, their values are computed based on evidence from root nodes
and  the  probabilistic relationships defined within the  BN.  Bayesian
inference is used to propagate probabilities throughout the network and
calculate the  posterior probabilities of  these dependent nodes. Both
inflow quality and wind speed can either receive real-time data or be
directly adjusted by users. Methane overrun is the only node in the
network that can function both as an online node and a dependent node,
depending on user preferences.
4.2. IoT-Bayes fusion
The next phase of the case implementation involved developing a
system to link IoT data streams with the constructed BN. Fig. 4illustrates
the architecture of the IoT-Bayes fusion system created for this purpose.
The system consists of two layers: data preparation and risk assessment.
In the data preparation layer, the dataset is retrieved and processed
according to  the  procedures outlined in Section 3.2,  ensuring it  is
properly formatted for input into the BN described in Section 4.1. To
integrate these layers seamlessly, the Python wrapper for the SMILE
Engine [54] was used. The SMILE library includes a set of C++classes
for managing the GeNIe Modeler through an Application Programming
Interface (API). The prepared data is then entered into the BN’s online
nodes as evidence within the risk assessment layer. Bayesian inference
procedures are  employed to  propagate risk  and generate insights as
specified by  the  user. These insights are  then fed  back to  the  data
## Table 5
Description of the prepared inputs for the developed BN for the Polish mine.
## Associated
BN Node
## Value
## Derivation
ThresholdMinMaxMeanSD
## Inflow
## Quality
## (%)
## Avg
## (MM261,
## MM262)
## Poor: >1
## Acceptable:
## <1
##  0.104.050.0500.075
## Wind Speed
## (m/s)
AN422Inadequate:
## <0.15
## Adequate: >
## 0.15
## 0.092.221.6550.114
## Methane
## Overrun
## (%)
## Avg
## (MM263,
## MM264,
## MM256)
## Serious: >2
## Negligible: <
## 2
## 02.290.3350.135
## Table 6
A summary of the developed scenarios for the Polish mine.
No.Input EvidenceTime Point/
## Interval
Rationale for Scenario Development
1Methane Overrun
[Online]
At each time
step
This serves as a baseline to assess the
system’s ability to monitor methane
overrun in real time under normal
operating conditions. The aim is to
provide a standard risk progression
with minimal intervention.
2Wind Speed
[Online]
At each time
step
Focuses on testing how well the
system can predict explosion risks
when ventilation parameters (wind
speed and inflow quality) change in
real time. Ventilation is a critical
aspect in maintaining safe methane
levels underground, making this
scenario relevant for assessing
environmental changes.
## Inflow Quality
[Online]
At each time
step
3Methane Overrun
[Online]
At each time
step
Introduces a period of preventive
failure, simulating real-life situations
where preventive measures might be
insufficient or poorly implemented.
This scenario is designed to assess
how the system manages multiple
risk factors and sudden spikes in
danger, especially when combined
with ignition sources (open fire).
## Preventive
Measures =Poor
Time step <
## 0.7E+5
Open Fire =Yes0.3E+5 <
Time step <
## 0.9E+5
## Preventive
## Measures =
## Effective
Time step >
## 0.7E+5
4Methane Overrun
[Online]
At each time
step
A scenario designed to showcase the
system’s capability in managing
mitigative measures post-failure.
Here, the focus shifts to how
mitigative efforts (like firefighting or
ventilation adjustments) can reduce
the severity of consequences, even
when preventive measures fail.
## Preventive
Measures =Poor
At each time
step
Open Fire =Yes0.3E+5 <
Time step <
## 0.9E+5
## Mitigative
Measures =Poor
Time step <
## 0.7E+5
## Mitigative
## Measures =
## Effective
Time step >
## 0.7E+5
M. Mousavi et al.

Reliability Engineering and System Safety 256 (2025) 110760
## 10
preparation layer for  visualization and presentation, aiding in
decision-making.
4.3. Case study on open-access data from a coal mine in Poland
This case study simulated real-time IoT data streams using an open-
source dataset from an underground coal mine in the Upper Silesian
Coal Basin in Poland. The dataset is publicly accessible in the Mendeley
data repository, as referenced by Sikora and Wr
## ́
obel [55]. It includes
data from 28  sensors strategically placed throughout the  mine from
March 2, 2014, to June 16, 2014. The dataset covers environmental data
from the mine and the operational status of a longwall shear, comprising
a  total of  9199,930 time-sensitive readings taken at  one-second in-
tervals, complete with timestamps and  measurements. Notably, the
dataset contains no missing values, ensuring its completeness and reli-
ability. A detailed overview of the sensor types used in the dataset can be
found in Kozielski, et al. [56]. Table 4lists the sensors used in this case
study, while Fig. 5shows their spatial distribution within the coal mine.
The data collected from environmental sensors was gathered using
the SMP-NT safety system, designed for monitoring conditions in un-
derground environments with risks of methane and coal dust explosions.
The SMP-NT system facilitated near-continuous communication with
underground sensors. This data was then transmitted to a central dis-
patching system called THOR, which served as a hub for storing and
visualizing the environmental data in real-time. The THOR dispatching
system was used in the control room to ensure continuous monitoring of
underground conditions [56].
The  dataset had  no  missing values. Initial measurements were
recorded at one-second intervals. However, these intervals were deemed
impractical for the study, as significant changes within each second were
not expected. Additionally, short intervals could exacerbate the impact
of outliers, potentially resulting in false alarms. Therefore, the authors
decided to  extend the  time steps to  60  s  (1  min). This adjustment
involved averaging the measurements collected within each 60-second
Fig. 6.Methane explosion risk progression in Scenarios 1 and 2 for the Polish mine.
Fig. 7.Methane explosion risk progression in Scenario 3 for the Polish mine.
M. Mousavi et al.

Reliability Engineering and System Safety 256 (2025) 110760
## 11
interval to represent each time step. This approach aimed to reduce the
influence of outliers while giving mine safety managers and personnel a
sufficient timeframe to implement necessary preventive measures. As a
result, the dataset was reduced to 153,333 data samples for each sensor
used in the study.
A strategy was implemented to address erroneous sensor measure-
ments. Instead of relying solely on individual sensor values, the average
measurements from closely situated sensors were aggregated and used
as inputs for their respective nodes in the developed BN. Specifically, the
mean values from three sensors—MM263, MM264, and MM256—lo-
cated near the junction of the  mine face and tailgate, were used to
trigger the  methane overrun node. This location is  crucial for  gas
monitoring due to high-intensity activities such as digging, blasting, coal
dropping, and transportation [57]. Similarly, the average readings from
MM261 and MM262 were used to activate the inflow quality node, as
these methane meters were positioned close to each other in the main-
gate. The readings from AN422 were directly used to provide evidence
for  the  wind speed node, as  it  was  the  only sensor in  the  tailgate
measuring air velocity.
The next step in data preparation involved translating the numerical
sensor measurements into states that the BN could interpret. Each input
was thresholded based on predefined criteria to achieve this. Acceptable
methane levels in underground coal mines can vary worldwide due to
differing regulations in various countries. Additionally, different sec-
tions of a mine may have varying maximum threshold limits even within
a  single location. For  this  case study, the  coal  mine was  located in
Poland. Therefore, the  regulatory standards of  Poland were used to
determine the permissible maximum methane concentrations. Specif-
ically, methane concentrations exceeding 2 % and 1 % were classified as
serious or poor for the air exiting and entering the mine face, respec-
tively, as stated by Tutak, et al. [58]. For wind speed, any recorded
measurements below 0.15 m/s were considered inadequate, while those
exceeding this threshold were deemed adequate [3]. Table 5describes
the three distinct inputs prepared for integration into the developed BN.
To demonstrate the practicality of the  proposed framework, four
hypothetical scenarios were created to represent various situations that
could potentially arise during the operation of an underground coal
mine. These scenarios were designed to  showcase the  framework’s
specific capabilities. Table 6summarizes the details of these scenarios,
the input evidence provided to the model at designated times, and the
reasoning behind their selection.
In Scenario 1, the variables within the developed BN were kept in
their initial states. Meanwhile, the methane overrun node received real-
time input from the simulated IoT data stream at each time step. As a
Fig. 8.Impact of mitigative measures on explosion consequences in Scenario 4 for the Polish mine.
Fig. 9.Cleaned sensor data trend in the Chinese dataset.
M. Mousavi et al.

Reliability Engineering and System Safety 256 (2025) 110760
## 12
result, the value of the methane overrun node at each time step could be
classified as either negligible or serious based on predefined thresholds
described in Section 4.1. After incorporating the real-time data into the
network, the  probabilities of  all  other variables were updated itera-
tively. Fig. 6visually presents the progression of methane explosion risk
over the data collection period. Notably, distinct spikes in explosion
probability appear at regular intervals, which may be due to periodic
sensor performance tests or  specific activities causing immediate
methane releases in the roadways. However, the peak predicted explo-
sion risk during these spikes only marginally exceeded 0.5. This result
can be attributed to the assumption in this scenario that all network
variables remained in their prior states (e.g., preventive measures were
assumed to be 80 % effective at all times), with no observable evidence
suggesting any changes.
Fig. 6also shows the outcomes of Scenario 2. In this scenario, it was
assumed that real-time data for methane overrun was unavailable, but
the inflow quality and wind speed nodes received online evidence from
IoT  sensors. In  the  developed BN,  the  methane overrun node was
influenced by  ventilation conditions, which depended on  the  inflow
quality and wind speed (see Fig. 3). Consequently, it was expected that
assuming all other nodes remained in their initial states, the outcomes of
Scenario 2 would resemble those of Scenario 1. Fig. 6confirms this
expectation, with nearly consistent spikes in predicted explosion risk
observed in both scenarios. In most cases, the spike appeared earlier in
Scenario 2, possibly due to the spatial distance between the sensors
triggering the first scenario and those used in the second scenario.
In Scenario 3, real-time evidence continuously informed the methane
overrun node at each time step. It was assumed that some evidence
existed before time step 0.7E+5, indicating a potential failure in the coal
miner’s efforts to prevent methane accumulation or eliminate ignition
sources. However, it later became clear that effective preventive mea-
sures were implemented after this time step. Additionally, a welding
activity was assumed to have occurred between time steps 0.3E+5 and
0.9E+5 near the end of the coal face. Due to the high risk associated with
this activity, users designated the open fire status as “yes” within this
time interval. Fig. 7visually represents the explosion risk progression in
Scenario 3.  As  shown, the  time steps before 0.7E+5  exhibited an
increased explosion risk of 0.13 due to the lack of effective preventive
measures, compared to Scenario 1
′s risk of only 0.04. While this risk
level isn’t  concerning without an  apparent ignition source, the
Fig. 10.Predicted risk of explosion based on methane concentration in Chinese mine data.
Fig. 11.Predicted risk of explosion Chinese mine data for Scenarios 1 and 2.
M. Mousavi et al.

Reliability Engineering and System Safety 256 (2025) 110760
## 13
introduction of an open fire source raised the risk to a probability of
0.23. The most critical point occurred at time step 46,563, marked by
the simultaneous presence of an open fire ignition source, a brief spike in
methane concentration, and ineffective preventive measures. This situ-
ation resulted in a high explosion risk probability of 0.95. After time step
0.7E+5, when effective preventive measures were in place, the explo-
sion risk dropped to 0.5, even with an ignition source and a sudden
release of methane. This scenario highlights the proposed framework’s
ability to account for the cascading effects of influencing factors, thereby
capturing the dynamic nature of environmental risks in underground
environments.
Scenario 4 was designed to demonstrate the prediction of explosion-
related consequences and the effectiveness of mitigative measures in
managing them. The configuration of Scenario 4 closely resembles that
of Scenario 3. In this case, preventive measures were assumed to be
ineffective at each time step, and mitigative measures were improved
from poor to effective at time step 0.7E+5. The outcomes are shown in
Fig. 8. As observed, an increase in explosion risk was associated with a
rise  in  consequences. This correlation was  expected, given that  the
methane explosion node influences all consequences in the network.
Another observation in Fig. 8occurs at  time step 0.7E+5 when the
mitigative measures became effective. At this point, the risk associated
with all consequences decreased, while the risk of the explosion itself
remained constant. This difference arises from the distinction between
preventive measures, which address the causes of the explosion, and
mitigative measures, which focus on minimizing the severity of conse-
quences, in the developed BN.
4.4. Case study on real data from an underground mine in China
The second case study was conducted at an underground coal mine in
China. Although this was a longwall mine, the dataset provided to the
research team was collected during the excavation of access tunnels
using a roadheader. The dataset recorded methane gas concentration
from a  sensor near the  excavation site, covering the  period from
December 19, 2021, to May 12, 2023, for a total of 509 days. The sensor
reported the maximum, minimum, and average methane concentration
every minute, resulting in a total of 732,451 data points.
Since this data was collected under real-world conditions, it included
some missing values. These values, recorded as NaN in the dataset, were
identified and replaced with the last available data. Additionally, the
sensor had been regularly tested with controlled amounts of methane
gas at set intervals, hence these periodic tests resulted in some methane
concentration values being recorded that  did  not  reflect the  actual
environmental conditions of the mine. These values were removed from
the dataset with the help of mine managers by matching them with the
test dates and were replaced with the last meaningful available value.
Fig. 9shows the trend of the sensor data after cleaning. The data ranges
from 0 to 7.26 %, with an average of 0.17 %.
The maximum methane concentration recorded each minute was
used as input evidence for the methane overrun node in the BN shown in
Fig. 3, while the other nodes remained in their prior states. Mine experts
set a concentration threshold of 1 % for this node. Therefore, concen-
trations above 1 % were labeled as serious, and those below 1 % were
labeled as negligible. After feeding the BN with these labels, Fig. 10
shows the predicted risk of explosion in the examined mine. The risk of
explosion was predicted to be very minimal throughout most of the data
collection period, which aligns with the actual mine conditions. Only
once, on February 3, 2023, at 3:23am, did the risk suddenly spike to
0.51. This spike was due to a sharp and sudden increase in methane
concentration in the mine, which rose to 7.26 %. The high concentration
was attributed to a sudden release of a large volume of methane from the
upper coal seam after mining, combined with initially high methane
levels and the occurrence of soft stratification.
To examine the conditions that might have occurred following this
incident, two additional scenarios were analyzed. In the first scenario, it
was assumed that an open fire source was located near the sensor for one
week before and after the incident and that preventive measures were
not effectively in place during that time. In the second scenario, it was
assumed that while an open fire source was present during the same
period, effective preventive measures were in  place to  control gas
accumulation. Figs. 11aand 11bshow the model’s predicted results for
explosion risk for Scenario 1 and Scenario 2, respectively.
According to Fig. 11a, in the absence of effective preventive mea-
sures and with a negligible methane concentration, a single open fire
source increased the explosion risk to 0.23. When a high methane con-
centration of 7.26 % was introduced into the mine, the explosion risk
peaked at 0.951. This high probability suggests that the lack of effective
preventive measures allows gas accumulation to reach dangerous levels,
which, combined with the presence of an open fire source, leads to a
significant explosion risk. The sharp spike also indicates that the ex-
plosion risk is time-sensitive and could potentially occur within a short
time frame, highlighting the need for timely and effective preventive
actions to mitigate such risks. Fig. 11bshows a much lower probability
of explosion, with the peak reaching a significantly lower level of 0.481.
This reduced peak probability indicates that effective preventive mea-
sures successfully mitigate the  risk of  gas  accumulation, thereby
lowering the explosion risk. It underscores the importance of having
robust safety protocols and measures in place to control potential haz-
ards and prevent catastrophic events such as explosions.
4.5. Results and discussion
The implementation of the proposed IoT-Bayes fusion system in the
selected case studies provided significant insights into the risk assess-
ment and  management of  methane explosions in  underground coal
mines. The findings from the two case studies highlight the system’s
effectiveness in dynamic risk prediction and its potential implications
for real-time risk management.
In the first case study, the BN model was applied to an open-source
dataset from a Polish coal mine, where real-time sensor measurements
were integrated into the BN through the IoT-Bayes fusion system. The
results showed that the BN effectively processed the dynamic inputs,
allowing it to update the risk levels of a potential methane explosion as
new data became available. For example, when an increase in methane
concentration was detected by the sensors, the BN model responded by
immediately raising the predicted risk of an explosion, enabling timely
preventive actions. This case study also underscored the critical role of
ventilation conditions in controlling methane levels, as poor ventilation
consistently correlated with higher methane concentrations. The
model’s ability to predict risk dynamically, adjusting to real-time data,
was validated by its close alignment with historical incident reports.
This capability is particularly valuable in the context of underground
coal mining, where conditions can change rapidly and unpredictably.
The second case study focused on a proprietary dataset from a Chi-
nese coal mine, which included instances of serious methane concen-
trations. The dataset allowed for a more in-depth examination of the
BN’s predictive accuracy and robustness under different scenarios. In a
real-time risk assessment scenario, the BN provided accurate risk levels
corresponding to  the  observed methane concentrations, effectively
predicting the potential for an explosion. When a scenario was simulated
where an open fire occurred alongside high methane concentrations, the
BN’s risk assessment reflected a significant increase in the explosion risk,
demonstrating the model’s sensitivity to cascading hazard scenarios.
Furthermore, when effective preventive measures, such as  improved
ventilation and the elimination of ignition sources, were assumed, the
BN indicated a substantial reduction in the risk of an explosion. This
finding illustrates the model’s utility in evaluating the potential impact
of various safety interventions.
The comparative analysis of these two case studies reveals several
innovative implications for the practical application of the IoT-Bayes
fusion system in underground operations. Integrating IoT data streams
M. Mousavi et al.

Reliability Engineering and System Safety 256 (2025) 110760
## 14
into the BN enables real-time data analytics to monitor and manage
cascading risks as  they occur. The  system’s  ability to  capture and
analyze data in real-time allows for immediate identification and eval-
uation of  potential hazards, leading to  timely decision-making and
proactive risk mitigation. In this way, instead of merely monitoring raw
data, underground managers can track analyzed risks in real time. By
performing what-if analyses, the system provides a robust platform for
simulating different risk conditions and their impacts, enhancing the
ability to foresee and respond to emerging threats in real time. This real-
time feedback loop also allows for immediate adjustments to risk man-
agement strategies based on new data and evolving conditions. Addi-
tionally, the  BN  framework captures tacit knowledge by  modeling
complex interdependencies and risk factors, translating expert insights
into actionable data.
## 5. Conclusions
This paper introduces a real-time framework for evaluating safety
risks in underground settings. The framework leverages IoT sensors to
generate real-time environmental data and uses BNs as a reliable risk
assessment tool. To validate the effectiveness of the proposed frame-
work, two case studies were conducted using two datasets focusing on
methane levels in coal mines in Poland and China. The findings highlight
the potential of the framework to assist safety managers in continuously
monitoring safety hazards in  underground environments, enabling
prompt interventions when needed.
The proposed framework offers two significant benefits for
enhancing safety in underground settings. First, the creation of a BN
facilitates the encapsulation and preservation of tacit knowledge from
safety experts in the underground environment. This type of knowledge
is often difficult to communicate but capturing it in BN models can
preserve it  as  a  valuable organizational asset. Second, the  semi-
automatic fusion of IoT data with the BN establishes a real-time risk
assessment and monitoring platform. This enables underground opera-
tors and safety managers to observe how complex and dynamic factors
interact and affect risks in real-time. The platform also allows managers
to  adjust variables and  see  immediate changes, which is  useful for
evaluating various risks and making safety decisions. Through this sys-
tem, ongoing evaluation and improvement of safety measures become
feasible, along with the early identification and mitigation of potential
risks before they escalate into more severe incidents.
During the development of the BN, challenges in implementation led
to consolidating various preventive and mitigative measures into single
nodes. This simplification does not account for potential variations in
the effects of different measures. Future research could address this by
incorporating the diverse impacts of individual measures into the model.
Another area of interest for further research might involve integrating
this system with visualization technologies. This could lead to the cre-
ation of an environmental digital twin for underground construction and
mining environments, enhancing the monitoring and management of
environmental safety.
CRediT authorship contribution statement
Milad Mousavi: Writing – review & editing, Writing – original draft,
Visualization, Methodology, Investigation, Formal analysis, Data cura-
tion, Conceptualization, Software, Validation. Xuesong Shen: Writing –
review & editing, Supervision, Funding acquisition. Zhigang Zhang:
Data curation. Khalegh Barati: Supervision. Binghao Li: Writing – re-
view & editing, Supervision, Funding acquisition.
Declaration of competing interest
The authors declare that they have no known competing financial
interests or personal relationships that could have appeared to influence
the work reported in this paper.
## Acknowledgments
This research is supported by funding from the Australian Research
Council (ARC) Research Hub for Resilient and Intelligent Infrastructure
Systems (IH210100048). The authors would like to thank Mr. Duncan
Chalmers and A/Prof. Guangyao Si at the School of Minerals and Energy
Resources at the University of New South Wales (UNSW Sydney), and
Mr.  Flynn Malnic, Ventilation Officer at  Anglo American, for  their
invaluable contributions to this research. Their guidance, insights, and
assistance were crucial in enhancing the quality of this study. We also
extend our gratitude to BayesFusion, LLC for providing us with free
access to GeNIe Modeler and SMILE Engine software, which greatly
aided our research.
Data availability
The authors do not have permission to share data.
## References
[1]Jang H, Topal E. Transformation of the Australian mining industry and future
prospects. Mining Technol 2020;129(3):120–34. https://doi.org/10.1080/
## 25726668.2020.1786298.
[2]Dong L, Tong X, Li X, Zhou J, Wang S, Liu B. Some developments and new insights
of environmental problems and deep mining strategy for cleaner production in
mines. J Clean Prod 2019;210:1562–78. https://doi.org/10.1016/j.
jclepro.2018.10.291.
[3]He S, Lu Y, Li M. Probabilistic risk analysis for coal mine gas overrun based on
FAHP and BN: a case study. Environ Sci Pollut Res 2022;29(19):28458–68. https://
doi.org/10.1007/s11356-021-18474-3.
[4]Wu Y, Chen M, Wang K, Fu G. A dynamic information platform for underground
coal mine safety based on internet of things. Saf Sci 2019;113:9–18. https://doi.
org/10.1016/j.ssci.2018.11.003.
[5]Qiao W. Analysis and measurement of multifactor risk in underground coal mine
accidents based on coupling theory. Reliab Eng Syst Saf 2021;208:107433. https://
doi.org/10.1016/j.ress.2021.107433.
[6]Liang Y, Liu Q. Early warning and real-time control of construction safety risk of
underground engineering based on building information modeling and internet of
things. Neural Comput Appl 2022;34(5):3433–42. https://doi.org/10.1007/
s00521-021-05755-8.
[7]Tariq S, Loy-Benitez J, Nam K, Kim S, Kim M, Yoo C. Deep-AI soft sensor for
sustainable health risk monitoring and control of fine particulate matter at sensor
devoid underground spaces: a zero-shot transfer learning approach. Tunnel
Underground Space Technol 2023;131:104843. https://doi.org/10.1016/j.
tust.2022.104843.
[8]Xue G, Liu S, Ren L, Gong D. Risk assessment of utility tunnels through risk
interaction-based deep learning. Reliab Eng Syst Saf 2024;241:109626. https://
doi.org/10.1016/j.ress.2023.109626.
## [9]
## ́
Slęzak D, Grzegorowski M, Janusz A, Kozielski M, Nguyen SH, Sikora M, et al.
A framework for learning and embedding multi-sensor forecasting models into a
decision support system: a case study of methane concentration in coal mines. Inf
Sci 2018;451-452:112–33. https://doi.org/10.1016/j.ins.2018.04.026.
[10]Janusz A, Grzegorowski M, Michalak M, Wr
## ́
obel Ł, Sikora M,
## ́
## Slęzak D. Predicting
seismic events in coal mines based on underground sensor measurements. Eng Appl
Artif Intell 2017;64:83–94. https://doi.org/10.1016/j.engappai.2017.06.002.
[11]Li M, Wang H, Wang D, Shao Z, He S. Risk assessment of gas explosion in coal
mines based on fuzzy AHP and bayesian network. Process Saf Environ Protect
2020;135:207–18. https://doi.org/10.1016/j.psep.2020.01.003.
[12]Janusz A, Sikora M, Wr
## ́
obel Ł, Stawicki S, Grzegorowski M, Wojtas P, et al. Mining
data from coal mines: IJCRS’15 data challenge. Rough sets, fuzzy sets, data mining,
and granular computing 2015:429–38. https://doi.org/10.1007/978-3-319-
25783-9_38. Cham, Y. Yao, Q. Hu, H. Yu, and J. W. Grzymala-Busse2015//.
[13]Huang MQ, Nini
## ́
c J, Zhang QB. BIM, machine learning and computer vision
techniques in underground construction: current status and future perspectives.
Tunnel Underground Space Technol 2021;108:103677. https://doi.org/10.1016/j.
tust.2020.103677.
[14]Moradi R, Cofre-Martel S, Lopez Droguett E, Modarres M, Groth KM. Integration of
deep learning and Bayesian networks for condition and operation risk monitoring
of complex engineering systems. Reliab Eng Syst Saf 2022;222:108433. https://
doi.org/10.1016/j.ress.2022.108433.
[15]You M, Li S, Li D, Xu S. Applications of artificial intelligence for coal mine gas risk
assessment. Saf Sci 2021;143:105420. https://doi.org/10.1016/j.
ssci.2021.105420.
[16]M. Li, H. Yu, and P. Liu, "An automated safety risk recognition mechanism for
underground construction at the pre-construction stage based on BIM," Autom
Constr, vol. 91, pp. 284–92, 2018, doi: https://doi.org/10.1016/j.autcon.2018.0
## 3.013.
[17]Muduli L, Mishra DP, Jana PK. Application of wireless sensor network for
environmental monitoring in underground coal mines: a systematic review.
M. Mousavi et al.

Reliability Engineering and System Safety 256 (2025) 110760
## 15
J Network Comput Appl 2018;106:48–67. https://doi.org/10.1016/j.
jnca.2017.12.022.
[18]Tubis A, Werbi
## ́
nska-Wojciechowska S, Wroblewski A. Risk assessment methods in
mining industry—a systematic review. Appl Sci 2020;10(15). https://doi.org/
## 10.3390/app10155172.
[19]Zhang P, Zhang Z-J, Gong D-Q. An improved failure mode and effect analysis
method for group decision-making in utility tunnels construction project risk
evaluation. Reliab Eng Syst Saf 2024;244:109943. https://doi.org/10.1016/j.
ress.2024.109943.
[20]Bai Y, Wu J, Liu K, Sun Y, Shen S, Cao J, et al. Energy-based coupling risk
assessment (CRA) model for urban underground utility tunnels. Reliab Eng Syst Saf
2024;250:110255. https://doi.org/10.1016/j.ress.2024.110255.
[21]Hai N, Gong D, Liu S, Dai Z. Dynamic coupling risk assessment model of utility
tunnels based on multimethod fusion. Reliab Eng Syst Saf 2022;228:108773.
https://doi.org/10.1016/j.ress.2022.108773.
[22]Li N, Feng X, Jimenez R. Predicting rock burst hazard with incomplete data using
Bayesian networks. Tunnel Underground Space Technol 2017;61:61–70. https://
doi.org/10.1016/j.tust.2016.09.010.
[23]Wu J, Bai Y, Fang W, Zhou R, Reniers G, Khakzad N. An integrated quantitative risk
assessment method for urban underground utility tunnels. Reliab Eng Syst Saf
2021;213:107792. https://doi.org/10.1016/j.ress.2021.107792.
[24]Tong X, Fang W, Yuan S, Ma J, Bai Y. Application of Bayesian approach to the
assessment of mine gas explosion. J Loss Prev Process Ind 2018;54:238–45.
https://doi.org/10.1016/j.jlp.2018.04.003.
[25]Wu X, Liu H, Zhang L, Skibniewski MJ, Deng Q, Teng J. A dynamic Bayesian
network based approach to safety decision support in tunnel construction. Reliab
Eng Syst Saf 2015;134:157–68. https://doi.org/10.1016/j.ress.2014.10.021.
[26]Marcot BG, Penman TD. Advances in Bayesian network modelling: integration of
modelling technologies. Environ Model Softw 2019;111:386–93. https://doi.org/
## 10.1016/j.envsoft.2018.09.016.
[27]Zhou C, Ding LY. Safety barrier warning system for underground construction sites
using Internet-of-Things technologies. Autom Constr 2017;83:372–89. https://doi.
org/10.1016/j.autcon.2017.07.005.
[28]Zhang P, Chen R-P, Dai T, Wang Z-T, Wu K. An AIoT-based system for real-time
monitoring of tunnel construction. Tunnel Underground Space Technol 2021;109:
- https://doi.org/10.1016/j.tust.2020.103766.
[29]Ye Z, Ye Y, Zhang C, Zhang Z, Li W, Wang X, et al. A digital twin approach for
tunnel construction safety early warning and management. Comput Ind 2023;144:
- https://doi.org/10.1016/j.compind.2022.103783.
[30]Liu Q, He R, Zhang L. Simulation-based multi-objective optimization for enhanced
safety of fire emergency response in metro stations. Reliab Eng Syst Saf 2022;228:
- https://doi.org/10.1016/j.ress.2022.108820.
[31]Zhou J, Zhang Y, Li C, He H, Li X. Rockburst prediction and prevention in
underground space excavation. Underground Space 2024;14:70–98. https://doi.
org/10.1016/j.undsp.2023.05.009.
[32]Zhang H, Li B, Karimi M, Saydam S, Hassan M. Recent advancements in IoT
implementation for environmental, safety, and production monitoring in
underground mines. IEEE Internet Things J 2023:1. https://doi.org/10.1109/
## JIOT.2023.3267828.
[33]Wang N, Xiao Y, Tian T, Yang J. The optimal 5G base station location of the
wireless sensor network considering timely reliability. Reliab Eng Syst Saf 2023;
236:109310. https://doi.org/10.1016/j.ress.2023.109310.
[34]Feng JR, Zhao M-k, Lu S-x. Accident spread and risk propagation mechanism in
complex industrial system network. Reliab Eng Syst Saf 2024;244:109940. https://
doi.org/10.1016/j.ress.2024.109940.
[35]Global Mining Guidelines Group. Underground Mine Communications
Infrastructure Guidelines Part III: general Guidelines. Underground mine
communications infrastructure guideline suite. Global Mining Guidelines Group
## (GMG); 2019.
[36]Li B, Saydam S. Communication, Monitoring, and Control. SME underground
mining handbook. Society for Mining, Metallurgy & Exploration (SME); 2023.
p. 635–64. P. Darling Ed.ch. 27.
[37]Yang J, Yue Z, Yuan Y. Deep probabilistic graphical modeling for robust
multivariate time series anomaly detection with missing data. Reliab Eng Syst Saf
2023;238:109410. https://doi.org/10.1016/j.ress.2023.109410.
[38]Jia-Qi L, Yun-Wen F, Da T, Jun-Yu C, Cheng L. Operational reliability evaluation
and analysis framework of civil aircraft complex system based on intelligent
extremum machine learning model. Reliab Eng Syst Saf 2023;235:109218. https://
doi.org/10.1016/j.ress.2023.109218.
[39]Lyu P, Chen N, Mao S, Li M. LSTM based encoder-decoder for short-term
predictions of gas concentration using multi-sensor fusion. Process Saf Environ
Protect 2020;137:93–105. https://doi.org/10.1016/j.psep.2020.02.021.
[40]Byun J-E, Song J. A general framework of Bayesian network for system reliability
analysis using junction tree. Reliab Eng Syst Saf 2021;216:107952. https://doi.
org/10.1016/j.ress.2021.107952.
[41]Kammouh O, Gardoni P, Cimellaro GP. Probabilistic framework to evaluate the
resilience of engineering systems using Bayesian and dynamic Bayesian networks.
Reliab Eng Syst Saf 2020;198:106813. https://doi.org/10.1016/j.
ress.2020.106813.
[42]Iamsumang C, Mosleh A, Modarres M. Monitoring and learning algorithms for
dynamic hybrid Bayesian network in on-line system health management
applications. Reliab Eng Syst Saf 2018;178:118–29. https://doi.org/10.1016/j.
ress.2018.05.016.
[43]TohidiFar A, Mousavi M, Alvanchi A. A hybrid BIM and BN-based model to
improve the resiliency of hospitals’ utility systems in disasters. Int J Dis Risk
Reduct 2021;57:102176. https://doi.org/10.1016/j.ijdrr.2021.102176.
[44]Zhang X, Mahadevan S. Bayesian network modeling of accident investigation
reports for aviation safety assessment. Reliab Eng Syst Saf 2021;209:107371.
https://doi.org/10.1016/j.ress.2020.107371.
[45]Ademujimi T, Prabhu V. Digital twin for training bayesian networks for fault
diagnostics of manufacturing systems. Sensors 2022;22(4). https://doi.org/
## 10.3390/s22041430.
[46]Adedipe T, Shafiee M, Zio E. Bayesian network modelling for the wind energy
industry: an overview. Reliab Eng Syst Saf 2020;202:107053. https://doi.org/
## 10.1016/j.ress.2020.107053.
[47]Meng X, Chang H, Wang X. Methane concentration prediction method based on
deep learning and classical time series analysis. Energies 2022;15(6). https://doi.
org/10.3390/en15062262.
[48]Brodny J, Felka D, Tutak M. The use of the neuro-fuzzy model to predict the
methane hazard during the underground coal mining production process. J Clean
Prod 2022;368:133258. https://doi.org/10.1016/j.jclepro.2022.133258.
[49]Meng X, Liu Q, Luo X, Zhou X. Risk assessment of the unsafe behaviours of humans
in fatal gas explosion accidents in China’s underground coal mines. J Clean Prod
2019;210:970–6. https://doi.org/10.1016/j.jclepro.2018.11.067.
[50]Rahimi S, Ataee-pour M, Madani H, Aminossadati SM. Investigating the impact of
gas emission uncertainty on airflow distribution in an auxiliary ventilation system
using CFD and Monte-Carlo simulation. Build Environ 2021;204:108165. https://
doi.org/10.1016/j.buildenv.2021.108165.
[51]Mousavi M, Shen X, Li B. Online safety risk management for underground mining
and construction based on IoT and Bayesian networks. In: presented at the
Proceedings of the 40th International Symposium on Automation and Robotics in
Construction; 2023. https://doi.org/10.22260/ISARC2023/0067. 2023/07/07.
[52]Mottahedi A, Sereshki F, Ataei M, Qarahasanlou AN, Barabadi A. Resilience
estimation of critical infrastructure systems: application of expert judgment. Reliab
Eng Syst Saf 2021;215:107849. https://doi.org/10.1016/j.ress.2021.107849.
[53]BayesFusion. "GeNIe Modeler: complete Modeling Freedom." https://www.bayes
fusion.com/genie/; 2024 (accessed 20 July 2022).
[54]BayesFusion. "SMILE: structural Modeling, Inference, and Learning Engine." https
## ://www.bayesfusion.com/smile/; 2024 (accessed 20 July 2022).
[55]M. Sikora and Ł. Wr
## ́
obel. Methane, Mendeley Data, V1, 2021, doi: 10.17632/yd7
vw4c5mk.1.
[56]Kozielski M, Sikora M, Wr
## ́
obel Ł. Data on methane concentration collected by
underground coal mine sensors. Data Brief 2021;39:107457. https://doi.org/
## 10.1016/j.dib.2021.107457.
[57]Chang H, Meng X, Wang X, Hu Z. Research on coal mine longwall face gas state
analysis and safety warning strategy based on multi-sensor forecasting models. Sci
Rep 2024;14(1):13795. https://doi.org/10.1038/s41598-024-64181-7.
[58]M. Tutak, J. Brodny, D. Szurgacz, L. Sobik, and S. Zhironkin, "The Impact of the
Ventilation System on the Methane Release Hazard and Spontaneous Combustion
of Coal in the Area of Exploitation—A Case Study," Energies, vol. 13, no. 18,https
## ://doi.org/10.3390/en13184891.
M. Mousavi et al.