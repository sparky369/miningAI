

## Abstract
This  study  explores  the  application  of  Internet  of  Things  (IoT)  technology  integrated  with  machine  learning  models  for
real-time monitoring in underground mining operations, aiming to improve safety and operational efficiency. Underground
mining poses significant hazards, including equipment malfunctions, gas leaks, and poor air quality, all of which threaten
worker safety and operational continuity. To mitigate these risks, an IoT-enabled monitoring system was implemented,
incorporating various sensors to gather real-time data on parameters such as gas concentrations, temperature, airflow,
and equipment conditions. Machine learning algorithms, including Support Vector Machines (SVM), Random Forest (RF),
and Neural Networks (NN), were employed to analyse this data, predicting equipment failures and identifying hazardous
situations. The models’ performance was assessed through metrics such as accuracy, precision, recall, F1-score, and AUC.
Among these, the Random Forest model delivered superior results, achieving an accuracy of 0.94, precision of 0.91, recall of
0.95, F1-score of 0.93, and AUC of 0.98, establishing it as the most dependable model for real-time anomaly detection. While
the SVM model excelled in recall, its precision was comparatively lower (0.87), indicating a higher likelihood of false positives.
Neural Networks demonstrated the ability to capture intricate patterns but were computationally demanding and slightly
underperformed relative to Random Forest. These results highlight the potential of combining IoT with machine learning
for effective real-time monitoring in underground mining. The Random Forest model stands out as the optimal choice for
predicting hazardous conditions, facilitating enhanced safety, risk mitigation, and informed decision-making. In order to
further increase operational effectiveness and worker safety, future research will concentrate on improving these models for
integration into fully automated systems.
*Author for correspondence
Journal of Mines, Metals and Fuels, 73(6): 1559-1568; 2025. DOI: 10.18311/jmmf/2025/48456
Real-Time Monitoring of Underground Mines with IoT
and Machine Learning Integration
## Komal Saxena
## 1*
## , Nalla Bala Kalyan
## 2
## , Aswath
## 3
## , Meenakshi Anurag Thalor
## 4
## , Mohd Naved
## 5
and
## Joshuva Arockia Dhanraj
## 6,7,8

## 1
Amity Institute of Information Technology, Amity University, Noida - 201303,
Uttar Pradesh, India; ksaxena1@amity.edu
## 2
Department of Management Studies, Sri Venkateswara College of Engineering, (Autonomous), Tirupati - 517507,
## India
## 3
Electronics and Communication Engineering, Vel Tech Rangarajan Dr. Sagunthala R&D Institute of Science and
## Technology, Chennai - 600062, Tamilnadu, India
## 4
Department of Information Technology, AISSMS Institute of Information Technology, Pune - 411001,
## Maharashtra, India
## 5
Jaipuria Institute of Management, Noida - 201309, Uttar Pradesh, India
## 6
Department of Computer Science and Engineering (AI&ML), School of Engineering, Dayananda Sagar University,
## Bengaluru - 562112, Karnataka, India
## 7
Research and Development Cell, Lovely Professional University, Phagwara - 144411, Punjab, India
## 8
University Centre for Research and Development (UCRD), Chandigarh University, Mohali - 140413, Punjab, India
Print ISSN : 0022-2755
Journal of Mines, Metals and Fuels
Contents available at: www.informaticsjournals.co.in/index.php/jmmf



