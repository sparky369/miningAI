

## 1
ol.:ȋͬͭͮͯͰͱͲͳʹ͵Ȍ
## Scientific Reports |        (2024) 14:13795
## |
https://doi.org/10.1038/s41598-024-64181-7
www.nature.com/scientificreports
Research on coal mine longwall
face gas state analysis and safety
warning strategy based
on multi‑sensor forecasting models
## Haoqian     Chang
## 1*
## , Xiangrui Meng
## 1
## , Xiangqian Wang
## 1,2*
## & Zuxiang Hu
## 1,2
Intelligent computing is transforming safety inspection methods and response strategies in coal
mines. Due to the significant safety hazards associated with mining excavation, this study proposes a
multi‑source data based predictive model for assessing gas risk and implementing countermeasures.
By examining the patterns of gas dispersion at the longwall face, utilizing both temporal and spatial
correlation, a predictive model is crafted that incorporates safety thresholds for gas concentrations,
four‑level early warning method and response strategy are devised by integrating weighted predictive
confidence with these correlations. Initially tested using a public dataset from Poland, this method
was later verified in coal mine in China. This paper discusses the validity and correlation of multi‑source
monitoring data in temporal and spatial correlation and proposes a risk warning mechanism based on
it, which can be applied not only for safety warning but also for regulatory management.
Keywords  Mining safety, Mining management engineering, Time series analysis, Warning strategy
Gas concentration is a pivotal parameter in assessing excavation safety within coal mines, almost all mining
operations are associated with gas concentration, and it is also the primary factor to coal mines  accidents
## 1
## .
Predictions and monitoring of large amounts of gas data are  feasible
## 2,3
, but the important bridging between
abstract complex physical systems and their users’ needs is missing. That is, there is a need for the conversion
of these predictions to a level explainable by metrics that reflect the true working scenarios and importantly, a
decision-making level by human  users
## 4
## .
The formidable operational environment of coal longwall faces (the place where coal is cut from the coal seam
either manually or mechanically), characterised by semi-enclosed tunnels, a plethora of sensors, diverse equip-
ment, extreme temperature and pressure  conditions
## 5
, and the ever-present risk of gas-related  accidents
## 6
, adds
substantial complexity to the assessment of overall safety. Furthermore, the complexity of geological  conditions
## 7

and structures across different longwall faces complicates the assessment of the general safety status.
Due to the rapid development of Industry 4.0
## 8
, traditional manual monitoring and management methods
in coal longwall face are not  sufficient
## 9
. Although accidents and megaton mortality rates in China’s coal mines
have shown a downward  trend
## 10,11
, the overall alarm rate remains high (see Fig. 1). Where Fig. 1a shows the
total number of accidents and casualties in China’s coal mines from 2008 to 2022, as well as the annual megaton
coal mining mortality rate. However, whilst accidents are most distressing, it is important to note also alarms
that have not led to accidents (yet). Figure 1b, displays the number of alarms (in the form of percentage) related
to gas in underground coal mines in each province of China from 2020 to 2022. Investigating these warnings
remains labor-intensive; fortunately, they have not escalated into serious accidents. However, it is crucial that
they are accurately categorized and systematically reviewed to prevent future incidents.
Hence, there is a growing demand for advanced early warning strategies and countermeasures to ensure coal
mining face safety. The primary research areas related to this include: gas concentration prediction through data
analysis
## 13
, accident prevention and early warnings, especially for incidents like gas explosions and coal and gas
herniations
## 14
, and digital twin  modelling
## 15
, whom focusing on the coordination of coal mining  equipment
## 16
## .
Other areas include safety monitoring and risk warning related to gas  concentration
## 17
, roof pressure  prediction
## 18
## ,
multifactor coupling and decoupling of the coal mining  face
## 19
, etc. Despite the diversity of these studies, the
## OPEN
## 1
School of Economics and Management, Anhui University of Science & Technology, Huainan 232000, China.
## 2
## These
authors contributed equally: Xiangqian Wang and Zuxiang Hu.
## *
email: haoqian.chang@durham.ac.uk; xiqwang@
aust.edu.cn

