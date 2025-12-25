

## Vol.:(0123456789)
## 1 3
Archives of Computational Methods in Engineering (2024) 31:371–388
https://doi.org/10.1007/s11831-023-09982-1
## REVIEW ARTICLE
Review on Machine Learning‑Based Underground Coal Mines Gas
Hazard Identification and Estimation Techniques
## Mayank Sharma
## 1
## · Tanmoy Maity
## 1

Received: 23 March 2023 / Accepted: 15 July 2023 / Published online: 29 July 2023
© The Author(s) under exclusive licence to International Center for Numerical Methods in Engineering (CIMNE) 2023
## Abstract
The underground coal mines (UCM) exhibit many life-threatening hazards for mining workers. In contrast, gas hazards are
among the most critical challenges to handle. This study presents a comparative study of the sensor fusion methodologies
related to UCM gas hazard prediction and classification. The study provides a brief theoretical background of the exist-
ing methodologies and their usage to mitigate the gas hazard issues in UCM. A brief comparison report emphasising the
advantages and disadvantages of the existing models related to the UCM gas hazard monitoring is presented. Additionally,
a separate comparison is also drawn, considering only neural network models based on their prediction accuracy and other
performance metrics. This study attempts to observe and compare the Neural network models with the conventional method
in the field of UCM gas hazard prediction, which is not explored in this fraternity.
## 1  Introduction
The underground coal mines (UCM) environment is entirely
different from other industries. It imposes many life-threat-
ening hazards on the mining workers. A reliable, real-time
hazard monitoring system is required to ensure occupational
safety. Based on the mining process, coal mines are clas-
sified into two categories, i.e., open cast and underground
mines [95]. Underground mines are considered the most
challenging and hazardous work environment. A brief clas-
sification of the UCM hazards as per literature [71] is men-
tioned as follows.
-     Rock burst hazard—A sudden violent destruction of rock
mass due to the instantaneous release of elastic defor-
mation energy [72]. These kinds of hazards are often
followed by coal or rock mass ejection and airwaves that
may be destructive.
-     Mine fire—These hazards are mainly associated with
the continuous coal combustion phenomena. It mainly
occurred due to the oxidation of residual coal in the goaf
area [53]. These hazards are often followed by fire-damp
explosions and coal dust explosions, resulting in disas-
ters responsible for fatal accidents.
-     Dust hazards—Mining of the coal body is responsible
for dust formation, and this dust transmits across all the
mining galleries through the mine ventilation system,
thus resulting in mine atmosphere contamination [12].
-      Coal and gas explosion hazards—Parameters responsible
for explosion hazards in UCM are fuel, oxygen, ignition
source and confinement. The fuel can be the optimum
level of combustible gases and coal dust. For the UCM
case, 5 to 15% methane concentration in the air is con-
sidered a flammable mixture [74]. The ignition source
can be a spark from electrical or mechanical equipment
or operations, continuous combustions, and many oth-
ers.
-     Water hazard—These hazards arise due to hydrogeologi-
cal conditions. The mining process in difficult conditions
of aquifers may lead to increased water hazards [53].
Floods are common examples of these types of hazards.
Various other hazards in the UCM originate due to the chal-
lenging UCM environment, but the above-mentioned haz-
ard classes are among the most common. Based on fatality
frequency of occurrence, gas-related hazards are considered
Mayank Sharma and Tanmoy Maity have contributed equally to this
work.
## * Tanmoy Maity
tanmoy@iitism.ac.in
## Mayank Sharma
## MAYANK.17DR000449@MME.ISM.AC.IN
## 1
Department of Electrical Engineering, Indian Institute
of Technology (ISM), Dhanbad, Jharkhnad 826004, India

## 372 M. Sharma, T. Maity
## 1 3
the most significant, as historical evidence shows relatively
larger fatalities in this hazard class. Table 1 shows the evi-
dence of fatalities reported by various literature in UCM
cases. From Table 1, it is prevalent that gas-related hazards
are associated with the greater proportion of fatalities in his-
tory. Hence, there is a requirement of identifying the state-
of-the-art models in gas hazard monitoring for the UCM
scenario.
Several studies have presented a detailed review of under-
ground coal mines’ gas hazard monitoring and identification
technologies. Szlązak et al., in the literature [89], presented
an assessment of current methods of methane control during
multi-seam extraction by longwall mining in Polish mines.
The study in literature [52] has discussed the various UCM
gas hazard indicator gases and their monitoring methods.
Literature [33] has reviewed the early warning monitor-
ing technology related to rock burst hazards in coal mines.
The literature [74] has emphasized the factors affecting the
explosion hazards in the UCM and their associated preven-
tive measures.
Similarly, the authors in the literature [65] have reviewed
the recent trends in UCM gas hazard monitoring dedicated
towards the application of wireless sensor networks. All
these methods are emphasized in the UCM hazard moni-
toring and mitigation. However, none of the literature has
effectively reviewed the effectiveness of machine learning
(ML) methods in UCM gas hazard identification. Table 2
briefs the objectives of several existing studies that reviewed
the UCM hazard and safety for the last two decades.
Table 2  prevails  that  most  of  the  existing  literature
reviews  are  only  dedicated  towards  mining  operations,
wireless sensor networks, and the assessment of disasters.
With the advancement of computational power and artifi-
cial intelligence (AI) technologies, the application of ML is
being investigated in UCM scenarios. However, to the best
of the authors’ knowledge, no comparative review related to
the application of ML against the UCM gas hazard predic-
tion is presented.. Therefore, this study aims to explore the
advancements in ML-based UCM hazard identification and
monitoring techniques and compare the conventional and
ML-based hazard identification methods. The contribution
of the study is as follows.
-     The application of popular prediction and estimation
methods in UCM gas hazard identification is discussed.
-     The comparison of conventional methods with the artifi-
cial neural networks in the context of UCM is presented.
-     The limitations of existing ML-based gas hazard identi-
fication and prediction models are explained.
Table 1    Comparison of
fatalities in commonly
occurring hazards
Country/periodGas explosion and
poisoning (%)
Fire (%)Rock
brust + roof col-
lapse (%)
Water/floodOther (%)
## China, 2001–2015 [60]64.724.088.4616.845.9
## India, 2001–2014 [91]3.36–55.14–41.5
## Poland, 2008–2017 [14]82.20.015.62.20.0
## USA, 1900–2006 [41]89.526.260.71–3.51
Table 2    Review studies related to UCM hazards and safety
Authors/LiteratureRepositoryYearReview objective
Wang et al. [98]Springer2022Ground warer Inrush Hazard
Verma and Chaudhari [97]ScienceDirect2016UCM hazard risk assessment techniques
Muduli et al. [65]ScienceDirect2018Application of wireless sensor network for environmental monitoring in UCM
Black [10]ScienceDirect2019Coal and gas outburst in Australian coal mines
Szlazak et al. [89]Springer2020Control of methane emission during multi-seam extraction of longwall mining in
Polish coal mines
Ray et al. [74]ScienceDirect2022Study the disasters occoured in the coal mines in last two daceds
Kumar [43]Springer2015Rescent innovation in mining equipments related to safety
Shahmoradi et al. [83]MDPI2020Application of drones in UCM
Mardonova and Choi [56]MDPI2018Wearable device technology for mining industries
Reddy et al. [75]IEEE2016WSN and monitoring technologies for mine safety
Dohare et al. [24]Taylor & Francis2015Wireless communication and environment monitoring in underground coal mines
Jung and Choi [38]MDPI2021Application of ML in mining exploration, exploitation and reclamation