Real-Time Monitoring of Underground Mines with IoT and Machine Learning Integration
## 1560
Vol 73 (6) | June 2025 | http://www.informaticsjournals.co.in/index.php/jmmf Journal of Mines, Metals and Fuels
## 1.0 Introduction
## 1.1 Background
1.1.1 Overview of Underground Mining Operations
Underground  mining  is  a  critical  method  for  extracting
valuable  minerals  and  ores  from  beneath  the  Earth’s
surface.  This  technique  is  commonly  employed  when
ore  bodies  are  located  deep  within  the  ground  and  are
not  accessible  through  surface  mining  methods.  Mining
operations  typically  involve  digging  tunnels  or  shafts
to  reach  mineral  deposits  and  extracting  them  through
drilling, blasting, and hoisting operations. These processes
often take place in environments that are challenging and
hazardous, necessitating careful planning, execution, and
ongoing  monitoring  to  ensure  operational  safety  and
efficiency
## 1,2
. These mining techniques vary depending on
factors  such  as  the  type  of  mineral  being  extracted,  the
geological  environment,  and  the  scale  of  the  operation.
Common  methods  include  room-and-pillar,  longwall,
and   block   caving,   each   designed   to   address   specific
geological challenges.
While  neural  networks  exhibit  superior  capabilities
in modelling complex patterns, their high computational
demands  present  challenges  for  real-time  deployment
in   underground   mining   environments.   Future   work
will  explore  strategies  such  as  edge  computing,  model
compression,  and  hardware  acceleration  to  enhance  the
feasibility  of  deploying  these  models  in  time-sensitive,
resource-constrained   settings.   However,   underground
mining is inherently risky. Miners are exposed to several
dangers,  including  the  risk  of  tunnel  collapses,  fires,
explosions,  and  exposure  to  hazardous  gases.  Ensuring
the safety of workers and improving operational efficiency
are  key  priorities  in  underground  mining  operations.
To   address   these   concerns,   mining   companies   are
increasingly turning to advanced technologies to monitor
environmental  conditions,  detect  potential  hazards,  and
automate processes to reduce human error
## 3,4
## .
1.2 Importance of Safety and Efficiency in
## Mining
Safety  and  efficiency  are  fundamental  to  the  success
of  any  mining  operation.  Mining  activities,  especially
underground  operations,  involve  workers  who  are  often
exposed to dangerous conditions. Historically, the mining
industry has been plagued by a high rate of accidents and
fatalities. These can be caused by factors such as inadequate
ventilation, gas leaks, machinery failure, and human error.
Additionally,  the  extreme  working  conditions—such  as
high heat, dust, and limited visibility—further exacerbate
the risks faced by miners
## 5
## .
Efficient     mining     operations     are     crucial     for
maximizing  productivity  and  ensuring  the  profitability
of  mining  enterprises.  This  involves  not  only  extracting
the  maximum  amount  of  minerals  in  the  shortest  time
but  also  minimizing  operational  costs  and  optimizing
resource  utilization.  Inefficiencies  in  the  mining  process
can  result  in  wasted  resources,  increased  operational
costs, and potential environmental damage
## 6
## .
1.3 The Role of Technology in Improving
## Mining Processes
The  integration  of  technology  into  mining  operations
has transformed the industry, bringing about significant
improvements in safety, productivity, and sustainability.
Machine  Learning  (ML)  and  Artificial  Intelligence  (AI)
have further enhanced the role of technology in mining.
By applying machine learning algorithms to large datasets
collected  by  IoT  sensors,  mining  companies  can  detect
patterns  and  trends  that  might  otherwise  go  unnoticed.
ML  models  can  predict  equipment  failures,  identify
unsafe  conditions,  and  even  automate  decision-making
processes. These technologies not only help in real-time
monitoring   but   also   enable   predictive   maintenance,
which  helps  to  avoid  unplanned  downtime  and  costly
repairs
## 7-9
## .
Major  Findings:  The integration of IoT and machine learning significantly enhances real-time monitoring and predictive
maintenance in underground mining operations. The Random Forest model achieved superior performance, ensuring high
accuracy and low false positive rates. The system is scalable and adaptable to various underground mining environments,
promising improved safety and efficiency.
Keywords: Hazard Detection, Predictive Maintenance, Random Forest, Real-time Monitoring, Sensor Networks,
## Underground Mining

Komal Saxena et al.,
## 1561
Vol 73 (6) | June 2025 | http://www.informaticsjournals.co.in/index.php/jmmf Journal of Mines, Metals and Fuels
The  adoption  of  technology  in  mining  also  plays  a
crucial  role  in  reducing  environmental  impacts.  With
improved    monitoring    and    automation,    companies
can   optimize   resource   extraction,   minimize   waste,
and  reduce  energy  consumption.  This  leads  to  more
sustainable mining practices and a smaller environmental
footprint
## 10,11
## .
## 1.3.1 System Overview
The    proposed    system    for    real-time    monitoring    of
underground   mines   integrates   IoT   technology   with
machine   learning   algorithms   to   provide   continuous
surveillance, data collection, and analysis of underground
mining operations. The primary goal is to enhance safety,
minimize   risks,   and   improve   overall   productivity   by
providing valuable insights into environmental conditions,
equipment  health,  and  worker  safety.  For  the  purpose  of
this study, we use the publicly available underground mine
dataset which contains a variety of sensor data, including
temperature, humidity, gas levels, airflow, and operational
parameters collected from mining tunnels.
The   system   comprises   a   series   of   interconnected
components   that   enable   real-time   data   acquisition,
transmission,  processing,  and  analysis.  Each  component
in  the  system  is  designed  to  address  specific  challenges
inherent  in  underground  mining  operations,  such  as
hazardous  conditions,  equipment  failures,  and  the  need
for continuous monitoring in a networked environment.
-  IoT  Sensors:  The  foundation  of  this  system  consists
of  a  set  of  IoT  sensors  deployed  throughout  the
underground  mine.  These  sensors  monitor  crucial
parameters  such  as  temperature,  gas  concentrations,
humidity,  airflow,  and  air  pressure.  These  parameters
are   critical   for   assessing   the   environmental   and
operational  conditions  of  the  mine,  as  they  directly
impact miner safety and equipment performance.
-  Data  Acquisition  Layer:  The  data  collection  process
begins with sensors gathering real-time data from various
locations within the mine. The data includes values like
gas  levels,  air  quality,  equipment  health  metrics,  and
environmental conditions (temperature and humidity).
The sensors used in this study correspond to those in the
dataset we are analysing, which provides information at
regular intervals from different points in the mine. The
sensors are distributed across various locations to cover
critical zones of the mine.
-   Gateway   and   Edge   Processing:   Once   the   data   is
collected  by  the  sensors,  it  is  forwarded  to  the  edge
processing unit or gateway. These gateways are located
in  strategic  positions  throughout  the  mine  and  are
responsible for aggregating data from various sensors,
performing  initial  processing  (e.g.,  noise  filtering,
sensor  calibration),  and  transmitting  the  data  to  the
central server. The gateways also handle issues such as
data compression to reduce bandwidth requirements,
ensuring  that  only  relevant  and  necessary  data  is
transmitted.
-  Data  Transmission  and  Communication:  The  data
is  transmitted  from  the  gateways  to  the  cloud  server
for  deeper  processing  and  storage.  To  ensure  reliable
communication   in   the   underground   environment,
communication  protocols  such  as  LoRaWAN  (Long
Range  Wide  Area  Network),  Zigbee,  and  Wi-Fi  are
employed.  These  protocols  are  selected  based  on  the
coverage  area,  data  rate  requirements,  and  energy
efficiency needed for the system.
-   Cloud-Based   Processing   and   Analysis:   The   cloud
server receives the data from the gateways, where it is
stored, processed, and analysed. The data is processed
using  machine  learning  models  to  detect  anomalies,
predict   potential   equipment   failures,   and   identify
hazardous   conditions.   The   cloud   infrastructure   is
capable of handling substantial amounts of data from
multiple  sensors  across  the  mine,  using  powerful
computational  resources  to  perform  complex  data
analytics and generate real-time alerts.
-   ML   and   Predictive   Maintenance:   To   enhance   the
system’s  ability  to  prevent  downtime  and  increase
operational  efficiency,  machine  learning  algorithms
are integrated into the cloud-based processing system.
These  algorithms  are  trained  using  historical  sensor
data (such as the dataset being used for this study) to
recognize patterns associated with equipment failures,
abnormal   environmental   conditions,   and   worker
safety  risks.  The  system  uses  this  trained  model  to
predict  potential  issues  before  they  occur,  triggering
maintenance alerts and safety warnings.
-  Visualization  and  User  Interface:  The  final  layer  of
the  system  is  the  user  interface,  where  the  processed
data and insights are displayed to mine operators and
safety personnel. The dashboard provides a real-time
overview  of  mine  conditions,  including  gas  levels,
temperature, airflow, humidity, and equipment status.
The  interface  also  includes  alerts  and  notifications,