## 2
## Vol:.(1234567890)
## Scientific Reports
## |        (2024) 14:13795  |
https://doi.org/10.1038/s41598-024-64181-7
www.nature.com/scientificreports/
analysis based on gas concentration remains the predominant research direction. This is because it offers the most
direct  insight
## 1,9
into the underground environment and serves as the primary criterion for warning mechanisms.
The study of early safety warning  strategies
## 20
for coal mine longwall faces is an important part of promoting
coal mine safety. Traditionally, mine safety management uses production thresholds to trigger alarms at certain
concentrations. by classifying coal mines into high, medium and low types for underground gas emissions and
coal production. Current  applications
## 21
primarily focus on safety and production status display, as well as warn-
ings for exceeding predefined limits. Based on the influencing factors related to gas concentration as variables.
Ding et al.
## 22
proposed a gas concentration prediction method based on partial least squares regression. However,
as digitalization and automation advance, there is an increasing need for accurate and early risk warnings but has
several challenges. First, monitoring data is the result of a combination of events, including gas  absorption
## 23
and
decomposition at the coal wall, coal mining operations, and coal transportation. Moreover, as the longwall face
expands, the pattern of this combination will also change. Secondly, there are multiple sensors at various locations
collectively monitoring the status of the gas concentration throughout the longwall face. This means that the
values from these sensors reflect the direction of movement of the gas in the longwall face and the trend of the
concentration, which contains both geographical and time lag information. However, this type of information is
difficult to interpret directly by forecasting. A coal mine longwall face presents a semi-enclosed  environment
## 24
## ,
characterised by high temperatures and pressures, exhaust gases, humidity and darkness, among other com-
plexities. High-precision sensors, such as methane and carbon monoxide, operating in this environment are
extremely prone to malfunction, damages by flying stones, as well as malicious manmade masking—resulting
in nulls, abnormal  values
## 25,26
. This raises the challenge of how to handle and recognise these anomalies, which
is important for the creation and evaluation of the overall safety warning strategy.
Gas concentration as highly time-dependent data, make deep learning based intelligent  algorithms
## 27,28
dem-
onstrated their capability to process and predict large volumes of multi-source data in various aspects of coal
mine safety  management
## 9
, gas  concentration
## 29
. But simply relying on conventional metrics, such as accuracy, or
learning test loss, to define gas trends, is insufficient, as these losses do not reflect the spatial correlation of gas
concentrations, i.e., the sorption effect of the gas as it drifts from position A to position B in the longwall face,
nor do they explain the effect of time lag on the prediction results. Ultimately, they do not provide managers
with the intuitive risk rating they  need
## 30
## .
To address these challenges and to evaluate the real-time working conditions of the coal mine longwall face,
early safety warning strategies are proposed and adopted in underground coal mine safety  management
## 31,32
## .
Current methodologies predominantly depend on manual observation and heuristic approaches. In contrast, the
implementation of big data models utilizing deep  learning
## 33
allows for comprehensive monitoring and evalua-
tion of the entire work environment. This advancement not only enhances managerial decision-making but also
mitigates human error. To development of an interpretable safety warning strategy relies on two main aspects: (i)
Multivariate-based time-series prediction of a large amount of gas monitoring data to decipher high-dimensional
coupling relationships; (ii) identification and analysis of dynamic multi-source data variation patterns across
both time and space. Thus, we propose a safety warning strategy that utilizes multi-sensor monitoring data,
incorporating it into a four level risk assessment system with an evolution mechanism. The strategy is validated
on a publicly available dataset from Poland and a coal mine in Anhui, China.
## Methodologies
Coal mine data description
The experimental data for this study comprises two main sources: a publicly available dataset from coal mine in
## Poland
## 26,34
and the data we collected from a coal mine in China;the dataset from the coal mine in Poland was
obtained from the Upper Silesian Coal Basin, consisting of time-sensitive readings from March 2, 2014, to June
16, 2014, with a total of 9,199,930 data instances, each detailed with timestamps and measurements. Meanwhile,
the dataset from the coal mine in China was acquired using gas sensors in the W3211 working face at Qianyingzi
Figure 1.    (a) Recent trends in China’s coal mine accident rates and mortality per million  tons
## 12
. (b) Key causes
of gas-related underground sensor alarms.

## 3
## Vol.:(0123456789)
## Scientific Reports
## |        (2024) 14:13795  |
https://doi.org/10.1038/s41598-024-64181-7
www.nature.com/scientificreports/
Mine, Suzhou City, Anhui Province, during the period from May 1, 2021, to July 20, 2021, accumulating a total of
3,407,328 data points. Both datasets have been preprocessed, with timestamps standardized to the minute level.
An overview of the main gas sensors for the two locations can be seen in Fig. 2. The upper corner represents a
critical gas monitoring point on the coal mining face. This location is significant due to intense activities such as
digging, blasting, coal dropping, and transportation. Furthermore, this is an area bustling with employees and
equipment, including coal miners, hydraulic supports, and scraper conveyors, among others.
The configuration of the longwall face support in Polish coal mines bears a resemblance to that utilized in
Chinese coal mines, as shown in Fig. 2. Both exhibit a U shaped layout, facilitating airflow from beneath and
directing it through the upper corners. This similarity warrants a comparative analysis of the two mining opera-
tions. However, the ventilation structure of a coal mining face is critical to the safety of the mine as it directly
affects the control of gas and dust and the working environment of the miners. We concurrently analyse the
spatio-temporal relationships of MM264 (upper corner), MM264, and MM256 in the Polish coal mine, and T0
(upper corner), T1, and T2 in the Chinese coal mine. To avoid redundancy and prevent confusion in our descrip-
tions, we will hereafter refer to the longwall face using the nomenclature of the Chinese coal mining industry.
From the data presented in Table 1, we observe consistent patterns across both datasets. Both datasets utilise
the “threshold risk judgement” methodology and are organised in a time-series format. Intrinsically, the datasets
depict a spatial pattern over time. These datasets are segmented into distinct levels, according to the exceeded
concentration value thresholds. Specific details regarding the preprocessing of these datasets are worth mention-
ing. Both datasets undergo several preprocessing steps, including padding and removal of invalid values. Addi-
tionally, due to the uneven data collection frequencies of the sensors, it is essential to synchronize the data across
the same time period for consistency, in this study, we averaged the data sampled over a one-minute period.
In contrast, the data from the Poland mine remains in its raw form, suggesting a need for preprocessing before
undertaking any experimental analyses. The coal mine longwall face functions as an integrated environment. It
encompasses a multitude of equipment sources, diverse monitoring data, and unpredictable coal rock conditions.
Figure 2.    Comparison of coal mine gas sensor locations in two coal faces in China and Poland (sensors start
with T in China and MM in Poland).
Table 1.   Sensor data from coal mines in Poland and China.
PointSensorAlarm (%)Warning (%)MinMaxMeanStd.devMedianLengths
Coal mine in Poland
## MM263
## ≥1.5≥1.0
## − 2.030.00.2480.1970.29,199,931
## MM264
## ≥1.5≥1.0
## − 2.040.00.3270.2060.39,199,931
## MM256
## ≥1.5≥1.0
## 0.030.00.4330.2040.49,199,931
Coal mine in China
## T0
## ≥1.5≥1.0
## 0.02.00.2540.0980.267,135,789
## T1
## ≥1.5≥1.0
## 0.02.00.2440.0910.247,135,789
## T2
## ≥1.5≥1.0
## 0.02.00.2730.0930.287,135,789