## 373
Review on Machine Learning-Based Underground Coal Mines Gas Hazard Identication and
## 1 3
- This study can help identify the suitable ML methodol-
ogy for UCM gas hazard monitoring scenarios.
## 2    Background
2.1    Gas Hazards Constraints in UCM
UCM gas hazards constitute a larger proportion of accidents
and fatalities. The gas responsible for hazards in the UCM
can be classified into two groups, i.e., toxic and flamma-
ble gases. Various toxic and flammable gases present in the
UCM are already discussed in the literature [26, 41, 44, 69,
70]. The toxic gases directly impact the worker’s health and
well-being if they exceed their threshold limit values (TLV).
Moreover, the flammable gases do not affect miners’ health
directly, but due to their flammability properties, they may
result in gas or coal-dust explosion, which is fatal and life-
threatening too. A brief explanation of these gases is pre-
sented in Table 3.
Apart from these gases, temperature and humidity are
also significant parameters determining the effectiveness
of the mining workers. Furthermore, these parameters also
affect the flammability limits of gases like
## CH
## 4
. Hence, these
parameters must be considered to design an effective gas
hazard monitoring and prediction system.
## 2.2    Underground Mine Gas Monitoring System
The UCM gas monitoring has been extensively investigated
for a safe and reliable operation throughout mining history.
A study in literature [82] has discussed the methane air-
flow pattern in a longwall mining operation. The gas pat-
tern was monitored using the automatic methane monitors
fixed throughout the length of the longwall face. Another
study in Schatzel et al. [81] presented the consequences of
methane emission due to the increased longwall face length.
This study also adopted a similar approach to monitor the
methane across the longwall face. Moreover, these studies
adopted statistical tools like linear regression to realise the
gas pattern. The main concern in this approach is that only
a single attribute is used for such analysis.
However, the gas concentration may depend on other
parameters like ambient environment and ventilation sta-
tus. Various gases in the underground coal mines pose a
non-linear and complex relationship that is hard to realise
using a physical model; therefore, several studies adopted
the artificial intelligance (AI) approach. The AI-based deep
neural network (DNN) models can extract the non-linear
and complex rules among various attributes to reach a dedi-
cated solution. The study [93] proposed the artificial neural
network (ANN)-based methane forecast model. The study
proposed multiple multilayer perceptions (MLPs) for various
## Table 3
Hazardous gases in UCM
## Gas
## Property
## Impact
## Source
## Methane (
## CH
## 4
## )
Colourless, odourless,tasteless, flammable, lighter
than air
Asphyxiation, dizziness, headache, and nausea in
high concentrations due to the displacement of oxygen, explosion (5%–15%)
Trapped in coal seams released during the mining
process
Carbon monoxide (CO)
Flammable, colourless, tasteless, odourless, lighter
than air, and toxic
At 200 ppm, slight headache, tiredness, dizziness,
nausea after 2 to 3 h; at > 200 ppm, life-threatening after 3 h
Coal Mine spray painting, spontaneous coal combus-
tion in goaf, gas explosion, coal dust explosion
Carbon dioxide (
## CO
## 2
## )
Colourless, odourless, heavier than air, suffocating
At 5%, stimulated respiration; at 7% to 10%, uncon-
sciousness after few minutes of exposure
Workers’ respiration, coal seam or rock oxidation
process, underground blasting
Hydrogen sulphide (
## H
## 2
## S
## )
colourless, slightly sweet, rotten egg flavour, flam-
mable, toxic, heavier than air
The concentration of 0.005–0.01% will cause irrita-
tion in the eyes and respiratory tract after 1.2 h, the concentration more than 0.01% will result in death in a short time. Explosion (> 45.5%)
It is generated during combustion of gunpowder,
explosion of substances including sulphide, and drainage of water in flooded areas
Nitrogen dioxide (
## NO
## 2
## )
Reddish-brown colour in high concentrations, acrid
or bleach odour, non-flammable, heavier than air
At 1–13 ppm, irritation of nose and throat;
## ≤
## 80

ppm, tightness in chest after 3 to 5 min; > 80 ppm, pulmonary enema after 30 min
Produced by underground blasting in coal mine
## Hydrogen (
## H
## 2
## )
Colourless, reacts easily with other chemical
substances, explosive mixtures are easily formed, lighter than air
High concentration causes oxygen-deficient environ-
ment, headaches, ringing in ears, drowsiness, nausea, skin having blue colour
As a result of coal gasification [
## 9
## ]

## 374 M. Sharma, T. Maity
## 1 3
locations in the underground coal mines and achieved sig-
nificant forecasted results for all the MLPs. Apart from the
methane-related studies, several studies, like Bonetti et al.
[11], presented the monitoring of other gases, including
methane. Gas monitoring and estimation is one aspect of
the gas monitoring system, and another is communication
among the sensor nodes—reliable communication between
the sensor nodes for adequately implementing the gas haz-
ard monitoring system. The wired communication system is
the conventional approach in UCM. However, the dynamic
and complex working environment imposes various critical
challenges, like mechanical damage to the wired communi-
cation setup. Therefore, several studies like Chen and Wang
[17] and Muduli et al. [65] are intended for the develop-
ment of a wireless sensor network (WSN) that leverages the
advantages of wireless networks. However, the underground
mine geometry and coal properties restrict the full-fledged
WSN implementation. Therefore, the literature survey in this
study covers both aspects, i.e., challenges associated with
the current gas hazard monitoring prediction and estimation
and limitations imposed by the wired and wireless sensor
network.
## 3    Review  Process
Following steps are adopted to review the existing prior arts
related to ML-based hazard identification in UCM scenarios.
-     Defining the research questions: The following research
questions are formulated to start the review process.
(a) What are the available hazards in UCM cases?
(b)   What are the existing hazard identification and
monitoring methods?
(c)   What is the application of ML technologies in
UCM, and how are they affecting the environmen-
tal safety of UCM?
Based on the formulated research questions, the following
search terms are identified.
(a) Underground coal mines gas hazard.
(b) Gas hazard Prediction.
(c) Underground coal mines hazard monitoring.
(d) Gas hazard Identification.
(e) Gas hazard Forecasting in underground coal mines.
(f)    multi-sensor-data-fusion.
-     Selection of data source: For the study presented in this
review, authors have considered the literature available
in reputed journals and international conference pro-
ceedings. The considered electronic database are as fol-
lows.
(a) IEEE Explore
(b)   ScienceDirect
(c)    SpringerLink
(d)   MDPI
## (e)    Arxiv
## (f) Google Scholar
- Identification of relevant literature: To identify the rel-
evant literature for the review process, two factors are
considered, i.e., date of publication and objective of
the research work. The date of publication is consid-
ered between 2000 to 2022. Any literature considering
at least one research term mentioned in Step 1 is also
accepted for review.
The following sections discusses the existing literature on
UCM  gas  hazard  identification  and  prediction  based  on
ML methods. The discussed articles are the outcome of the
above-mentioned review process.
4   Gas Hazard Prediction and Estimation
in UCM
This section discusses various existing studies related to
UCM gas hazard monitoring, prediction, and estimation.
The associated theories of each methodology are briefly
explained,  along  with  their  application  in  the  UCM  gas
monitoring system. Moreover, a brief comparison is also
presented to identify the suitable option for the problem
underhand.
## 4.1     Kalman  Filtering
It is a recursive process for estimating the state of any phys-
ical phenomenon. A well-defined mathematical model of
any physical process is required for the state estimation. It
involves two steps, i.e., the prediction step and the update
step. In the prediction step, an estimated value of a priori
state is calculated as follows,
## In (1),
## ̂x
## −
k
is the a priori state for the kth time stamp,
## ̂x
## +
k−1
is
the a posteriori state of
## (k−1)
th time stamp,
u
k−1
is the con-
trol input to the physical model,
w
k−1
is the process model
noise for
## (k−1)
th time stamp.
## F
k−1
## ,
## G
k−1
,  and
## L
k−1
are the
state transition matrix, control input matrix, and process
## (1)
## ̂x
## −
k
## =F
k−1
## ̂x
## +
k−1
## +G
k−1
u
k−1
## +L
k−1
w
k−1

## 375
Review on Machine Learning-Based Underground Coal Mines Gas Hazard Identication and
## 1 3
model  noise  sensitivity  matrix.  In  this  step,  the  process
model covariance of
## (k−1)
th time stamp is also propagated
to the kth time stamp, given in (2).
where
## ̂
## P
## −
k
## ,
## ̂
## P
## +
k−1
are the priori and posteriori covariance of kth
and
## (k−1)
th time stamp and
## Q
k−1
is the covariance matrix
for the process model noise. The second step, i.e., the update
step, uses the linear measurement model for the correction
of the state. For the linear Kalman filter, the measurement
model can be given as,
where
## H
k
is  the  measurement  matrix,
## M
k
measurement
model noise sensitivity matrix, and
## V
k
is the measurement
model noise. The covariance matrix for the measurement
model is given in (4).
where
## R
k
is the covariance matrix of measurement model
noise. The state is updated as follows,
where
## K
k
is the Kalman gain that can be calculated as,
Again, the covariance of the update step also needs to be
propagated to the next time step, which is mentioned in (7).
Equations (1)–(7) represents the complete process of linear
Kalman filtering. The other variants are Extended Kalman
filter, Unscented Kalman filters and Ensemble Kalman fil-
ters. Further details in this regard are given in the literature
[5, 16], but a minimal number of literature is dedicated to
its usage for gas hazard prediction in the UCM. Literature
[99] has adopted the Ensemble Kalman filter to estimate
the methane gas dispersion in the main return airway. The
model was developed considering the stationary and regular
structure of the return airway. But the UCM environment
is dynamic and very complex, making it challenging to be
interpreted mathematically. Hence it becomes a challenging
task to design the process model in (1) and the measure-
ment model in (3). Another problem with this technique is
its scalability. That is, as the mine geometry changes, there
is a requirement to re-design the process model and meas-
urement model.
## (2)
## ̂
## P
## −
k
## =F
k−1
## ̂
## P
## +
k−1
## F
k−1
## T
## +Q
k−1
## ,
## (3)
y
k
## =H
k
x
k
## −
## +M
k
## V
k
## ,
## (4)
## S
k
## =H
k
## P
k
## −
## H
k
## T
## +R
k
## ,
## (5)
## ̂x
## +
k
## =̂x
## −
k
## +K
k
## 
y
k
## −H
k
x
k
## −
## 
## ,
## (6)
## K
k
## =P
k
## −
## H
k
## T
## S
k
## (7)
## ̂
## P
## +
k
## =(I−K
k
## H
## K
## )
## ̂
## P
k
## −
## 4.2     Least  Square
The least-square is a non-probabilistic method of param-
eter estimation. This method can estimate a parameter by
minimising the objective function mentioned in (8).
where
## 휀
is the measurement residual, it can be given as,
In (9), y is the actual output of any process,
## ̂x
is the estimated
state, and H is the measurement matrix. The optimal esti-
mated state can be found by minimising the overall measure-
ment residual in (8), which is given in (10).
The other variants of least squares are the weighted least
square and the recursive least square. It is a method that
estimates the parameters by minimising the squared dis-
tance between the data points and the regression line. For
the UCM case, literature [81] used this method to estimate
the parameter of a linear regression model to predict meth-
ane concentration. The disadvantage of this method is the
requirement of a regression model before the procedure.
On many occasions, it may require testing with multiple
regression models to get an optimal model, making it time-
consuming and resulting in suboptimal solutions for the
estimates.
## 4.3     Maximum  Likelihood
It is another parameter estimation technique; unlike least
squares, this model accounts for the probability distribu-
tion function (PDF) of the observed samples. The likeli-
hood function can be given as,
In (11), f represents the PDF, W is the parameter vector, Y is
the sample vector, and
y
## 1
## −y
k
are the elements of the sample
vector Y. To obtain the maximum likelihood estimate (MLE)
of W parameters, the first order partial derivative of likeli-
hood function L with respect to all the parameters in the W
vector is computed as,
## W
i
is the
i
th
element of the W. Using (12), the estimated
parameters associated with W can be obtained. For computa-
tional ease, instead of using (12), the partial derivative of the
## (8)
## J=휀
## 1
## 2
## +휀
## 1
## 2
## +...+휀
k
## 2
## =휀
## T
## ⋅휀,
## (9)
휀=y−H⋅̂x
## (10)
## ̂x
opt
## =(H
## T
## H)
## −1
## H
## T
y
## (11)
## L
## (
## W
## Y
## )
## =f
## 
y
## 1
## W
## 
f
## 
y
## 2
## W
## 
f
## 
y
## 3
## W
## 
## ....f
## 
y
k
## W
## 
## (12)
## 휕L(WY)
## 휕w
i
## =0

## 376 M. Sharma, T. Maity
## 1 3
log-likelihood is preferred. More details about MLE can be
observed in the literature [66]. In the UCM case, literature
[4] used MLE for the parameter estimation of the negative
binomial model for an injury variable indicator model. Apart
from this work, no significant study is present in the field
of UCM gas hazard prediction using the MLE. Again, this
method accounts for a known PDF model with its param-
eter to be estimated. However, in the UCM case, the limited
available data and its variability across different mines make
it challenging to design a generic hazard prediction model
using MLE.
4.4    Knowledge‑Based Expert System
The Knowledge-based expert system (KBES) consists of the
input as the sensor data, and it can be an image, environmental
parameters like temperature, humidity, or anything that can
be observed by means of a sensor. A typical schematic of a
KBES is shown in Fig. 1. The KBES generate decisions based
on the correlation between the input and the Knowledge base.
The knowledge base consists of syntactic rules and parametric
templates for decision-making. The rules can be in the form
of an "IF-Then" statement. More details about this method
are given in the literature [59]. Comparatively, this model is
among the simplest techniques that can be directly deployed on
small sensing devices like microcontrollers. Due to this fact,
most of the gas detectors for UCM are based on this method.
Literature [76] has proposed an IoT-based mine safety system
using an Arduino controller, interfacing gas sensors, and a
speaker as an alarm indicator. The alarm signals are designed
such that a gas level rises to its maximum allowable limit, the
speaker starts to ring. Literature [87] proposed an IoT-enabled
smart helmet for UCM environment monitoring. The helmet
consists of sensors as the input microcontroller that samples
the sensor data and transmit it to a cloud server. In the cloud
server, the sensed data are correlated with a predefined set of
rules to generate the alarm signal. Literature [80] proposed a
mine hazard alert system to mitigate fire, water, and strata-
related hazards. Sensors integrated with microcontrollers for
these modalities are used to serve the purpose, and a dedicated
rule base is used for hazard identification. Similar kinds of
studies can be observed in the literature [25, 36, 68, 85, 108]
with a dedicated knowledge for hazard identification.
## 4.5     Fuzzy  Set  Theory
Fuzzy set-based inference models are suitable when there is
vagueness in the input data, or the input data is fuzzified [39].
For vague data mostly represented by a linguistic variable, it
consists of two steps. The first step is to develop a fuzzy rule
base for the inference model, as mentioned in (13).
The fuzzy rule mentioned above has an ‘IF-THEN’ struc-
ture containing some statements. The statement associated
with ‘IF’ is antecedent, and the statement associated with
‘THEN’ is consequent. The antecedent is the combination
of various attributes
## (A
## 1
## −A
k
## )
with their
i
th
linguistic vari-
ables
## (S
## 1
## −S
n
## )
using logical operators like AND, OR, and
NOT. Furthermore, the consequent statement associated
with ‘THEN’ is output O represented with a linguistic vari-
able D. The output is a fuzzy variable that is again converted
to a crisp number using defuzzification methods. The com-
plete process is to employ the vague input variable to the
fuzzy inference model, where the inference is made using
the predefined set of rules and gives a fuzzy output that is
converted to a crisp value using the defuzzification process.
Another scenario of fuzzy set theory is when the input is a
crisp number but converted to the fuzzy variable using the
fuzzification process. In this process, each crisp input vari-
able is associated with a linguistic variable using a member-
ship function, as mentioned in (14).
In (14), F represents the set of fuzzy variables for crisp input
x,
## 휇
k
represents the membership function for the kth fuzzy
variable within [0,1]. Further details about this method can
be gained from the literature [64]. Since this method does
not require any physical model or prior historical data, it is
extensively used for fire and gas-related hazard mitigation
in the UCM. In literature [50] fuzzy AHP-based Bayesian
network is studied over the explosion hazard. Various fac-
tors like ventilation failure, seal quality, human error, and
instrument error are considered, and a questionnaire was
arranged with multiple subject domain experts to get the
occurrence probability of those factors based on fuzzy AHP.
Literature [19] presented the study in fire intensity for UCM.
The concentrations of
## O
## 2
## ,
## N
## 2
## ,
## CO
and temperature are con-
sidered as the input to the fuzzy inference system. The trap-
ezoidal membership function is used for all the input for
## (13)
## R∶IF(A
## 1
isS
i1
## ANDA
## 2
isS
i2
## AND
## A
## 3
isS
i3
## ....ANDA
k
isS
ik
## )
THEN(OisD)
## (14)
## F=
## 
x,휇
k
## (
x
## )
## 
∶∀x∈X
## 
Fig. 1    Knowledge-based expert system

## 377
Review on Machine Learning-Based Underground Coal Mines Gas Hazard Identication and
## 1 3
the fuzzification process, and the centroid of area (COA)
has been used for the defuzzification of the fuzzy output of
the model. In literature [54], fuzzy TOPOSIS-based hazard
mitigation is proposed. It considered multiple hazard fac-
tors for the UCM like geochemical, electrical, mechanical,
chemical, environmental, personal, and social. The ranking
of the abovementioned factors is done using fuzzy TOPO-
SIS. Literature [7] also deals with fire intensity monitoring
in the UCM based on various gases but using a type 2 fuzzy
logic controller. The type-2 controller has the advantage of
modelling the uncertainty in the membership function of the
type-1 fussy controller. Similarly, the literature [13] and Shi
et al. [86] presented the different variants of the fuzzy-based
hazard monitoring system for the UCM.
## 4.6     Bayesian
It is another popular ML technique based on the probability
theory. Primarily used in a network form, it is integrated
with an acyclic graph to represent the complex and fuzzy
relationship among the various factors of a given problem.
These networks, also known as Bayesian network (BN),
includes a directed acyclic graph and conditional probabil-
ity table. Figure 2 depicts the basic structure of a BN. The
joint probability distribution of a node can be calculated
using (15).
where x represents the individual nodes and parent(x) rep-
resents the parent node of x. More details in this regard can
## (15)
## P
## (
a,b,c,d,e,f,g
## )
## =
## 
x∈a,b,c,d,e,f,g
## P(xparent(x)),
be found in Stephenson [88]. The usage of BNs in UCM
hazard mitigation has been extensively studied. Literature
[90] has shown the usage of a BN integrated with the Delphi
method as an effective tool for assessing mine explosion
hazards. Zhang et al. proposed a gas outburst prediction
model based on weighted Bayesian [106]. The posterior
probabilities under various indexes are weighted based on
the entropies among the indexes. The outburst probability is
then calculated using the weighted posterior probabilities. In
literature [49], Li et al. studied the fuzzy Bayesian network
for the risk assessment of the mine ignition sources. A fuzzy
AHP model is adopted to incorporate the decision of various
subject experts based on their expertise, knowledge, educa-
tion level, and other parameters. A similar kind of study can
be seen in articles [23, 34, 47, 48].
## 4.7     Neural  Networks
ANNs are biologically inspired mathematical models con-
sisting of processing elements called neurons. Each neuron
is connected using a coefficient called weight [84]. The
fundamental structure of an ANN is depicted in Fig. 3.
Unlike the previously discussed models, ANN does not
require explicit modelling to exhibit the detection or clas-
sification task. Therefore, ANN is a suitable candidate for
complex physical phenomena where mathematical mod-
elling is not possible or is not resource-efficient. These
supervised learning-based data-driven models are diverse
based on their fundamental operation and architectures.
For UCM gas hazard cases, neural networks are exten-
sively used for forecasting and prediction purposes. These
Fig. 2    Knowledge-based expert
system

## 378 M. Sharma, T. Maity
## 1 3
models can broadly be classified into two groups, i.e., shal-
low neural networks and DNNs. Both types are briefly
explained as follows.
- Shallow Neural networks: A shallow neural network is
a specific class of neural network model with a com-
paratively smaller number of hidden layers than a DNN.
These models are considered less complex than DNNs
like CNNs or recurrent neural networks (RNN). Support
vector machines and ANN with a single hidden layer
are popular models in this category. The basic struc-
ture of the Shallow neural network is shown in Fig. 3.
The computational process associated with the model in
Fig. 3 is as follows. The majority of the neural network
model follows a fundamental computation process. This
process is divided into two steps, i.e., forward propaga-
tion and backward propagation. The brief of these two
processes is discussed below.
(a)    Forward  propagation:  The  non-linear  combi-
nations  of  input  weighted  by  dedicated  coef-
ficient and biases are joined together to achieve
a required output value. A typical realisation of
the forward propagation for a network in Fig. 3 is
given in (16).
where
## A
## 1
is the activation of hidden layer ‘1’,
## W
## 1

is the weight matrix associated with the hidden
layer ‘1’ and the previous layer, X is the previous
layer input in vector form,
## B
## 1
is the bias associated
with layer ‘1’. In (16), g, represents the non-linear
activation function, like sigmoid, tanh and RELU.
Similarly, the output can be realised as,
## (16)
## A
## 1
## =g
## 
## 
## W
## 1
## 
## T
## ⋅X+B
## 1
## 
## ,
(b)    Backward  propagation:  It  updates  the  weight
or coefficient of each layer based on the gradi-
ent descent algorithm. The gradients of residual
between the actual and the predicted values are
derived and propagated back throughout the net-
work.  The  residuals  can  be  calculated  using  a
dedicated loss function, given as,
In (17), J is the loss function. The parameter W for
the different layers can be updated using the gra-
dient descent algorithm [77], and the parameter
updates can be represented as follows.
where
## 훼
is a hyperparameter called learning rate,
## 훿J
## 훿W
is the gradient of the loss function with respect
to the parameter W. The capability of ANN in
generating non-linear decision boundaries helps
to model problem solutions for complex tasks.
In contrast, SVM, a large-margin classifier, is dif-
ferent from the traditional ANN models in terms of its
decision boundaries. SVM implements an extra margin
around the decision boundaries, shown in Fig. 4, which
is uncommon in the ANN-based models [63]. Therefore,
SVM provides more accurate decisions as compared to
the ANN-based classifiers. These models are considered
for gas concentration prediction in UCM scenarios. The
study in the literature [100] introduced the backpropa-
gation ANN (BP-ANN) model to mitigate the danger
degree associated with spontaneous coal combustion in
the UCM. The authors also investigated the genetic algo-
## Y
## 2
## 0
## =g
## 
## 
## W
## 2
## 
## T
## ⋅A
## 1
## +B
## 2
## 
## (17)
## J=
## 1
## 2m
m
## 
i=0
## 
y
i
## −y
i
## 
## 2
## W=W−훼
## 훿J
## 훿W
## ,
Fig. 3    ANN Architecture
Fig. 4    ANN Architecture

## 379
Review on Machine Learning-Based Underground Coal Mines Gas Hazard Identication and
## 1 3
rithm’s effect to optimise the model’s hyperparameter.
The outcome of the complete study was an optimum
and robust model with faster training performance. An
Unscented Kalman filter (UKF) based BP-ANN model
is introduced in the literature [102]. The UKF is claimed
to be used to adjust the BP-ANN model parameters, but
no such validation is shown in the literature. The author
also claimed that the proposed system is robust against
faults and has high decision-making precision. Authors
of the literature [94] have proposed a multi-layer-percep-
tron model for the methane concentration prediction of
UCM. They studied the effect of the various architecture
in the prediction process to forecast the methane concen-
tration for the next 15 min. Literature [6] has proposed
an ANN model to classify the fire hazard class using
the measurable parameters of UCM like
## CO
## ,
## CO
## 2
## ,
## O
## 2
## ,
air velocity, and other parameters. The study has shown
that the proposed model’s classification accuracy was
97%. Similar kinds of studies like [32, 37, 78, 101] sug-
gested the application of ANN as a reliable model for
gas hazard prediction in the UCM scenarios. In contrast
to the studies involved in ANN, a significant portion of
the literature also involves SVM-based models. The arti-
cle [20] has proposed an SVM-based regression model
integrated with particle swarm optimisation (PSO). The
model was intended to predict the temperature of the
continuous coal combustion inside a goaf using the pre-
sent gases like CO and
## CO
## 2
. In comparison with the
BP-ANN models, the SVM-based regression model was
more accurate in temperature prediction. The literature
[46] has investigated the systematic comparison of the
Random Forest model and SVM for the prediction of
the temperature of continuous coal combustion in UCM.
The principal component analysis was used to generate
a dimensionally reduced feature set. The investigation
has shown that the performance of SVM can be signifi-
cantly affected by the selection of the hyperparameter,
but in comparison, the RF model was robust against the
proposed SVM and showed better prediction accuracy
compared to the SVM. However, an optimum selection
of the SVM hyperparameter significantly improves the
prediction performance of the SVM. Another study in
the literature [92] has compared K-nearest neighbour
(KNN), Logistic regression (LR), Decision-Tree (DT),
and SVM for the mine hazard classification. For this
purpose, 17 input variables affecting underground safety
were selected. The input attributes like mean, variance,
quartile, and maxima are manually extracted for each
input variable. The comparison has shown that, except
for the DT, all models have shown acceptable classifica-
tion performance based on the accuracy and F1-score
metrics. Apart from the normal SVM, one of its vari-
ants, i.e., least square-SVM (LSSVM), has also been
the subject of discussion in the field of UCM gas haz-
ard. One study in the article [15] has investigated the
methane-based gas-related hazard using LSSVM. The
authors have proposed a forecasting and forewarning
model based on the LSSVM. The forecasting model is
claimed to have high precision with a credible forewarn-
ing model. However, the proposed model was not com-
pared with the other available methodologies that could
have supported the claim. Other similar studies based on
the investigation of LSSVM for UCM hazard scenarios
are presented in the literature [18, 104, 107].
-     DNN: Unlike shallow neural networks like ANN and
SVM, DNN architectures consist of a larger number of
hidden layers and usually have a complex neural net-
work. ANNs with a relatively higher number of hidden
layers, also called Deep-ANN (DANN), Convolutional
Neural Networks (CNN), and RNN, are among the most
studied fundamental DNN models. The operational fun-
damentals of the DANN are the same as ANN, except it
has a larger and more complex network structure. How-
ever, the operation of CNN and RNN has fundamental
differences compared to the DANN. The basic principle
behind CNN and RNN are discussed below.
(a)    CNN:  These  models  are  commonly  employed
for  spatial  feature  extraction.  The  auto  feature
extraction capability of the CNN models has an
additional advantage over the other DNN mod-
els where manual feature extraction is required
[3]. The basic structure of a CNN architecture
is shown in Fig 5. In contrast to the ANN archi-
tecture, CNN performs convolution operations
between the input and the kernel. The input block
is a tensor of shape
## (h×w×c)
, where ‘h’ indi-
cates the number of rows, ‘w’ indicates the num-
ber of columns, and ‘c’ represents the number of
channels. The kernel block is analogous to the
neurons of ANN architecture, containing specific
weights that can convolve across the input. The
kernel block is also a tensor having the shape of
## (a×b×c)
, where ‘a’ is the height of the kernel,
‘b’ is the width of the kernel, and ‘c’ is the num-
ber of channels. It is worth mentioning that the
number of channels of the kernel and the input
shall be the same. The ’Conv out’ block repre-
sents the tensor that stores the extracted features
from the convolution process. For more details
in this context, literature [29] can be taken as a
reference.  Although  the  ML-based  models  for
the  UCM  scenarios  are  at  the  initial  stages  of
the research, CNN-based gas outburst prediction
models are also available. The literature [51] pro-
posed a CNN-based coal and rock outburst hazard

## 380 M. Sharma, T. Maity
## 1 3
using acoustic emission (AE) and Electromagnetic
radiation (EMR) signals. The AE and EMR sig-
nals are initially modified using empirical mode
decomposition (EMD) and then converted into a
two-dimensional tensor for the CNN input. The
authors have used an indirect method of predict-
ing the rock and gas outburst, i.e., using EM and
EMR instead of gas concentrations. In the litera-
ture [105], RFID based methane concentration
prediction  model  is  proposed.  The  prediction
algorithm is based on an integrated CNN-LSSVM
algorithm. The CNN is used to extract the robust
features from the row sensor data using an RFID
tag, and the prediction is made using the LSSVM
model.  The  authors  of  the  literature  [73]  have
established the gas hazard classification and pre-
diction model using K-NN integrated with CNN.
The K-NN is used to classify the source of abnor-
mal gas concentration, and CNN is used to predict
the outburst risk due to the blasting process.
(b)    RNN:  These  are  like  the  ANN  in  architecture
with  some  additional  temporal  structure.  This
temporal structure extracts the temporal features
of any time series sequence. The basic architec-
ture of the RNN is depicted in Fig. 6. In the RNN
architecture,
## X
## 1
## -
## X
## T
represents the time series data
Fig. 5    CNN-based model

## 381
Review on Machine Learning-Based Underground Coal Mines Gas Hazard Identication and
## 1 3
sequence, and
## A
## 1
## 1
## -
## A
## 1
## T
are the extracted features
for the given time-stamp
## 1−T
. The subscript in
the above-mentioned notations indicates the time
stamp, and the superscript represents the layer
number. Furthermore, the intuitive block diagram
for one of the time-stamp operations in the RNN
architecture  is  shown  in  Fig. 7.  The  RNN  cell
shown in the figure has two inputs, one is from the
actual input (
## X
t
) of the corresponding time stamp,
and  another  is  from  the  previous  time-stamp
## (A
l
t−1
## )
. The other variants of the RNN are gated
recurrent unit (GRU) and long short-term mem-
ory (LSTM). The basic difference between the
plain RNN, LSTM, and GRU is that they exhibit
memory-retaining cells operated by some gated
mechanism. This memory cell helps to maintain
the temporal features over the long temporal sam-
ples. The detail about the RNN models and their
variants can be seen in the literature [79]. The
usage of the RNN-based models for the coal mine
methane concentration forecast is evident in recent
literature. The article [103] presented the LSTM-
based menthane gas concentration prediction in
the UCM. The whale optimisation algorithm was
used to optimise the LSTM for the hyperparam-
eters. Additionally, the author introduced the input
sequence’s empirical mode decomposition (EMD)
to get individual intrinsic mode function (IMF) as
an input to the LSTM. The authors in the literature
[45] proposed uniform manifold approximation
and projection (UMAP)-LSTM-based mine fire
prediction using various attribute gases like
## O
## 2
## ,
## CO
## ,
## CO
## 2
## ,
## CH
## 4
## ,
## H
## 2
## ,
## N
## 2
,  and
## C
## 2
## H
## 4
. The proposed
model was substantially efficient compared with
traditional ML methods like SVM and ARIMA.
The studies in the literature [61] and Dey et al.
[22] also utilise the LSTM -based model for gas
hazard prediction in the coal mines.
Apart from the CNN and RNN models, some litera-
ture, like Dey et al. [21] and Hati et al. [31], advocate
using a hybrid CNN-LSTM model for gas concentra-
tion forecasting in coal mines. The hybrid architectures
leverage the advantages of both, i.e., auto feature extrac-
tion from CNN and maintaining the temporal integrity
between the extracted features. These hybrid models
have shown better performance than the independent
CNN or RNN models.
4.8    Comparison of Fusion Models
This section compares the above-mentioned algorithms in
the context of UCM scenarios. This attempts to filter out the
most suitable sensor fusion algorithms for the UCM sce-
narios. The comparison is presented in Table 4.
Considering the UCM scenarios, the dynamic and com-
plex environment makes it difficult to realise a physical
model for a gas hazard monitoring process. Even the stud-
ies in the literature, like Wu et al. [99], are based on the
approximate physical model with several assumptions. No
practical usage of physical model for gas hazard prediction
and mitigation has been reported yet. Therefore, the physical
models are not suitable for the gas hazard prediction task.
Due to the non-linear relationship among the gas concen-
trations and their hazards, maximum likelihood and least
square-based models are also unsuitable for the concerned
purpose. Therefore, very little literature can be found for
the Kalman filtering, least square, or Maximum likelihood.
Compared  with  the  previous  models  in  Table 4,  the
Bayesian model is not bound to any predefined mathematical
model as in the least square or maximum likelihood. In con-
trast, these models require conditional probability tables that
may be cumbersome to design for multiple hypotheses and
conditionally dependent events. Although, all these models
severely suffered from data uncertainty and vagueness. In
contrast, the tough and dynamic environment makes sensor-
based monitoring susceptible to various noisy measurements
that impose uncertainty on the data. Fuzzy-set theory and
Fig. 6    Basic RNN architecture
Fig. 7    RNN cell

## 382 M. Sharma, T. Maity
## 1 3
Dempster-Shafer-based  models  can  handle  these  uncer-
tainties and vagueness in the data. These models are found
significant when very small information is available, and
the inference engine is developed with the help of a human
expert and cognitive intelligence. However, these models
are not suitable for pattern recognition or forecasting tasks.
Unlike the other sensor fusion algorithm, ANNs and DNNs
can find the non-linear relationship between any process’s
input and output variables. These models proved to be highly
efficient for highly complex and non-linear processes.
Moreover, shallow neural networks like ANN or SVM
are susceptible to noisy data, but DNN models like CNN
can handle the noisy data. Neural networks’ efficient
pattern recognition capability makes them a suitable for
the  UCM  hazard  recognition  models.  The  significant
limitations  of  these  data-driven  models  are  observed
when any fault in the sensor occurs. A faulty sensor may
result in faulty observations resulting in faulty estima-
tion or prediction. There is no literature found dealing
with this practical issue. Additionally, most of the stud-
ies are primarily concerned with designing a data-driven
model whose reliability may be a concern in uncertainty
scenarios.
Table 4    Comparison of UCM gas monitoring models
ModelAdvantageDisadvantage
Kalman filtering [99]1. More accurate compared to data-driven
models
- Kalman filtering is only suitable for a well-
defined physical model
- It effectively considers the process model
and measurement model noise, shown in
(2) and (4), which is not present in the other
traditional approaches
- Non-linear process models are complex
to realise, and those are computationally
expensive
Least Squares [81]1. Simple modelling1. Require a predefined model, unsuitable for a
dynamic and complex process
- No requirement for prior information2. Not flexible towards the changes in the input
parameters
- Does not require any physical models
Maximum Likelihood [4]1. The usage of PDF instead of curve fitting
improves the estimation accuracy
- Requires prior knowledge of the PDF related
to the parameters under investigation
- It does not require any physical model2. Estimates can be biased for a small sample
- The complexity of the model depends upon
the choice of the likelihood function
Bayesian [23, 34, 47–49, 90, 106]1. Does not require any physical model1. A priori probability distribution is required
beforehand
- Suitable for the small data sample2. For multiple hypotheses and multiple condi-
tional dependents, it becomes complex
- Combining different sources of knowledge
## [96]
- Require conditional probability tables for
Bayesian network models [40]
- Considers only two hypotheses at a time
Knowledge-based expert systems [25, 36, 68,
## 76, 80, 85, 87, 108]
- Simple in design1. Requires predefined rule base
- No need for any physical models2. Can not handle uncertainty in measurement
- It May result in a faulty decision when slight
observation deviations occur
Fuzzy set theory [7, 13, 19, 50, 54, 64, 86]1. Can effectively handle vagueness in the data
sample
- Require a predefined rule base
- Type-2 fuzzy inference model can handle
data uncertainty [58]
- Only supports the identification or classifica-
tion tasks, not suitable for forecasting [1]
- No requirement for physical models
## Neural Networks [6, 15, 18, 20–22, 31, 32, 37,
## 45, 46, 51, 61, 73, 78, 79, 92, 94, 100–105,
## 107]
- It Does not require any explicit physical
model
- The feature engineering step can be time
cumbersome
- Learns the rules related to a process using
historical data only
- These are black-box models [30]
- Does not require any prior knowledge of
probability distributions [55]
- These models are computationally complex
compared to the other models

## 383
Review on Machine Learning-Based Underground Coal Mines Gas Hazard Identication and
## 1 3
4.9    Comparison of Neural Networks Models
A brief comparison of the conventional neural networks-
based models from the existing articles in the UCM sce-
narios is presented in Table 5,
Table 5 evaluates the usage of ML models related to
gas hazards in the UCM. The table dictates the signifi-
cant performance of these models in terms of accuracy
in a dynamic and complex environment of a UCM. Most
of the models presented in the discussion have achieved
good classification or regression accuracy.
4.10    Challenges Associated with Neural Networks
The models discussed in Table 5 access the sensor data from
the underground coal mines to process inferential actions.
The complete inference pipeline exhibits data collection,
data engineering, model preparation and model deployment.
In the data engineering step, features from the row sensor
data are extracted and normalised for training and validation
purposes. However, certain limitations associated with this
approach are as follows,
- A very small number of articles are available for DNNs
implementation in UCM hazard monitoring.
- All the hazard forecasting models adopted a uni-model
approach,  i.e.,  individual  networks  are  dedicated  to
Table 5    Comparison of neural network in UCM scenarios
ModelLiteratureTaskPurposeRemak
ANN and its variants[100]ClassificationPrediction of coal spontaneousNo quantitative result is mentioned
[102]RegressionCoal and methane outburst prediction
## R
## 2
## —0.99
[94]RegressionPrediction of methane concentrationMean Test RMSE—0.021, MAPE%—2.05
[6]ClassificationMine fire classificationAccuracy—97%, F1-score—96.7%
[78]ClassificationCoal and gas outburst predictionClassification accuracy 87%
[32]ClassificationCoal and gas outburst classificationAccuracy—100% approx
[101]RegressionGas outburst prediction
## MSE—393,
## R
## 2
## —0.98
[37]RegressionMine environment index prediction
## MAE—0.15, RMSE—0.21,
## R
## 2
## —0.6654
SVM and its variants[20]RegressionCoal temperature prediction
## MAE—0.5976, RMSE—0.8852,
## R
## 2
## —0.9656
[46]RegressionCoal temperature prediction
## MAE—0.461, RMSE—0.797,
## R
## 2
## —0.9709
[92]ClassificationMultiple hazard classificationJaccard—0.92, F1-score—0.89
[15]Classification
and Regres-
sion
Methane concentration forecasting and
hazard classification
The relative error between the actual and
predicted values is between 0.088 and
## 6.915%
[107]RegressionMine gas predictionNo quantitative result is mentioned
[104]RegressionGas content predictionThe relative prediction error is 0.39 to
## 1.71%
[18]ClassificationSeismic hazard predictionPrediction accuracy 93.96%
CNN and its variants[51]ClassificationCoal and gas outburst prediction using AE
and EMR
## Accuracy—98%
[105]RegressionMethane gas density predictionHigh accuracy (quantitative result is not
published)
[73]ClassificationOutburst risk predictionAccuracy—86.1%
RNN and its variants[79]RegressionCoal mine gas predictionMAE—0.018, RMSE—0.025
[103]RegressionCoal mine gas concentration predictionRMSE for
## O
## 2
## ,  CO,
## CH
## 4
## ,
## CO
## 2
## ,
## H
## 2
## ,
## N
## 2
,  and
## C
## 2
## H
## 4
gases—0.288, 0.006, 0.0995, 0.902,
0.238, 0.452, and 0.006
[45]RegressionMethane concentration prediction
## Highest
## R
## 2
—0.92 and Lowest RMSE—0.02
[61]RegressionUCM gas predictionPrediction accuracy—89.7–92.4%
[22]RegressionConcentration forecasting of UCM gasesLowest MSE—0.029
Hybrid of CNN and RNN
[21]RegressionMiner’s health quality index (MHQI)
prediction
## MSE—0.0009
[31]RegressionPrediction of ventilation system airflow
of UCM
RMSE—0.01, MAE—0.02, Accu-
racy—96.7

## 384 M. Sharma, T. Maity
## 1 3
individual parameters for the predictions. However, the
prediction of that parameter can be influenced by other
factors which are not considered in any of the present
literature.
-     Actual sensor data usually have uncertainty due to vari-
ous factors. Any uncertainty may lead to wrong clas-
sification or estimation, especially in edge scenarios,
e.g., a methane sensor with a reading of 12,000 ppm,
a threshold value of 12,500 ppm and a measurement
uncertainty of 5% may not be able to decide whether the
sensor observation is below the threshold or above it.
-     All the neural network models are trained on a crisp
sensor value that does not consider the sensor uncertain-
ties, which may result in reduced accuracy in real-time
scenarios.
- The issue can persist if there is an occurrence of sensor
malfunctioning. Due to the harsh and complex under-
ground environment, sensor malfunctioning is frequent
and inevitable in the UCM. The evidence of faulty node
scenarios has been observed in the UCM hazard moni-
toring studies. The study in the literature [82] prevailed
about a malfunctioning methane sensor on the third day
of their experiment in the coal mine. Consequently, the
methane concentration was high compared to the other
methane monitors. Another study in literature [42] also
reported a similar kind of event. The methane monitor
installed at the 80th shield gave conflicting observations
compared to the other methane monitors. A malfunc-
tioning sensor observation may result in an out-of-dis-
tribution (OOD) scenario, and it can be easily handled
using some statistical anomaly detection methods. How-
ever, it is not always necessary to observe a malfunction-
ing sensor following OOD. If such occurrences happen,
the estimation or classification process suffers from a
significant reduction in accuracy.
- The dynamic and complex UCM environment imposes
many restrictions on traditional hazard monitoring sys-
tems. Based on the survey of various works of literature,
the significant challenges associated with coal mine sen-
sor networks are as follows.
(a)   On the completion of coal extraction in one of
the mine galleries, there is a requirement to move
the  whole  machinery  and  infrastructure  to  the
following operating region. This dismantling and
remounting process imposes limitations on con-
ventional wired communication infrastructures.
(b)    Moreover,  wired  communication  networks  are
prone to mechanical and other damage.
(c)    In this scenario, wireless infrastructure is advanta-
geous in terms of flexibility and portability. How-
ever, the subsurface operations of the UCMs put
restrictions on traditional wireless systems.
(d)   Additionally, these wireless systems face high sig-
nal attenuation due to the coal dielectric proper-
ties and UCM geological features.
## 5    Possible  Solutions
The  unreliability  in  the  sensor  observation  due  to  node
or network-initiated malfunctions can be avoided using a
Dempster-Shafer evidence theory (DSET)-based multi-cri-
teria fusion process. The missing data and uncertainty-han-
dling capability of DSET confirm it as a reliable decision-
making model [27]. Due to its superior uncertainty handling
capability [8], DSET is widely used in various fields like
wireless sensor networks, fault detection in motors, and envi-
ronment monitoring [2, 35, 57, 67]. However, the DSET has
not ever been investigated in the UCM environment monitor-
ing process that inherently poses significant noise in real-
time sensor observations. Therefore, there is an opportunity
to investigate the DSET for the UCM scenario. However,
DSET combines the beliefs from multiple sources to make a
decision. Therefore, increasing the number of sources would
lead to an increase in computational cost. Therefore, DSET
can not replace the neural network that can handle a large
amount of information simultaneously. However, DSET can
be utilised as a front-end to the conventional neural net-
work models, utilising fixed and comparatively lesser data
to identify and filter out malfunctioning sensor observations.
The utilisation of DSET for sensor fault identification has
been studied in the literature [28]. The literature shows a
remarkable improvement in decision-making compared to
conventional models.
Another significant challenge is reliable communication.
The limitations of wired and wireless communication infra-
structure have already been discussed. Due to the challeng-
ing geography of UCM and the nature of the underground
environment, realising a reliable wireless sensor network is
inefficient. Therefore, the implementation of any real-time
gas hazard monitoring model is strictly limited due to the
implications mentioned above. The conventional deep learn-
ing (DL) models require higher computational resources like
cloud-based servers or a dedicated computer. Therefore,
these models cannot be directly implemented for UCM in
real-time scenarios. Although the local area wireless sensor
networks, where line of sight communication is possible,
like in longwall mining operations, can be adopted, these
local area networks can be integrated with the wired com-
munication infrastructure. LPWAN is sought as an optimal
solution for developing a Local area network, given their low
power and long-range features. Another approach is edge
machine learning (EML), where a neural networks can be
transformed into a lighter version based on the requirement
of the resource constraint edge devices like microcontrollers

## 385
Review on Machine Learning-Based Underground Coal Mines Gas Hazard Identication and
## 1 3
[62]. The EML models can run on edge devices and can
be deployed directly on the actual (in-situ) location. There-
fore, it does not require any internet connection, reducing
network-related latency and security issues.
## 6    Conclusion
The underground coal mine environment is utterly unpre-
dictable due to the sudden presence of various gas hazards
and therefore requires monitoring continuously for work-
ers’ safety. This literature survey discusses the challenges
observed for the end-to-end realisation of the UCM gas
hazard monitoring system. The survey prevails over cer-
tain limitations associated with the commonly adopted gas
monitoring models in terms of scalability, human interven-
tion and prediction and classification accuracies. Moreover,
neural network-based models have performed significantly
well in terms of estimation and identification accuracy. How-
ever, the reliability of these models is challenged by the data
uncertainty originating from real-time sensor observations.
Additionally, the implementation of neural networks tradi-
tionally employs a cloud server or dedicated computer, but
the implications of WSN limit these approaches.
Therefore, based on these existing limitations, a multi-
sensor fusion based on DSET can be used as a front end of
the neural network to filter out faulty and malicious data
samples in real time. Since traditional cloud-based neural
network solutions are not feasible, EML can be a better solu-
tion for practically implementing the smart hazard prediction
model. Although this study is limited to the review of the
ML-based gas hazard identification methods, this can be
further extended to the other hazards to achieve a broad idea
in the context of overall UCM hazard safety.
## Declarations
Conflict of interest On behalf of all authors, the corresponding author
states that there is no conflict of interest.
## References
-    Adriaenssens V, De Baets B, Goethals PL et al (2004) Fuzzy
rule-based models for decision support in ecosystem manage-
ment. Sci Tot Environ 319(1–3):1–12
-    Ahmed M, Huang X, Sharma D et al (2012) Wireless sensor
network internal attacker identification with multiple evidence by
dempster-shafer theory. International conference on algorithms
and architectures for parallel processing. Springer, Berlin, pp
## 255–263
- Alzubaidi L, Zhang J, Humaidi AJ et al (2021) Review of deep
learning: Concepts, cnn architectures, challenges, applications,
future directions. J Big Data 8(1):1–74
- Asfaw A, Mark C, Pana-Cryan R (2013) Profitability and occu-
pational injuries in us underground coal mines. Accid Anal Prev
## 50:778–786
- Auger F, Hilairet M, Guerrero JM et al (2013) Industrial appli-
cations of the Kalman filter: a review. IEEE Trans Ind Electron
## 60(12):5458–5471
- Barros-Daza MJ, Luxbacher KD, Lattimer BY et al (2022) Real
time mine fire classification to support firefighter decision mak-
ing. Fire Technol 58(3):1545–1578
-     Basu  S,  Pramanik  S,  Dey  S  et  al  (2019)  Fire  monitoring  in
coal  mines  using  wireless  underground  sensor  network  and
interval type-2 fuzzy logic controller. Int J Coal Sci Technol
## 6(2):274–285
-    Bellenger A, Gatepaille S (2011) Uncertainty in ontologies:
Dempster–Shafer theory for data fusion applications. arXiv Pre-
print. arXiv:1106.3876
-    Bhutto AW, Bazmi AA, Zahedi G (2013) Underground coal
gasification: From fundamentals to applications. Prog Energy
## Combust Sci 39(1):189–214
-  Black DJ (2019) Review of coal and gas outburst in Australian
underground coal mines. Int J Min Sci Technol 29(6):815–824
-  Bonetti B, Abruzzi RC, Peglow CP et al (2019) Ch 4 and co
2 monitoring in the air of underground coal mines in southern
Brazil and GHG emission estimation. REM Int Eng J 72:635–642
-  Brodny J, Tutak M (2018) Exposure to harmful dusts on fully
powered longwall coal mines in Poland. Int J Environ Res Public
Health. https:// doi. org/ 10. 3390/ ijerp h1509 1846
- Brodny J, Felka D, Tutak M (2022) The use of the neuro-fuzzy
model to predict the methane hazard during the underground coal
mining production process. J Clean Prod 368(133):258
-   Burtan Z, Chlebowski D (2018) Natural hazard conditions result-
ing in major accidents in the coal-mining sector in Poland. In:
25th world mining congress, Astana
-   Cao SG, Liu YB, Wang YP (2008) A forecasting and forewarning
model for methane hazard in working face of coal mine based on
LS-SVM. J China Univ Min Technol 18(2):172–176
-  Chen S (2011) Kalman filter for robot vision: a survey. IEEE
## Trans Ind Electron 59(11):4409–4420
-  Chen W, Wang X (2020) Coal mine safety intelligent moni-
toring  based  on  wireless  sensor  network.  IEEE  Sens  J
## 21(22):25465–25471
- Chou JS, Thedja JPP (2016) Metaheuristic optimization within
machine learning-based classification system for early warnings
related to geotechnical problems. Autom Constr 68:65–80
-  Danish E, Onder M (2020) Application of fuzzy logic for pre-
dicting of mine fire in underground coal mine. Saf Health Work
## 11(3):322–334
-   Deng J, Lei C, Xiao Y et al (2018) Determination and prediction
on three zones of coal spontaneous combustion in a gob of fully
mechanized caving face. Fuel 211:458–470
-  Dey P, Chaulya S, Kumar S (2021) Hybrid CNN-LSTM and
IoT-based coal mine hazards monitoring and prediction system.
## Process Saf Environ Prot 152:249–263
- Dey P, Saurabh K, Kumar C et al (2021) T-SNE and variational
auto-encoder with a Bi-LSTM neural network-based model for
prediction of gas concentration in a sealed-off area of under-
ground coal mines. Soft Comput 25(22):14183–14207
-  Dogra SK, Jayanthu S, Samal AK et al (2021) Machine learn-
ing approach to implement mine fire predicting for underground
coal mines. In: 2021 2nd global conference for advancement in
technology (GCAT), IEEE, pp 1–4
-   Dohare YS, Maity T, Das P et al (2015) Wireless communication
and environment monitoring in underground coal mines-review.
IETE Tech Rev 32(2):140–150
-  Dohare YS, Maity T, Paul PS et al (2016) Smart low power
wireless  sensor  network  for  underground  mine  environment

## 386 M. Sharma, T. Maity
## 1 3
monitoring.  In:  2016  3rd  international  conference  on  recent
advances in information technology (RAIT), IEEE, pp 112–116
-   Fan Z, Xu F (2021) Health risks of occupational exposure to toxic
chemicals in coal mine workplaces based on risk assessment
mathematical model based on deep learning. Environ Technol
## Innov 22(101):500
- Fontani M, Bianchi T, De Rosa A et al (2013) A framework for
decision fusion in image forensics based on Dempster-Shafer
theory of evidence. IEEE Trans Inf Forensics Security 8(4):593–
- https:// doi. org/ 10. 1109/ TIFS. 2013. 22487 27
-  Ghosh N, Paul R, Maity S et al (2020) Fault matters: Sensor
data fusion for detection of faults using Dempster-Shafer the-
ory of evidence in IoT-based applications. Expert Syst Appl
## 162(113):887
-   Goodfellow I, Bengio Y, Courville A (2016) Deep learning. MIT,
Cambridge. https:// www. deepl earni ngbook. org/
-  Guidotti R, Monreale A, Ruggieri S et al (2018) A survey of
methods for explaining black box models. ACM Comput Surv
## (CSUR) 51(5):1–42
-  Hati AS et al (2022) Convolutional neural network-long short
term memory optimization for accurate prediction of airflow in
a ventilation system. Expert Syst Appl 195(116):618
-  He X, Chen W, Nie B et al (2010) Classification technique for
danger classes of coal and gas outburst in deep coal mines. Saf
## Sci 48(2):173–178
-   He Xq, Zhou C, Song Dz et al (2021) Mechanism and monitoring
and early warning technology for rockburst in coal mines. Int J
## Miner Metall Mater 28:1097–1111
-   He S, Lu Y, Li M (2022) Probabilistic risk analysis for coal mine
gas overrun based on FAHP and BN: a case study. Environ Sci
## Pollut Res 29(19):28,458-28,468
-  Hou L, Bergmann NW (2011) Induction motor fault diagnosis
using industrial wireless sensor networks and Dempster–Shafer
classifier fusion. In: IECON 2011-37th annual conference of the
IEEE industrial electronics society. IEEE, pp 2992–2997
-  Huang Y, Cheng W, Tang C et al (2015) Study of multi-agent-
based coal mine environmental monitoring system. Ecol Indic
## 51:79–86
-   Jo B, Khan RMA (2018) An internet of things system for under-
ground mine air quality pollutant prediction based on azure
machine learning. Sensors 18(4):930
-  Jung D, Choi Y (2021) Systematic review of machine learning
applications in mining: exploration, exploitation, and reclama-
tion. Minerals 11(2):148
-   Khaleghi B, Khamis A, Karray FO et al (2013) Multisensor data
fusion: a review of the state-of-the-art. Inf Fusion 14(1):28–44
-  Klein LA (2004) Sensor and data fusion? A tool for informa-
tion  assessment  and  decision  making,  vol  138.  SPIE  Press,
## Bellingham
-   Kowalski-Trakofler  K,  Alexander  D,  Brnich  M  et  al  (2009)
Underground coal mining disasters and fatalities-United States,
1900–2006. MMWR Weekly 57(51–52):1379–1382
-  Krog R, Schatzel S, Garcia F et al (2006) Predicting methane
emissions from longer longwall faces by analysis of emission
contributors. In: Mutmanski JM, Ramani RV (eds) Proceedings
of the 11th US/North American mine ventilation symposium.
Balkema Publishers, Leiden, pp 383–392
-   Kumar D (2016) Application of modern tools and techniques for
mine safety and disaster management. J Inst Eng (India) Ser D
## 97:77–85
- Kumar A, Kingson T, Verma R et al (2013) Application of gas
monitoring sensors in underground coal mines and hazardous
areas. Int J Comput Technol Electron Eng 3(3):9–23
-  Kumari K, Dey P, Kumar C et al (2021) UMAP and LSTM
based  fire  status  and  explosibility  prediction  for  sealed-off
area in underground coal mine. Process Saf Environ Protect
## 146:837–852
-   Lei C, Deng J, Cao K et al (2019) A comparison of random forest
and support vector machine approaches to predict coal spontane-
ous combustion in gob. Fuel 239:297–311
-   Li Y, Mao S, Xie H et al (2011) Technique of dynamically warn-
ing of coalmine gas outburst based on Bayesian network. In:
2011 19th international conference on geoinformatics. IEEE, pp
## 1–4
-   Li D, Li S, You M (2019) Research on mine safety situation pre-
diction model: the case of gas risk. In: 2019 11th international
conference on wireless communications and signal processing
(WCSP). IEEE, pp 1–6
-   Li M, Wang D, Shan H (2019) Risk assessment of mine ignition
sources using fuzzy Bayesian network. Process Saf Environ Prot
## 125:297–306
-  Li M, Wang H, Wang D et al (2020) Risk assessment of gas
explosion in coal mines based on fuzzy AHP and Bayesian net-
work. Process Saf Environ Prot 135:207–218
- Li B, Wang E, Shang Z et al (2021) Deep learning approach to
coal and gas outburst recognition employing modified ae and
EMR signal from empirical mode decomposition and time-fre-
quency analysis. J Nat Gas Sci Eng 90(103):942
- Liang Y, Zhang J, Wang L et al (2019) Forecasting spontaneous
combustion of coal in underground coal mines by index gases: a
review. J Loss Prev Process Ind 57:208–222
-  Ma L, Guo R, Wu M et al (2020) Determination on the hazard
zone of spontaneous coal combustion in the adjacent gob of dif-
ferent mining stages. Process Saf Environ Protect 142:370–379
-   Mahdevari S, Shahriar K, Esfahanipour A (2014) Human health
and safety risks management in underground coal mines using
fuzzy topsis. Sci Tot Environ 488:85–99
- Mahesh B (2020) Machine learning algorithms—a review. Int J
Sci Res (IJSR) 9:381–386
- Mardonova M, Choi Y (2018) Review of wearable device tech-
nology and its applications to the mining industry. Energies
## 11(3):547
-  Maseleno A, Hasan MM (2012) Skin diseases expert system
using Dempster-Shafer theory. Int J Intell Syst Appl 4(5):38–44
-   Melin P, Castillo O (2014) A review on type-2 fuzzy logic appli-
cations in clustering, classification and pattern recognition. Appl
## Soft Comput 21:568–577
- Meng F, Fang Y, Li C (2019) Research on safety early warning
management of coal mining face based on expert system. In:
IOP conference series: materials science and engineering. IOP
Publishing, Bristol, p 062056
-   Meng X, Liu Q, Luo X et al (2019) Risk assessment of the unsafe
behaviours of humans in fatal gas explosion accidents in China’s
underground coal mines. J Clean Prod 210:970–976
- Meng X, Chang H, Wang X (2022) Methane concentration pre-
diction method based on deep learning and classical time series
analysis. Energies 15(6):2262
-   Merenda M, Porcaro C, Iero D (2020) Edge machine learning for
AI-enabled IoT devices: a review. Sensors 20(9):2533
- Moraes R, Valiati JF, Neto WPG (2013) Document-level senti-
ment classification: An empirical comparison between SVM and
ANN. Expert Syst Appl 40(2):621–633
- Muduli L, Jana PK, Mishra DP (2018) Wireless sensor network
based fire monitoring in underground coal mines: a fuzzy logic
approach. Process Saf Environ Prot 113:435–447
-  Muduli L, Mishra DP, Jana PK (2018) Application of wireless
sensor network for environmental monitoring in underground
coal mines: a systematic review. J Netw Comput Appl 106:48–67
-  Myung J (2002) Tutorial on maximum likelihood estimation. J
## Math Psychol 47(2003):90100

## 387
Review on Machine Learning-Based Underground Coal Mines Gas Hazard Identication and
## 1 3
-   Nesa N, Banerjee I (2017) IoT-based sensor data fusion for occu-
pancy sensing using Dempster-Shafer evidence theory for smart
buildings. IEEE Internet Things J 4(5):1563–1570
-  Nie W, Liu Y, Li C et al (2014) A gas monitoring and control
system in a coal and gas outburst laboratory. J Sens 2014:172016
-  Osunmakinde IO (2013) Towards safety from toxic gases in
underground mines using wireless sensor networks and ambient
intelligence. Int J Distrib Sens Netw 9(2):159273
-   Özmen İ, Aksoy E (2015) Respiratory emergencies and manage-
ment of mining accidents. Turk Thorac J 16(Suppl 1):S18
-  Prostański D (2018) Development of research work in the air-
water spraying area for reduction of methane and coal dust explo-
sion hazard as well as for dust control in the polish mining indus-
try. In: IOP conference series: materials science and engineering.
IOP Publishing, Bristol, p 012026
-   Qiu Pq, Ning Jg, Wang J et al (2021) Mitigating rock burst hazard
in deep coal mines insight from dredging concentrated stress: a
case study. Tunnell Undergr Space Technol 115(104):060
-  Qiu L, Peng Y, Song D (2022) Risk prediction of coal and gas
outburst based on abnormal gas concentration in blasting driving
face. Geofluids 2022:3917846
-  Ray SK, Khan AM, Mohalik NK et al (2022) Review of pre-
ventive and constructive measures for coal mine explosions: an
Indian perspective. Int J Min Sci Technol 32(3):471–485
-   Reddy NS, Saketh MS, Dhar S (2016) Review of sensor technol-
ogy for mine safety monitoring systems: a holistic approach. In:
2016 IEEE first international conference on control, measure-
ment and instrumentation (CMI). IEEE, pp 429–434
-  Reddy NVK, Varma GM, Visalakshi P (2021) Design of IoT
based coal mine safety system using Arduino UNO. Ann Roman
## Soc Cell Biol 25(5):5663–5670
-  Ruder S (2016) An overview of gradient descent optimization
algorithms. arXiv preprint. arXiv:1609.04747
-   Ruilin Z, Lowndes IS (2010) The application of a coupled artifi-
cial neural network and fault tree analysis model to predict coal
and gas outbursts. Int J Coal Geol 84(2):141–152
- Salehinejad H, Sankar S, Barfett J et al (2017) Recent advances
in recurrent neural networks. arXiv preprint. arXiv:1801.01078
-   Sarkar F, Adhikari P, Mangal A (2021) Development of a hybrid
type mine hazard alert system (MHAS) for inhibiting the dis-
astrous incidences due to fire hazards, water inrush and strata
failure in underground mines: an experimental trial. J Inst Eng
(India) Ser D 102(1):39–46
-   Schatzel S, Krog R, Garcia F, et al (2006) Prediction of longwall
methane emissions and the associated consequences of increas-
ing longwall face lengths: a case study in the Pittsburgh coalbed.
In: Proceedings of 11th US/North American mine ventilation
symposium, pp 375–382
-   Schatzel S, Krog R, Dougherty H (2017) Methane emissions and
airflow patterns on a longwall face: potential influences from
longwall gob permeability distributions on a bleederless longwall
panel. Trans Soc Min Metall Explor 342(1):51
-   Shahmoradi J, Talebi E, Roghanchi P et al (2020) A comprehen-
sive review of applications of drone technology in the mining
industry. Drones 4(3):34
- Shanmuganathan S (2016) Artificial neural network modelling:
an introduction. Artificial neural network modelling. Springer,
Cham, pp 1–14
-  Sharma M, Maity T (2018) Low cost low power smart helmet
for real-time remote underground mine environment monitoring.
## Wirel Pers Commun 102(1):149–162
-   Shi S, Jiang B, Meng X (2018) Assessment of gas and dust explo-
sion in coal mines by means of fuzzy fault tree analysis. Int J Min
## Sci Technol 28(6):991–998
-   Singh N, Gunjan VK, Chaudhary G et al (2022) IoT enabled hel-
met to safeguard the health of mine workers. Comput Commun
## 193:1–9
-  Stephenson TA (2000) An introduction to Bayesian network
theory and usage. Tech. Rep, IDIAP
-   Szlazak N, Obracaj D, Swolkien J (2020) Enhancing safety in the
polish high-methane coal mines: an overview. Min Metall Explor
## 37(2):567–579
-  Tong X, Fang W, Yuan S et al (2018) Application of Bayesian
approach to the assessment of mine gas explosion. J Loss Prev
## Process Ind 54:238–245
-  Tripathy DP, Ala CK (2018) Identification of safety hazards in
Indian underground coal mines. J Sustain Min 17(4):175–183
-  Tripathy D, Parida S, Khandu L (2021) Safety risk assessment
and risk prediction in underground coal mines using machine
learning techniques. J Inst Eng (India) Ser D 102(2):495–504
- Tutak M, Brodny J (2019) Forecasting methane emissions from
hard coal mines including the methane drainage process. Ener-
gies 12(20):3840
- Tutak M, Brodny J (2019) Predicting methane concentration in
longwall regions using artificial neural networks. Int J Environ
## Res Public Health 16(8):1406
-  Ullah MF, Alamri AM, Mehmood K et al (2018) Coal mining
trends, approaches, and safety hazards: a brief review. Arabian
Journal of Geosciences 11(21):1–16
-   Uusitalo  L  (2007)  Advantages  and  challenges  of  bayesian
networks in environmental modelling. Ecological modelling
## 203(3–4):312–318
- Verma S, Chaudhari S (2016) Highlights from the literature on
risk assessment techniques adopted in the mining industry: a
review of past contributions, recent developments and future
scope. International Journal of Mining Science and Technology
## 26(4):691–702
-  Wang D, Sui W, Ranville JF (2022) Hazard identification and
risk  assessment  of  groundwater  inrush  from  a  coal  mine:  a
review. Bulletin of Engineering Geology and the Environment
## 81(10):421
-   Wu J, Yuan S, Zhang C et al (2018) Numerical estimation of gas
release and dispersion in coal mine using ensemble kalman filter.
Journal of Loss Prevention in the Process Industries 56:57–67
-   Xiao H, Tian Y (2011) Prediction of mine coal layer spontaneous
combustion danger based on genetic algorithm and bp neural
networks. Procedia Engineering 26:139–146
-   Xie X, Fu G, Xue Y et al (2019) Risk prediction and factors risk
analysis based on ifoa-grnn and apriori algorithms: Application
of artificial intelligence in accident prevention. Process Safety
and Environmental Protection 122:169–184
- Xu L, Sun L, Wang D et al (2020) Study on intelligent percep-
tion Internet of Things apply in mine safety. J Phys Conf Ser
## 1646:012146
-   Xu N, Wang X, Meng X et al (2022) Gas concentration prediction
based on iwoa-lstm-ceemdan residual correction model. Sensors
## 22(12):4412
-   Yang L, Liu C (2013) Prediction of gas emission based on partial
correlation analysis and SVR. Appl Math Inf Sci 7(5):1671
- Zhang C, Fu Y, Deng F et al (2018) Methane gas density moni-
toring and predicting based on rfid sensor tag and cnn algorithm.
## Electronics 7(5):69
- Zhang J, Ai Z, Guo L et al (2021) Research of synergy warning
system for gas outburst based on entropy-weight Bayesian. Int J
## Comput Intell Syst 14(1):376–385
- Zhao Xh, Gang W, Zhao KK et al (2009) On-line least squares
support vector machine algorithm in gas prediction. Min Sci
Technol (China) 19(2):194–198

## 388 M. Sharma, T. Maity
## 1 3
-   Ziętek B, Banasiewicz A, Zimroz R et al (2020) A portable envi-
ronmental data-monitoring system for air hazard evaluation in
deep underground mines. Energies 13(23):6331
Publisher's  Note  Springer  Nature  remains  neutral  with  regard  to
jurisdictional claims in published maps and institutional affiliations.
Springer  Nature  or  its  licensor  (e.g.  a  society  or  other  partner)  holds
exclusive rights to this article under a publishing agreement with the
author(s) or other rightsholder(s); author self-archiving of the accepted
manuscript  version  of  this  article  is  solely  governed  by  the  terms  of
such publishing agreement and applicable law.