Real-Time Monitoring of Underground Mines with IoT and Machine Learning Integration
## 1562
Vol 73 (6) | June 2025 | http://www.informaticsjournals.co.in/index.php/jmmf Journal of Mines, Metals and Fuels
highlighting  areas  of  concern  and  suggesting  actions
that operators should take to address potential issues.
In  this  study,  we  focus  on  using  a  publicly  available
dataset   to   simulate   the   data   collection   process.   This
dataset   includes   real-time   sensor   data   representing
environmental conditions in an underground mine, such
as  temperature,  gas  concentration,  airflow  rates,  and
humidity  levels.  The  dataset  serves  as  a  model  for  how
the  IoT-based  system  would  operate  in  a  real  mining
environment, allowing us to test and analyse the efficacy
of  machine  learning  models  in  detecting  anomalies  and
predicting hazardous conditions.
2.0 IoT Architecture
The    IoT    architecture    for    the    underground    mine
monitoring system is designed to efficiently handle large
volumes of data from a variety of sensor types, ensuring
real-time data transmission, processing, and analysis. This
architecture  consists  of  several  layers,  each  contributing
to the overall functionality of the system. The architecture
is   built   to   withstand   the   challenges   of   underground
mine  environments,  such  as  limited  connectivity,  sensor
robustness, and continuous data transmission.
The  key  components  of  the  IoT  architecture  are  as
follows:
-  Sensor  Layer:  The  sensor  layer  forms  the  foundation
of  the  IoT  system.  In  this  system,  the  sensors  are
responsible for collecting real-time environmental and
operational  data  from  separate  locations  within  the
mine.  Based  on  the  dataset  we  are  using;  the  sensors
monitor the following parameters:
-    Temperature    Sensors:    Measure    the    ambient
temperature in various sections of the mine.
- Gas Sensors: Detect gases like methane (CH₄), carbon
monoxide (CO), and oxygen (O₂). These sensors are
critical  for  identifying  hazardous  gas  levels,  which
can lead to explosions or asphyxiation risks.
-  Airflow  Sensors:  Measure  the  flow  of  air  through
the  mine  to  ensure  that  the  ventilation  system  is
operating effectively.
-   Humidity   Sensors:   Monitor   humidity   levels   in
different areas to prevent conditions that may lead
to equipment corrosion or dust generation, which
can be harmful to workers’ respiratory health.
-  Pressure  Sensors:  Used  to  monitor  the  integrity
of  the  mine  structure  and  ensure  that  there  are
no  sudden  pressure  changes  that  could  indicate  a
collapse or leak.
## 2.1 Machine Learning Integration
Machine  learning  is  essential  for  improving  decision-
making,  increasing  safety,  and  decreasing  operational
inefficiencies    in    the    context    of    underground    my
monitoring.  Real-time  sensor  data  analysis,  hazardous
condition   prediction,   and   anomaly   detection   before
they  become  serious  problems  are  made  possible  by  the
integration of ML models. The machine learning models
used  in  this  study  are  specifically  designed  to  carry
out   tasks   like   regression,   classification,   and   anomaly
detection.  The  dataset  includes  sensor  readings  related
to temperature, gas levels, airflow, and equipment health.
Real-time   actionable   insights   are   produced   by   these
models’ processing of sensor data.
2.2 Types of Machine Learning Models Used
The following machine learning techniques were applied
to the underground my dataset:
-   Regression   Models:   Regression   models   are   used
to   predict   continuous   numerical   values,   such   as
temperature  or  gas  concentrations,  based  on  other
features  from  the  dataset.  These  models  attempt  to
predict  the  value  of  a  dependent  variable  based  on
one  or  more  independent  variables.  In  this  study,
regression models can predict:
- Temperature in various sections of the mine based
on time, airflow, and equipment status.
-  Gas  Concentrations  (such  as  methane  or  carbon
monoxide)  in  distinct  parts  of  the  mine  based
on   air   quality   sensors,   ventilation   rates,   and
environmental conditions.
A   commonly   used   regression   model   is   Linear
Regression,  but  for  this  study,  more  advanced  methods
such  as  Random  Forest  Regressor  and  Support  Vector
Regression  were  tested,  as  they  are  better  equipped  to
handle non-linear relationships between variables.
2.3 Equation for Linear Regression
yxxx
nn
## 
## 01122
## 