## 4
## Vol:.(1234567890)
## Scientific Reports
## |        (2024) 14:13795  |
https://doi.org/10.1038/s41598-024-64181-7
www.nature.com/scientificreports/
Developing a safety warning strategy based on a multi-sensor model entails understanding intricate coupling
relationships concealed amidst vast amounts of monitoring data.
In China, coal mine operations generally run 24 h. a day, the intense coal mining operations primarily occur
during daytime, with the remaining intervals designated for overhaul operations. During the mid-shift, which is
the primary mining period, the gas concentration at the three locations spikes significantly, whereas it diminishes
during the other two overhaul shifts, as depicted in Fig. 3. In Fig. 3a, the mining work shift schedule is plotted
against the length of the longwall face (measured in meters) and the associated shift timings.
Four main shifts are observed: Morning, Midday, Night. Figure 3b illustrates the variations in gas concentra-
tions as monitored by three distinct gas sensors: T0, T1, and T2, during the same shift times. As shown in Fig. 3,
the horizontal axis represents time, segmented according to the primary work shifts— Morning, Midday, and
Night. The vertical axis measures the levels of gas concentration. The data illustrates substantial diurnal fluctua-
tions in gas concentration, characterized by distinct peaks and troughs. These peaks often correlate with periods
of intense mining activity or specific processes within the mine, indicating a cyclical pattern to the gas emissions.
Notably, there are significant increases in gas levels during the early hours of both the Morning and Midday
shifts. A comprehensive analysis of both spatial and temporal variations enables a deeper understanding of the
gas movement and diffusion patterns within the mine’s tunnels, encompassing both time and space dimensions.
Temporal and spatial correlation
In coal mine longwall face, gas sensors are primarily categorised into different types, T0 (upper corner), which
is no more than 800 mm from the roof plate, is the closest sensor to the coal mining position; T1: installed in
the return airflow, within 10 m from the coal wall of the longwall face; T2: installed in the longwall face from
the wind lane outlet to within 10–15 m, the distance between sensors is not explicit in the Polish dataset, so the
same parameters are used. Each sensor gathers data, organised and stored in chronological sequences. These
sequences reflect the state of coal mining operations and the corresponding conditions of the coal wall at differ-
ent times. This can be expressed as
## Sensor
## 0
## ={x
## 1
## ,x
## 2
## ,...,x
i
## ,...}
,  where
x
i
denotes an observation at time i with a
total length of points in time observed.
Cross-covariance functions for spatio-temporal (CCFST) multi-sensor data: Considering that gas in the
longwall face drifts from sensor T0 to T1 due to wind flow, and as the workface continues to be excavated, the
entire environment, as well as the location of the sensors changes. During the calculation process, time-space
lagged values are generated, and a simple covariance calculation or Pearson’s correlation between the sensors
would ignore potentially important patterns in the data. This spatial lag is crucial to understand how changes in
gas concentration at one sensor location might influence or correlate with changes at another sensor location.
The time lag helps in comprehending temporal correlations; it elucidates how fluctuations at a given moment
might influence or correlate with subsequent changes, either at the same sensor or another.
The cross-covariance function for spatio-temporal data (CCFST) provides a measure of linear association
between two time series (from different spatial locations) at different time points. It aids in deciphering how
one sensor’s output fluctuates in relation to another’s across various spatial points and over time. Given sets of
spatio-temporal sensor
## S
## 1
## (s,t)
and
## S
## 2
## (s
## ′
## ,t
## ′
## )
, where s and t represent spatial location and time, respectively the
CCFST can be define as Eq. (1):
where
τ
and
## 
are temporal and spatial lag, also denoted as
lag
temporal
## (τ)
and
lag
spatial
## ()
. E denotes the expecta-
tion.
μ
## 1
## (s,t)
and
μ
## 2
## (s+τ,t+)
are the means of the processes at their respective locations and times.
Covariance measures the relationship between two datasets. If the datasets tend to increase and decrease
together, the covariance is positive. If one set tends to increase when the other decreases, the covariance is
## (1)
## C
## S
## 1
## S
## 2
(τ,)=E[(S
## 1
## (s,t)−μ
## 1
(s,t))(S
## 2
## (s+τ,t+)−μ
## 2
## (s+τ,t+))],
Figure 3.    Coal mine operation roster in China and variation of gas concentration.

## 5
## Vol.:(0123456789)
## Scientific Reports
## |        (2024) 14:13795  |
https://doi.org/10.1038/s41598-024-64181-7
www.nature.com/scientificreports/
negative. Each sensor, such as T0, T1, and T2, produces a time series of data over a consistent period. Even though
each time series represents measurements from a different spatial location, the readings across these sensors at
the same time can be viewed as a multi-dimensional data point. In our multi-sensor setup, the covariance matrix
provides pairwise covariances for each sensor pair. The diagonal elements of the covariance matrix represent
the variance of each sensor’s data, and the off-diagonal elements represent the covariance between the pairs of
sensors. This allows us to analyse measurements from all the sensors.
Prediction models
In the following the prediction models that have been applied in this work are described, together with the
reason for using them.
Long short-term Memory (LSTM)
## 35
networks have been developed to mitigate the issue of gradient vanishing
encountered by standard Recurrent Neural Networks (RNNs) when processing long sequences. LSTM is set as
the baseline model because of its mature architecture and its wide range of applications to facilitate comparison
with more complex models. Incorporating the gate concept, LSTM comprise a forgetgate:
f
t
,  an inputgate:
i
t
and
an outputgate:
o
t
, each contributing to the model’s ability to retain or discard information through sequential
data processing. The gates can be expressed as Eq. (2):
where
σ
is the sigmoid function of the forget gate
f
t
## . W
f
and b
f
are the weights and biases,
h
t−1
and
x
t
are the
hidden state of the previous time step and the input of the current time step.
where
i
t
is the input gate,
## ̃
## C
t
is the candidate unit status, and unit status update via Eq. (5).
The output gate
o
t
determines which information will be passed to the next loop:
where
h
t
is the hidden state of the current time step, tanh() indicates the hyperbolic tangent function,
## W
o
and
b
o
are the weights and biases of
o
t
## .
Self-attention  mechanism
## 36,37
based models have become a cornerstone in NLP tasks, encompassing machine
translation, text summarisation, and question-answering systems, among other sequence-based applications.
The Transformer model stands out for its proficiency in handling long sequences, discerning intricate depend-
encies, and facilitating a high degree of parallel computation. The self-attention mechanism operates as Eq. (8):
where
d
k
is the dimension of the key vector used to scale the dot product and Q, K, V are Query, Key and Value
respectively. The multi-head attention mechanism as shown in Eqs. (9) and (10) enables the concurrent capture
of various contextual relationships within a sequence. Coupled with positional encoding, this approach preserves
the order of elements, ensuring that the model remains sensitive to the sequence’s syntactic structure.
Evaluation metrics
To assess the predictive accuracy of various time series forecasting techniques, we utilise four distinct popular
metrics. These include the mean squared error (MSE), root mean squared error (RMSE), mean absolute error
(MAE), and mean absolute percentage error (MAPE). The MSE is a measure that captures the average squared
differences between predicted and actual values. And RMSE, which is the square root of MSE, and MAE are
absolute measures that quantify the prediction errors in their original scale. Conversely, MAPE offers a relative
measure, providing an error percentage. All the metrics can be defined as:
## (2)
f
t
=σ(W
f
## ·[h
t−1
## ,x
t
## ]+b
f
## ),
## (3)
i
t
=σ(W
i
## ·[h
t−1
## ,x
t
## ]+b
i
## )
## (4)
## ̃
## C
t
=tanh(W
## C
## ·[h
t−1
## ,x
t
## ]+b
## C
## ),
## (5)
## C
t
## =f
t
## C
t−1
## +i
t
## ̃
## C
t
## .
## (6)
o
t
=σ(W
o
## ·[h
t−1
## ,x
t
## ]+b
o
## )
## (7)
h
t
## =o
t
tanh(C
t
## ),
## (8)
Attention(Q,K,V)=softmax(
## QK
## T
## √
d
k
## )V,
## (9)
MultiHead(Q,K,V)=Concat(head
## 1
## ,...,head
h
## )W
## O
## ,
## (10)
head
i
=Attention(QW
## Q
i
## ,KW
## K
i
## ,VW
## V
i
## ).
## (11)
## MSE=
## 1
## N
## N
## ∑
i=1
## (y
i
## −ˆy
i
## )
## 2
## ,

## 6
## Vol:.(1234567890)
## Scientific Reports
## |        (2024) 14:13795  |
https://doi.org/10.1038/s41598-024-64181-7
www.nature.com/scientificreports/
where the
y
i
is the actual value, and
## ˆy
i
is predicted value.
Safety warning strategy based on multi‑sensor information
Conceptual architecture
To mitigate safety risks in the coal mining face and prevent emergency accidents, especially during mining
operations, we propose a risk level warning system based on spatial–temporal correlations and multivariate time
prediction models. This system encompasses risk determination, evolution mechanisms, and the implementa-
tion of corresponding safety measures. As depicted in Fig. 4, the multi-source sensor data prediction and weight
calculation involve a sliding window approach which demonstrates a sliding-window methodology applied to
data collected from multiple sensors, labelled from Sensor1 to Sensorn. This method involves continual data
capture in temporal increments, processing the most recent data points while sliding past the older ones. Each
sensor captures data at regular intervals, ensuring real-time monitoring.
Each sensor records data in temporal increments: the current data is labelled as t, while the two previous
data points are labelled
t−1
and
t−2
. Post the sliding-window processing, the data undergoes a correlation
process with a time lag, essentially comparing a reading’s current value with its historical values. Understanding
the temporal relationships of gas concentrations is crucial. This correlation provides insights into the behaviour
and flow of the gas within the tunnel.
By sampling the multi-sensor monitoring values from Sensor1 to Sensor n through sliding windows and
compute the correlation for the corresponding length time periods, calculating the correlation of a time series by
segmentation can effectively identify individual patterns hidden in the overall correlation. At the same time, by
controlling the size of the time window, not only the amount of computation can be alleviated, but also the time
lag of the computation can be controlled, this time lag is particularly important in longwall face monitoring data,
because most of the longwall faces in coal mines work according to a fixed scheduling pattern, i.e., two shifts and
one inspection, as shown in the Fig. 3. The correlation matrix which contains the relationship between different
data sources, and predictably, if one data source fails or changes drastically, the correlation matrix correspond-
ing to the other data sources will also change, this provides constant weight CCFST for the risk discrimination
mechanism, and variable weight which is losses from predictive models trained and predicted for each data
source separately, by calculating the share of other data sources in this prediction (Fig. 5).
Model architecture
Model loss influences early risk warning method which derived from a large number of calculations can be
classified into three thresholds
α,β
and
γ
, are based on a large number of model predictions. When assessing
the status of a single sensor, three primary states: Red, Ye l l o w, and Green, are determined by correlating the cur-
rent model loss with the score from the most recently assessed sensor. The specific thresholds
α,β
and
γ
can be
adjusted based on the chosen model and metrics, allowing for tailored application. The comprehensive structure
of this approach is illustrated in Fig. 5.
## (12)
## RMSE=
## √
## √
## √
## √
## 1
## N
## N
## ∑
i=1
## (y
i
## −ˆy
i
## )
## 2
## ,
## (13)
## MAE=
## 1
## N
## N
## ∑
i=1
## |y
i
## −ˆy
i
## |,
## (14)
## MAPE=
## 1
## N
## N
## ∑
i=1
## |y
i
## −ˆy
i
## |
y
i
## ×100%,
Figure 4.    Multi-sensor data prediction and weight calculation.

## 7
## Vol.:(0123456789)
## Scientific Reports
## |        (2024) 14:13795  |
https://doi.org/10.1038/s41598-024-64181-7
www.nature.com/scientificreports/
For each level there is a predicted value and ground truth. Loss thresholds are defined by calculating the loss
between the predicted and actual values. A loss judgement can be defined as Eq. (15):
Each threshold has a corresponding weight, i.e., a prediction weight
ω
as well as a correlation weight
γ
## .  For
example, when both
ω
and
γ
rise and exceed the maximum threshold loss, defined as Red state, and when
ω

rises and
γ
falls, defined as Green state. By using the sensors at different locations for state judgement, we can
get a weighted risk judgement method as shown in Fig. 6 where the four risk levels are determined by basic state
and their corresponding weights. Each level is indicated by a specific basic state, whereas multiple factors can
collectively signify any of the states. This framework allows for a nuanced interpretation of risks based on the
interplay and intensity of different factors.
## (15)
f(BasicState)=
## {
## Redif
## |
ω−(1−l)
## |
## >α
## Yellowifβ≤
## |
ω−(1−l)
## |
## ≤α
## Greenifγ≤
## |
ω−(1−l)
## |
## <β.
Figure 5.    Weighted average based multi-sensor prediction models.
Figure 6.    Four-level risk judgement and evolutionary mechanisms.

## 8
## Vol:.(1234567890)
## Scientific Reports
## |        (2024) 14:13795  |
https://doi.org/10.1038/s41598-024-64181-7
www.nature.com/scientificreports/
Risk evolution mechanisms and response plan
We propose a four-level warning determination and multi-state representation as shown in Fig. 7. Combin-
ing multi-sensor data, which may represent a variety of sensor readings or states, with a series of weights and
constants will result in the determination of four risk levels, each associated with a colour: red, yellow, blue and
green. In combining the multi-state data and weights constants, a final risk judgement is derived, represented by a
gradient from green to red, with increasing risk from left to right. By demonstrates that each risk class comprises
a weighted combination of three distinct risk factors, which are made up of a spatio-temporal correlation matrix
and modelled losses, where a structured multi-source sensor-based gas risk decision-making system around
operational adjustments in a mining environment based on different states of warning conditions. At the top,
’warning conditions’ represent different levels of warning or risk, and each colour may indicate a different warn-
ing level, from low risk (green) to high risk (red). In relation to the actual mining process, actions are adjusted
according to the warning status. And the safety response strategy is determined by the current working state
together with the warning state, represented as Eq. (16):
The safety strategy implemented within the mining operation is structured into three distinct parts, each
designed to address specific aspects of the operational safety continuum. Firstly, the Excavation Unit is tasked
with managing the core mining processes. Depending on the severity of the safety alerts received, this unit
has the capability to adjust the coal discharge rate to mitigate risks effectively. Secondly, the Ventilation Unit is
crucial for maintaining optimal air quality and gas concentrations within the mine. This unit’s responsibilities
include actions such as increasing ventilation rates or adjusting the operational speed of the shearer to ensure
a safe working environment. Lastly, the Supervision Unit acts as the oversight mechanism. It is empowered to
implement robust safety measures, which may include halting operations or shutting down electric devices that
could pose hazards under critical conditions.
The operational flowchart delineates a hierarchy of responses. These responses are designed to escalate from
routine operational adjustments to more intensive, safety-focused interventions. This escalation is directly cor-
related with the progression from less severe to more severe warning states, ensuring a dynamic and responsive
safety management system. Actions evolve from regular operational adjustments to intensive, safety-centric
interventions as one transitions from the least to the most severe warning state.
Experiments and results
Spatio‑temporal correlation of different coal mines
To analyze the spatio-temporal correlation within the datasets, we employed a sliding window technique with
a window size of 480, equivalent to 8 h of operational activity, applied consistently across all datasets. The com-
puted results are illustrated in Fig. 8a for Chinese coal mines and Fig. 8b for Polish coal mines. Subsequently,
the data were normalized to simplify the interpretation, encompassing a total of five thousand sliding windows.
The Cross-correlation function for spatio-temporal data (CCFTS) values indicate the degree of interaction
between two points in the dataset. While CCFTS value approaching 1 signifies a strong correlation, indicating
that the two points move in a highly synchronous manner. This strong correlation is evident in the consistent
trends observed in the data from both Chinese and Polish coal mines throughout the time series. The simulta-
neous rise and fall in these values across the datasets indicate a persistent underlying pattern, suggesting that
similar operational or environmental factors influence both mining locations.
## (16)
## Action
unit
=f(WarningsState,CurrentOperationalState).
Figure 7.    Workflow of the response plan.

## 9
## Vol.:(0123456789)
## Scientific Reports
## |        (2024) 14:13795  |
https://doi.org/10.1038/s41598-024-64181-7
www.nature.com/scientificreports/
Model prediction results and risk level determination
We implemented three distinct models to analyze the multivariate time series data across all datasets: LSTM
(Long Short-Term Memory)
## 35
served as the baseline, with  Transformer
## 36
and  Autoformer
## 37
to do multivari-
ate time series prediction, where the position of the upper corner is the predicted value and the others are
used as eigenvalues. To verify the effect of different sliding window sizes on the prediction results, we selected
[24,48,96,168] sizes for the verification, and this window selection is borrowed from the idea of Autoformer
model. At the same time we recorded all the model losses, where the bolded text is the minimum loss, see Table 2.
The prediction results for Chinese and Polish coal mines are shown in Figs. 9a–c and 10a–c, respectively. The
LSTM model, used here as a baseline, exhibits suboptimal performance in handling multivariate prediction tasks.
In contrast, the Autoformer model ranks second, while the Transformer model demonstrates the most robust
performance in this scenario. For instance, the LSTM model underperforms compared to the Transformer, par-
ticularly in predicting outliers as illustrated in Fig. 9a,c, and also has some challenges with partially intractable.
The fitting effect of the model is very important for the determination of the risk level of the coal mining face,
in Figs. 9d–f and 10d–f the results of the risk level of the Chinese coal mines and the Polish coal mines are shown,
respectively, and we opted to display the warning results over a span of 2000 sliding windows, and the size of each
Figure 8.    Spatio-temporal correlation between Chinese and Polish coal mines.
Table 2.   Comparison of methods on different metrics for coal mines in China and Poland. Significant values
are in bold.
MethodsMetrics
## LSTM
## 35
## Transformer
## 36
## Autoformer
## 37
## MSEMAERMSEMAPEMSEMAERMSEMAPEMSEMAERMSEMAPE
Coal mine in China
## 240.010.170.240.940.140.160.200.920.140.150.210.78
## 480.010.260.311.490.010.200.251.100.010.180.240.96
## 960.030.450.532.720.110.140.200.720.010.190.260.99
## 1680.040.570.653.560.170.170.220.940.010.190.251.01
Coal mine in Poland
## 240.431.822.074.240.110.751.071.560.020.270.460.61
## 480.221.181.482.620.110.761.051.600.020.310.490.71
## 960.191.021.392.130.140.861.191.840.030.380.550.88
## 1680.401.772.014.090.160.931.251.970.030.420.591.00

## 10
## Vol:.(1234567890)
## Scientific Reports
## |        (2024) 14:13795  |
https://doi.org/10.1038/s41598-024-64181-7
www.nature.com/scientificreports/
window is the same as that in the value of the CCFTS. By predicting the data in each sliding window separately
and calculating the value of CCFTS, finally the risk rank is obtained by weighted average. It is interesting to
note that as the fit of the model improves, the risk level judged to be red is gradually decreasing, while the risk
level in green is gradually increasing, as demonstrated in Fig. 9d–f. This may be due to the fact that the model
is a poor predictor and gets a large loss, this loss exceeds the loss threshold while at this time the value of the
Figure 9.    Results of different model predictions and risk level judgements for coal mines in China.
Figure 10.    Results of different model predictions and risk level judgements for coal mines in Poland.

## 11
## Vol.:(0123456789)
## Scientific Reports
## |        (2024) 14:13795  |
https://doi.org/10.1038/s41598-024-64181-7
www.nature.com/scientificreports/
CCFTS, which is the distance between the sensors, remains constant, thus ending up with a higher risk rating.
As the accuracy of the model improves, the loss decreases and the majority of the risk level is judged to be green.
## Discussions
Despite evidence of similar spatial and temporal correlations and model generalization across different mines,
choosing the appropriate parameters, such as the size of the time window, becomes crucial. Factors like under-
ground wind speed and the structure of the coal mining face are essential in determining more precise time lags
for the results. Furthermore, models based on time series prediction significantly influence the risk rating out-
comes, as evidenced by the data shown in Figs. 9 and 10. Challenges persist, particularly as patterns in industrial
data evolve over time, such as coal mining and tunneling, the relocation of sensors as the excavation progresses
poses additional complexities. Additionally, validating the timeliness of the data remains a critical area for future
research. Considering the opaque nature of deep learning models, future studies focusing on interpretable AI
may offer a more promising direction, aiming to provide clearer insights into the decision-making processes of
these models.
## Conclusion
Intelligent computing is transforming coal mine safety through advanced gas risk assessments and enhanced
countermeasure planning. This study introduces a predictive model that utilizes multi-source data to assess gas
risk levels effectively, refining responses by examining gas drift patterns in longwall mining using temporal and
spatial correlations. Supported by a four-tier early warning system, the model integrates weighted predictive
confidence with extensive data analysis. Initially tested using a public dataset in Poland and later validated in a
Chinese coal mine, the method has demonstrated some effectiveness in real-world scenarios. This underscores
the value of multi-source data in enhancing correlation analyses and developing a robust risk warning mecha-
nism that improves safety and regulatory management within the mining industry. Although current results are
promising, the complexity and variability of underground environments call for extensive future field testing.
Pursuing deep learning research that includes more variables, or achieving comprehensive environmental aware-
ness across the entire working face, remains an exciting future research direction.
Data availability
The data used in this paper are available on request from the corresponding author.
## Received: 15 March 2024; Accepted: 5 June 2024
## References
-    Lei, Y., Cheng, Y., Wang, L., Ren, T. & Tu, Q. Mechanisms of coal and gas outburst experiments: Implications for the energy principle
of natural outbursts. Rock Mech. Rock Eng. 56, 363–377 (2023).
- Guo, Z. et al. Prediction of coalbed methane production based on deep learning. Energy 230, 120847 (2021).
- Xiang, W. et al. Short-term coalmine gas concentration prediction based on wavelet transform and extreme learning machine.
## Math. Probl. Eng. 2014, 1 (2014).
- Ye, Z. et al. A digital twin approach for tunnel construction safety early warning and management. Comput. Ind. 144, 103783
## (2023).
- Fan, C., Li, S., Luo, M., Du, W. & Yang, Z. Coal and gas outburst dynamic system. Int. J. Mining Sci. Technol. 27, 49–55 (2017).
- Ma, Y.-K. et al. Mechanism investigation on coal and gas outburst: An overview. Int. J. Miner. Metall. Mater. 27, 872–887 (2020).
- Liu, T., Lin, B., Fu, X. & Zhu, C. Modeling air leakage around gas extraction boreholes in mining-disturbed coal seams. Process
## Saf. Environ. Prot. 141, 202–214 (2020).
-    Hyder, Z., Siau, K. & Nah, F. Artificial intelligence, machine learning, and autonomous technologies in mining industry. J. Database
## Manag. 30, 67–79 (2019).
- Miao, D., Lv, Y., Yu, K., Liu, L. & Jiang, J. Research on coal mine hidden danger analysis and risk early warning technology based
on data mining in china. Process Saf. Environ. Prot. 171, 1–17 (2023).
-   Wang,  G. et al. Research and practice of intelligent coal mine technology systems in China. Int. J. Coal Sci. Technol. 9, 24 (2022).
-  Tingjiang, T., Enyuan, W., Ke, Z. & Changfang, G. Research on assisting coal mine hazard investigation for accident prevention
through text mining and deep learning. Resour. Policy 85, 103802 (2023).
-   China. National Mine Safety Administration. https:// www. china mine- safety. gov. cn/ (2024).
-  Diaz, J., Agioutantis, Z., Hristopulos, D. T., Schafrik, S. & Luxbacher, K. Time series modeling of methane gas in underground
mines. Mining Metall. Explor. 39, 1961–1982 (2022).
-  Wu, Y., Gao, R. & Yang, J. Prediction of coal and gas outburst: A method based on the bp neural network optimized by gasa. Process
## Saf. Environ. Prot. 133, 64–72 (2020).
-  Xie, J., Li, T. & Wang, X. A novel dt-based intelligent experiment method for complex industrial products. Adv. Eng. Inform. 59,
## 102275 (2024).
-  Dindarloo, S. R. & Siami-Irdemoosa, E. Data mining in mining engineering: Results of classification and clustering of shovels
failures data. Int. J. Mining Reclam. Environ. 31, 105–118 (2017).
-  Zhang, J., Ai, Z., Guo, L. & Cui, X. Research of synergy warning system for gas outburst based on entropy-weight Bayesian. Int. J.
## Comput. Intell. Syst. 14, 376–385 (2021).
-   Gao,  X. et al. An agcrn algorithm for pressure prediction in an ultra-long mining face in a medium-thick coal seam in the northern
Shaanxi area. China. Appl. Sci. 13, 11369 (2023).
-  Qiao, W. Analysis and measurement of multifactor risk in underground coal mine accidents based on coupling theory. Reliab. Eng.
## Syst. Saf. 208, 107433 (2021).
-  Cai, Y., Wu, S., Zhou, M., Gao, S. & Yu, H. Early warning of gas concentration in coal mines production based on probability
density machine. Sensors 21, 5730 (2021).
- Tutak, M. & Brodny, J. Predicting methane concentration in longwall regions using artificial neural networks. Int. J. Environ. Res.
## Public Health 16, 1406 (2019).
-  Ding, J., Shi, H., Jiang, D. & Rong, X. Prediction of coal mine gas concentration based on partial least squares regression. In 2019
Chinese Automation Congress (CAC) 5243–5246 (IEEE, 2019).

## 12
## Vol:.(1234567890)
## Scientific Reports
## |        (2024) 14:13795  |
https://doi.org/10.1038/s41598-024-64181-7
www.nature.com/scientificreports/
-   Du,  Z. et al. Response characteristics of gas concentration level in mining process and intelligent recognition method based on
bi-lstm. Mining Metall. Explor. 40, 807–818 (2023).
-  Yang, X., Yu, X., Zhang, C., Li, S. & Niu, Q. Minegps: Battery-free localization base station for coal mine environment. IEEE Com-
mun. Lett. 25, 2579–2583 (2021).
- Janusz,  A. et al. Predicting seismic events in coal mines based on underground sensor measurements. Eng. Appl. Artif. Intell. 64,
## 83–94 (2017).
-  Kozielski, M., Sikora, M. & Wróbel, Ł. Data on methane concentration collected by underground coal mine sensors. Data Brief
## 39, 107457 (2021).
-  Ashish, V. Attention is all you need. Adv. Neural Inf. Process. Syst. 30, 1 (2017).
-  Liu, Y., Gong, C., Yang, L. & Chen, Y. Dstp-rnn: A dual-stage two-phase attention-based recurrent neural network for long-term
and multivariate time series prediction. Expert Syst. Appl. 143, 113082 (2020).
-  Diaz, J., Agioutantis, Z., Hristopulos, D. T., Luxbacher, K. & Schafrik, S. Forecasting of methane gas in underground coal mines:
Univariate versus multivariate time series modeling. Stoch. Environ. Res. Risk Assess. 37, 2099–2115 (2023).
-  Zhang, G., Wang, E., Zhang, C., Li, Z. & Wang, D. A comprehensive risk assessment method for coal and gas outburst in under-
ground coal mines based on variable weight theory and uncertainty analysis. Process Saf. Environ. Prot. 167, 97–111 (2022).
-  Kursunoglu, N. Fuzzy multi-criteria decision-making framework for controlling methane explosions in coal mines. Environ. Sci.
## Pollut. Res. 1, 1–17 (2024).
-  Shi, L., Wang, J., Zhang, G., Cheng, X. & Zhao, X. A risk assessment method to quantitatively investigate the methane explosion
in underground coal mine. Process Saf. Environ. Prot. 107, 317–333 (2017).
-  Lai, W. & Shao, L. Projection of early warning identification of hazardous sources of gas explosion accidents in coal mines based
on ntm deep learning network. Appl. Math. Nonlinear Sci. 8, 407–418 (2023).
-   Ślęzak,  D. et al. A framework for learning and embedding multi-sensor forecasting models into a decision support system: A case
study of methane concentration in coal mines. Inf. Sci. 451, 112–133 (2018).
-  Hochreiter, S. & Schmidhuber, J. Long short-term memory. Neural Comput. 9, 1735–1780 (1997).
-  Wu, H., Xu, J., Wang, J. & Long, M. Autoformer: Decomposition transformers with auto-correlation for long-term series forecast-
ing. Adv. Neural Inf. Process. Syst. 34, 22419–22430 (2021).
- Vaswani,  A. et al. Attention is all you need. Adv. Neural Inf. Process. Syst. 30, 1 (2017).
Author contributions
Haoqian Chang: Conceptualization, Methodology, Data curation, Writing original draft; Xiangrui Meng: Funding
acquisition, Supervision; Xiangqian Wang: Data curation, Resources; Zuxiang Hu: Validation, Review & editing.
## Funding
This work was financially supported by the National Natural Science Foundation of China (Grant Nos. 52374074,
## 51874003, 51474007).
Competing interests
The authors declare no competing interests.
Additional information
Correspondence and requests for materials should be addressed to H.C. or X.W.
Reprints and permissions information is available at www.nature.com/reprints.
Publisher’s note Springer Nature remains neutral with regard to jurisdictional claims in published maps and
institutional affiliations.
Open  Access    This  article  is  licensed  under  a  Creative  Commons  Attribution  4.0  International
License, which permits use, sharing, adaptation, distribution and reproduction in any medium or
format,  as  long  as  you  give  appropriate  credit  to  the  original  author(s)  and  the  source,  provide  a  link  to  the
Creative Commons licence, and indicate if changes were made. The images or other third party material in this
article are included in the article’s Creative Commons licence, unless indicated otherwise in a credit line to the
material.  If  material  is  not  included  in  the  article’s  Creative  Commons  licence  and  your  intended  use  is  not
permitted by statutory regulation or exceeds the permitted use, you will need to obtain permission directly from
the copyright holder. To view a copy of this licence, visit http:// creat iveco mmons. org/ licen ses/ by/4. 0/.
## © The Author(s) 2024