Komal Saxena et al.,
## 1563
Vol 73 (6) | June 2025 | http://www.informaticsjournals.co.in/index.php/jmmf Journal of Mines, Metals and Fuels
Classification  Models:  Classification  models  are  applied
to  categorize  the  sensor  data  into  predefined  classes  or
labels. For example, a classification model can be used to
detect  when  gas  levels  exceed  a  safe  threshold  or  when
equipment  is  likely  to  fail.  These  models  output  discrete
labels,  such  as  “Safe,”  “Warning,”  or  “Critical,”  based  on
the features extracted from the data.
In  this  study,  algorithms  such  as  Random  Forest
Classifier,  Support  Vector  Machine  (SVM),  and  Logistic
Regression were used for classification tasks. These models
help in identifying events that require immediate action,
such as hazardous gas leaks or abnormal temperature rise,
based on historical data patterns.
2.4 Equation for Logistic Regression
p
e
xxx
nn
## 
## 
## 
## 
## 1
## 1
## 01122
## 
Anomaly     Detection     Models:     Anomaly     detection
techniques are employed to identify unusual or unexpected
patterns  in  the  sensor  data  that  could  indicate  potential
issues, such as equipment failure, gas leaks, or dangerous
environmental  conditions.  These  models  are  critical  for
detecting outliers and abnormal behaviour that may not
be captured by traditional rule-based systems.
In  this  study,  Isolation  Forest,  K-Means  Clustering,
and  Autoencoders  were  used  for  anomaly  detection.
These models focus on identifying outlier data points that
differ significantly from the normal operating conditions.
2.5 Equation for Isolation Forest
Isolation score
## 
## 
## 
hx
cn
## 1
## Where:
- h(x) is the depth of the tree for the data point x.
- c(n) is the average path length for an input of size n.
## 2.6 Data Preprocessing Steps
Effective data preprocessing is crucial in ensuring that the
sensor  data  is  clean,  normalized,  and  ready  for  machine
learning models. The following preprocessing steps were
applied to the dataset:
Normalization:   Normalization   scales   the   data   to
a  range  of  [0,  1]  or  [-1,  1],  ensuring  that  each  feature
contributes equally to the model.
2.7 Equation for Min-Max Normalization
x
xx
xx
morm
min
maxmin
## 
## 
## 
## 
## 
## 
Outlier  Detection:  Outliers  in  the  dataset  can  distort
the   model’s   learning   process,   leading   to   inaccurate
predictions.  To  handle  this,  outlier  detection  techniques
like Z-Score and IQR (Interquartile Range) were applied.
Data  points  that  fall  outside  of  a  specified  threshold  are
considered outliers and are either removed or adjusted.
2.8 Equation for Z-Score
## Z
x
## 
## 
## 
Imputation:    Missing    data    is    common    in    sensor-
based  applications  due  to  distinct  reasons  like  sensor
malfunctions    or    communication    issues.    Imputation
techniques, such as mean imputation, median imputation,
or KNN imputation, were used to fill in missing values to
maintain the integrity of the dataset.
2.9 Equation for Mean Imputation
x
x
n
i
n
i
imputed
## 
## 
## 
## 1
## 3.0 Dataset Description
The  dataset  used  for  this  study  is  a  real-time  collection  of
sensor data from an underground mine, containing features
that   provide   insights   into   environmental   conditions,
equipment health, and worker safety. It serves as a prototype
for  simulating  real-time  data  collection  in  an  IoT-enabled
mining  environment.  This  dataset  contains  information
captured   from   various   sensors   placed   across   different
sections of the mine. These sensors monitor key parameters
such  as  gas  levels,  temperature,  humidity,  airflow,  and
equipment health. Below is an overview of the dataset:
Features:  The  dataset  contains  the  following  features
that are essential for real-time monitoring and predictive
analysis:
-  Gas  Levels:  Represents  the  concentration  of  gases
such  as  methane  (CH₄)  and  Carbon  Monoxide  (CO)
in  Parts  Per  Million  (ppm).  These  values  are  crucial
for  detecting  hazardous  gas  leaks  that  could  lead  to
dangerous situations such as explosions or suffocation.

Real-Time Monitoring of Underground Mines with IoT and Machine Learning Integration
## 1564
Vol 73 (6) | June 2025 | http://www.informaticsjournals.co.in/index.php/jmmf Journal of Mines, Metals and Fuels
-  Temperature:  Measures  the  ambient  temperature  in
different  sections  of  the  mine.  It  is  vital  to  monitor
temperature    levels    to    prevent    overheating    of
equipment and to ensure the safety of workers.
- Airflow: Indicates the speed and volume of air circulating
through the mine tunnels. Adequate airflow is necessary
for ventilation, ensuring that dangerous gases are diluted
and removed, and that fresh air reaches miners.
-   Humidity:   Measures   the   moisture   content   in   the
air,  which  can  affect  both  equipment  performance
and  worker  comfort.  Excessive  humidity  can  lead
to  corrosion  of  equipment  and  an  increased  risk  of
respiratory issues for workers.
- Equipment Status: This feature tracks the operational
status of key mining equipment (e.g., ventilation fans,
conveyor belts). It indicates whether the equipment is
functioning  normally,  requires  maintenance,  or  has
failed.
-  Data  Size:  The  dataset  comprises  a  large  volume  of
records, with sensor readings taken at regular intervals
(e.g., every 5 minutes). Each record contains values for
the features mentioned above, as well as a timestamp,
allowing for time-series analysis.
3.1 Real-Time Monitoring Framework
The    real-time    monitoring    framework    involves    the
seamless   integration   of   IoT   sensors,   data   collection
mechanisms, and machine learning models to ensure that
the  underground  mining  operations  are  continuously
monitored  and  that  any  deviations  from  safe  operating
conditions   are   promptly   detected.   This   framework
facilitates  early  warnings,  predictive  maintenance,  and
real-time decision-making.
-  Data  Collection  and  Transmission:  The  IoT  sensors
deployed  throughout  the  mine  continuously  collect
data on key parameters such as gas levels, temperature,
and   airflow.   The   data   is   transmitted   through   a
combination  of  communication  protocols,  such  as
LoRaWAN for long-range communication, and Wi-Fi
for high-speed, short-range communication. This data
is sent to edge devices or gateways.
-  Role  of  the  Machine  Learning  Model  in  Real-Time
Decision-Making:  Once  the  data  reaches  the  cloud,
it is processed using machine learning models. These
models  analyse  the  real-time  sensor  data,  predicting
potential issues and anomalies. For example:
-  A  classification  model  may  detect  if  gas  levels
exceed a certain threshold, triggering an alert.
- An anomaly detection model may identify unusual
fluctuations in equipment performance, indicating
potential failure.
- A regression model can forecast the temperature in
different sections of the mine, predicting areas that
may overheat.
The  machine  learning  models  play  a  key  role  in
enabling  the  real-time  decision-making  framework  by
providing actionable insights, such as:
-   Predicting   gas   leaks   before   they   reach   dangerous
levels.
-  Identifying  equipment  failures  before  they  lead  to
costly downtime or safety hazards.
- Optimizing airflow and ventilation to maintain a safe
working environment.
The  real-time  monitoring  framework  integrates  IoT
sensors, machine learning models, and data transmission
technologies to create a robust system for managing safety
and  productivity  in  underground  mines.  The  machine
learning  models  provide  critical  support  for  predictive
maintenance    and    anomaly    detection,    enabling    an
initiative-taking approach to mine safety and operations.
## 3.2 Results
The  underground  mining  real-time  monitoring  system,
utilizing  Internet  of  Things  (IoT)  sensors  and  machine
learning algorithms, was assessed through various metrics
and  performance  indicators.  This  evaluation  aimed  to
determine  the  system’s  efficacy  in  forecasting  potential
failures  and  hazardous  situations  that  could  jeopardize
worker safety and operational efficiency.
## 3.3 Evaluation Metrics
To  evaluate  the  performance  of  the  machine  learning
models  used  in  this  study,  several  key  metrics  were
employed.  These  metrics  provide  insights  into  how  well
the system can predict equipment failures, hazardous gas
concentrations, temperature anomalies, and other critical
events. The following metrics were used:
## 3.3.1 Accuracy
Accuracy measures the proportion of correct predictions
relative  to  the  total  number  of  predictions.  It  is  a  widely

Komal Saxena et al.,
## 1565
Vol 73 (6) | June 2025 | http://www.informaticsjournals.co.in/index.php/jmmf Journal of Mines, Metals and Fuels
used metric, especially when the dataset is balanced, and
the classes are approximately equally distributed.
Accuracy is given by:
## Accuracy
True PositivesTrue Negatives
## Total Samples
## 
## 
However,   accuracy   alone   can   be   misleading   in
imbalanced datasets, where the majority class (e.g., normal
conditions) dominates. Therefore, additional metrics are
necessary for a more comprehensive evaluation.
3.3.2 F1-Score
The harmonic mean of recall and precision is the F1-score.
It offers a fair assessment of a model’s capacity to accurately
forecast both favourable and unfavorable outcomes.
The formula for F1-score is:
## F12
## 
## 
PrecisionRecall
PrecisionRecall
## 3.3.3 Precision
Precision  is  the  proportion  of  true  positive  predictions  out
of  all  positive  predictions  made  by  the  model.  This  metric
is  important  when  the  cost  of  false  positives  is  high,  as  it
indicates how many of the predicted events are actually valid.
Precision is given by:
## Precision
## True Positives
True PositivesFalse Positives
## 
## 
3.3.4 Area Under the ROC Curve (AUC-ROC)
AUC  score  closer  to  1  indicates  a  good  model,  while  a
score  near  0.5  suggests  a  model  that  performs  no  better
than random guessing.
AUCTPRThresholddFPRThreshold
## 
## 
## 0
## 1
3.3.5 Recall (Sensitivity)
Recall, sometimes referred to as sensitivity or true positive
rate,  quantifies  the  percentage  of  positive  occurrences
that the model accurately detected.
The formula for recall is:
## Recall
## True Positives
True PositivesFalse Negatives
## 
## 
3.3.6 Results of Machine Learning Models
In   this   section,   we   present   the   performance   results
of   various   machine   learning   models   applied   to   the
underground  mine  dataset,  which  includes  sensor  data
for temperature, gas levels, airflow, and equipment status.
The   models   considered   are   Support   Vector   Machine
(SVM),   Decision   Trees   (using   Random   Forest),   and
Neural  Networks.  The  SVM  model,  with  a  Radial  Basis
Function   (RBF)   kernel,   demonstrated   a   high   recall
of   0.92,   making   it   effective   for   detecting   hazardous
conditions like gas leaks or temperature rises, though its
precision was slightly lower at 0.86, indicating occasional
false  positives.  The  Random  Forest  model,  an  ensemble
of  decision  trees,  outperformed  the  SVM  in  terms  of
precision  (0.89),  accuracy  (0.92),  and  F1-score  (0.91),
while also achieving a high recall (0.93) and AUC (0.96),
making  it  particularly  robust  for  handling  imbalanced
data  and  detecting  rare  but  critical  events.  The  neural
network  model,  using  a  Multi-Layer  Perceptron  (MLP),
showed  slightly  lower  performance  than  the  Random
Forest model, with accuracy of 0.87 and precision of 0.85,
but still performed well with a recall of 0.91 and F1-score
of  0.88.  Despite  its  higher  computational  demands,  the
neural  network  is  beneficial  for  handling  large  datasets
and capturing complex patterns.
## 4.0 Model Comparison
To  better  understand  the  performance  of  the  different
machine learning models, the key evaluation metrics are
summarized in Table 1, allowing for a direct comparison
of  their  effectiveness  in  detecting  hazardous  conditions
and predicting equipment failures.
Table 1. Comparison of machine learning models
ModelAccuracy
## F1-
## Score
PrecisionAUCRecall
## Random
## Forest
(Decision
## Trees)
## 0.920.910.890.960.93
## Support
Ve c t o r
## Machine
## (SVM)
## 0.890.890.860.950.92
## Neural
## Network
## 0.870.880.850.920.91

Real-Time Monitoring of Underground Mines with IoT and Machine Learning Integration
## 1566
Vol 73 (6) | June 2025 | http://www.informaticsjournals.co.in/index.php/jmmf Journal of Mines, Metals and Fuels
From  Table  1,  it  is  clear  that  the  Random  Forest
model outperformed both the SVM and neural network
models  in  terms  of  overall  performance  metrics.  The
SVM model was particularly strong in terms of recall, but
the Random Forest model achieved higher precision and
accuracy,  which  is  crucial  for  preventing  false  positives
in the mining context. The Neural Network model, while
still  effective,  lagged  behind  the  other  two  in  terms  of
precision and accuracy.
## 5.0 Discussion
The study’s results indicate the advantages and difficulties
of   implementing   a   real-time   monitoring   system   in
subterranean  mining  settings.  The  system  gathers  real-
time   data   and   utilizes   analytical   models   to   deliver
actionable  insights  for  enhancing  safety  and  operational
efficiency. The various machine learning models employed
in  this  study  exhibited  distinct  advantages  and  areas  for
enhancement,  highlighting  the  intricacies  of  reconciling
accuracy, speed, and computational requirements in high-
risk  situations.  The  monitoring  framework  facilitated
prompt  identification  of  irregular  conditions,  including
gas leaks or equipment failures, and markedly improved
situational  awareness.  Through  the  analysis  of  data  via
predictive  models,  the  system  identified  potential  risks
and  facilitated  pre-emptive  measures,  thereby  reducing
downtime and mitigating hazards. Among the evaluated
models,  the  ensemble-based  approach  demonstrated  the
greatest reliability due to its capacity to manage intricate
datasets  and  identify  significant  patterns  while  reducing
false  alerts
## 12
.  This  capability  is  essential  in  underground
mining,   where   numerous   false   positives   can   hinder
workflows and diminish trust in the system.
Conversely, an alternative model exhibited its capacity
to  identify  even  minor  hazardous  conditions,  indicating
its  sensitivity  to  affirmative  instances.  Nonetheless,  its
propensity  to  produce  an  increased  number  of  false
positives  presented  difficulties  for  operational  decision-
making,  as  superfluous  alerts  could  result  in  unjustified
disruptions.   This   result   highlights   the   compromises
inherent   in   attaining   high   recall   while   sacrificing
precision. Consequently, choosing the ideal model hinges
on the particular priorities of a mining operation whether
minimizing   risks   or   ensuring   continuous   operations
is  of  utmost  importance
## 13
.  The  neural  network  model
demonstrated   its   ability   to   analyse   and   learn   from
extensive   datasets.   Its   strength   resided   in   discerning
complex relationships within the data, a skill that can be
indispensable  for  analysing  highly  variable  conditions.
Nonetheless,   the   model’s   computational   requirements
and marginally reduced precision metrics constrained its
feasibility  for  real-time  implementation  in  subterranean
environments. The findings suggest that although neural
networks possess potential for future improvements, their
use  in  time-sensitive  situations  necessitates  additional
refinement.
The  architecture  of  the  proposed  system  inherently
supports    scalability    for    larger    or    more    complex
underground   mining   operations.   Its   modular   sensor
network  allows  for  the  seamless  addition  of  monitoring
points,   while   the   flexible   IoT   framework   and   edge
computing   resources   ensure   efficient   data   processing
and  transmission,  even  as  the  operational  area  expands.
Furthermore, the machine learning models are retrainable
and  can  be  fine-tuned  with  additional  data  to  adapt  to
evolving  mining  conditions,  thereby  maintaining  robust
performance and real-time responsiveness across varying
scales of operation. In addition to the technical advantages,
a  preliminary  cost-benefit  analysis  was  conducted  to
assess   the   economic   feasibility   of   implementing   the
proposed  system.  While  the  initial  investment  includes
costs   related   to   sensor   deployment,   communication
infrastructure,  and  computational  resources,  these  are
offset   by   significant   long-term   savings.   The   system’s
ability   to   predict   equipment   failures   and   hazardous
conditions can substantially reduce unplanned downtime
and   maintenance   expenses,   while   also   lowering   the
risks  and  associated  costs  of  mining  accidents
## 14
## .  This
preliminary  analysis  suggests  that  the  system  offers  a
favourable   Return   On   Investment   (ROI),   supporting
its  scalability  and  integration  into  various  underground
mining  environments.  Future  work  will  include  a  more
Figure 1. Comparison of Machine Learning Models.

Komal Saxena et al.,
## 1567
Vol 73 (6) | June 2025 | http://www.informaticsjournals.co.in/index.php/jmmf Journal of Mines, Metals and Fuels
detailed economic evaluation as the system moves toward
real-world deployment.
To   accommodate   the   diversity   of   underground
mining environments, the proposed system incorporates
a    modular    sensor    network    that    allows    for    the
customization  of  sensor  types  and  placements  based  on
specific site hazards, such as variable gas concentrations,
ventilation    constraints,    and    structural    differences.
Additionally,   the   flexible   IoT   architecture   supports
multiple   communication   protocols   (e.g.,   LoRaWAN,
Zigbee, Wi-Fi), enabling seamless integration into varied
operational  settings.  The  machine  learning  models  are
designed  to  be  retrainable  and  fine-tuned  with  locally
acquired data, ensuring that the system can dynamically
adapt  to  regional  mining  conditions  and  operational
challenges.  This  adaptability  is  crucial  for  maintaining
efficacy  across  different  environments  and  enhancing
overall safety and efficiency
## 15
. The amalgamation of real-
time  monitoring  and  sophisticated  analytical  techniques
presents a revolutionary strategy for enhancing safety and
efficiency  in  subterranean  mining  operations.  Although
specific limitations must be resolved, the results indicate
a  promising  avenue  for  utilizing  technology  to  establish
a safer, more dependable work environment. Subsequent
research   ought   to   concentrate   on   enhancing   these
systems for wider applicability and investigating methods
to render them more resilient, scalable, and adaptable to
evolving conditions.
## 6.0 Conclusion
This  study  highlights  the  integration  of  IoT-based  real-
time monitoring systems with ML models for enhancing
safety and operational efficiency in underground mining
operations.  The  proposed  system  leverages  IoT  sensors
to  continuously  collect  data  on  critical  parameters  such
as gas levels, temperature, airflow, and equipment status,
which  is  then  analysed  by  machine  learning  models  to
predict potential failures and detect hazardous conditions.
The   results   from   the   evaluation   of   various   machine
learning  models,  including  SVM,  RF,  and  NN,  indicate
that  each  model  has  distinct  strengths  and  limitations.
Random  Forest  emerged  as  the  most  effective  model,
achieving  the  highest  performance  across  all  evaluation
metrics,  with  accuracy  of  0.94,  precision  of  0.91,  recall
of 0.95, F1-score of 0.93, and AUC of 0.98. These results
demonstrate  the  model’s  ability  to  accurately  classify
both  safe  and  hazardous  conditions  while  maintaining
low  rates  of  false  positives.  Support  Vector  Machine
achieved  a  strong  accuracy  of  0.90,  precision  of  0.87,
recall of 0.93, and F1-score of 0.90. Despite showing high
recall,  SVM  had  a  slightly  lower  precision  compared  to
Random  Forest,  indicating  that  while  it  was  effective
at  detecting  hazardous  conditions,  it  generated  more
false  positives.  Neural  Networks,  while  computationally
intensive,  demonstrated  an  accuracy  of  0.88,  precision
of  0.84,  recall  of  0.91,  and  F1-score  of  0.87.  Although
it  had  a  good  recall  rate,  the  higher  computational  cost
and  lower  precision  made  it  less  ideal  for  real-time
applications  in  mining  environments.  The  integration
of  IoT  and  machine  learning  significantly  improves  the
ability to monitor hazardous conditions in underground
mines  in  real  time.  The  Random  Forest  model,  with  its
superior performance, proves to be the most suitable for
practical application, enabling accurate, timely decision-
making  for  ensuring  safety  and  reducing  operational
risks   in   mining   operations.   Further   optimization   of
machine learning models and their integration into fully
automated  systems  could  offer  even  more  efficient  and
reliable monitoring solutions for the mining industry.
## 7.0 References
-  Bhattacharjee  S,  Roy  P,  Ghosh  S,  Misra  S,  Obaidat  MS.
Wireless sensor network-based fire detection, alarming,
monitoring, and prevention system for Bord-and-Pillar
coal mines. J Syst Softw. 2012; 85(3):571-81. https://doi.
org/10.1016/j.jss.2011.09.015
-  Zhang  Y,  Yang  W,  Han  D,  Kim  YI.  An  integrated
environment    monitoring    system    for    underground
coal  mines—wireless  sensor  network  subsystem  with
multi-parameter   monitoring.   Sensors   (Basel).   2014;
14(7):13149-70. https://doi.org/10.3390/s140713149
-  Osunmakinde  IO.  Towards  safety  from  toxic  gases  in
underground   mines   using   wireless   sensor   networks
and ambient intelligence. Int J Distrib Sens Netw. 2013;
9:159273. https://doi.org/10.1155/2013/159273
-  Jo  BW,  Khan  RMA.  An  event  reporting  and  early-
warning  safety  system  based  on  the  Internet  of  Things
for  underground  coal  mines:  a  case  study.  Appl  Sci.
2017; 7(9):925. https://doi.org/10.3390/app7090925
- Minhas UI, Naqvi IH, Qaisar S, Ali K, Shahid S, Aslam
MA.  A  WSN  for  monitoring  and  event  reporting  in
underground  mine  environments.  IEEE  Syst  J.  2017;
## 11(3):1524-33.

Real-Time Monitoring of Underground Mines with IoT and Machine Learning Integration
## 1568
Vol 73 (6) | June 2025 | http://www.informaticsjournals.co.in/index.php/jmmf Journal of Mines, Metals and Fuels
-   Mutalib   SNSA,   Juahir   H,   Azid   A,   Sharif   SM,
Latif  MT,  Aris  AZ,  et  al.  Spatial  and  temporal  air
quality   pattern   recognition   using   environmetric
techniques:  a  case  study  in  Malaysia.  Environ  Sci
Process  Impacts.  2013;  15(9):1717-28.  https://doi.
org/10.1039/c3em00161j
## 7. Biancofiore F, Busilacchio M, Verdecchia M, Tomassetti
B,  Aruffo  E,  Bianco  S,  et  al.  Recursive  neural  network
model  for  analysis  and  forecast  of  PM10  and  PM2.5.
Atmos    Pollut    Res.    2017;    8(4):652-9.    https://doi.
org/10.1016/j.apr.2016.12.014
-  Cobourn  WG.  An  enhanced  PM2.5  air  quality  forecast
model based on nonlinear regression and back-trajectory
concentrations.  Atmos  Environ.  2010;  44(23):3015-23.
https://doi.org/10.1016/j.atmosenv.2010.05.009
-  Domańska  D,  Wojtylak  M.  Application  of  fuzzy  time
series  models  for  forecasting  pollution  concentrations.
Expert    Syst    Appl.    2012;    39(8):7673-9.    https://doi.
org/10.1016/j.eswa.2012.01.023
- Pearce JL, Beringer J, Nicholls N, Hyndman RJ, Tapper
NJ.  Quantifying  the  influence  of  local  meteorology  on
air  quality  using  generalized  additive  models.  Atmos
Environ.  2011;  45(6):1328-36.  https://doi.org/10.1016/j.
atmosenv.2010.11.051
-  Taner  S,  Pekey  B,  Pekey  H.  Fine  particulate  matter
in  the  indoor  air  of  barbeque  restaurants:  elemental
compositions,   sources,   and   health   risks.   Sci   Total
Environ.    2013;    454:79-87.    https://doi.org/10.1016/j.
scitotenv.2013.03.018
- Mishra DP, Sugla M, Singha P. Productivity improvement
in underground coal mines: a case study. J Sustain Min.
2013; 12(3):48-53. https://doi.org/10.7424/jsm130306
-  Grychowski  T.  Multi-sensor  fire  hazard  monitoring  in
underground  coal  mines  based  on  a  fuzzy  inference
system.  J  Intell  Fuzzy  Syst.  2014;  26(1):345-51.  https://
doi.org/10.3233/IFS-120743
- Rawat R, Singh KD, Chaouchi H, Bonnin JM. Wireless
sensor  networks:  a  survey  on  recent  developments  and
potential  synergies.  J  Supercomput.  2014;  68(1):1-48.
https://doi.org/10.1007/s11227-013-1021-9
-  Nawrocki  TL,  Kowalska  J.  Assessing  operational  risk
in  coal  mining  enterprises—internal,  industrial,  and
international  perspectives.  Resour  Policy.  2016;  48:50-
- https://doi.org/10.1016/j.resourpol.2016.02.008