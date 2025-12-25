


Online Deep Transfer Learning and Multi-Sensor
Analysis for Enhanced Underground Monitoring

## Milad Mousavi
School of Civil and Environmental
## Engineering
The University of New South Wales (UNSW)
## Sydney, Australia
milad.mousavi@unsw.edu.au

## Xuesong Shen*
School of Civil and Environmental
## Engineering
The University of New South Wales (UNSW)
## Sydney, Australia
x.shen@unsw.edu.au

## Zhigang Zhang
## Chongqing Research Institute
## China Coal Technology & Engineering
## Group
## Chongqing, China
zzg-2@163.com




## Khalegh Barati

School of Civil and
## Environmental Engineering

The University of New South
Wales (UNSW)

## Sydney, Australia

khalegh.barati@unsw.edu.au

## Binghao Li

School of Mineral and Energy
## Resources Engineering

The University of New South
Wales (UNSW)

## Sydney, Australia

binghao.li@unsw.edu.au







Abstract—Underground environments present unique
challenges  for  monitoring  hazardous  conditions  due  to  their
complex  and  dynamic  nature.  Current  prediction  methods  often
suffer  from  data  scarcity,  especially  during  the  early  operation
phases, and fail to adapt to changing conditions. This paper aims
to  address  these  issues  by  integrating  multi-sensor  analysis  with
online    transfer    learning    techniques    to    enhance    methane
concentration     monitoring     in     underground     settings.     The
methodology   involves   training   a   baseline   Long   Short-Term
Memory  (LSTM)  model  on  open-source  data  from  a  Polish  coal
mine  and  fine-tuning  it  using  an  online  learning  approach  with
data obtained from a Chinese coal mine. The results demonstrate
significant  improvements  in  prediction  accuracy  and  reliability,
especially  during  the  initial  stages  of  monitoring  when  data  are
sparse, achieving an R² value of 0.93 when using the online transfer
learning model. This study helps improve the safety and efficiency
of  underground  monitoring  systems  by  addressing  initial  data
scarcity    and    enhancing    model    adaptability    to    dynamic
environmental conditions.
Keywords—Multi-Sensor  Analysis,  Long  Short-Term  Memory
(LSTM),    Online    Transfer    Learning,    Dynamic    Underground
## Monitoring, Methane Concentration Prediction
## I. INTRODUCTION
Operating  in  underground  environments  presents  distinct
challenges   and   dangers   compared   to   their   above-ground
counterparts.   These   challenges   include   spatial   complexity,
geological   unpredictability,   inadequate   ventilation,   and   the
release  of  hazardous  substances  such  as  gases  and  dust  [1,  2].
The   variability   of   underground   settings,   characterized   by
fluctuating geological factors and gas emissions, poses dynamic
risks jeopardizing worker safety and surrounding infrastructure
[3,  4].  In  the  context  of  coal  mining  practices,  methane,  a
byproduct of coal formation, presents a persistent hazard, with
its accumulation considered extremely explosive when it reaches
between  5%  and  15%  [5].  However,  miners  typically  halt
operations    once   methane   concentrations   go   above   1%,
preventing  the  levels  from  nearing  the  explosive  range.  This
interruption   causes   significant   productivity   loss   in   mining
operations, resulting in millions of dollars in financial loss [6].
Hence,  continuous  monitoring  and  prediction  strategies  are
indispensable  for  ensuring  the  safety  and  sustainability  of
underground operations [7].
Underground  spaces  are  usually  equipped  with  advanced
digital systems for monitoring and sensing purposes [8]. These
systems  also  feature  specialized  tools  to  detect  and  manage
natural hazards such as dangerous methane concentration levels.
The Internet of Things (IoT) has further enhanced real-time data
collection,  monitoring,  and  early  warning  capabilities  in  these
settings  [9].  These  technologies  provide  real-time  information
on  environmental  conditions  like  temperature,  humidity,  and
hazardous  gas  levels  [10].  Despite  the  vast  amount  of  data
generated,  current  monitoring  systems  primarily  use  it  for
visualization and rely on engineering professionals for analysis.
However, visual analysis of multivariate sensor data streams is
a  complex  task.  Consequently,  valuable  data  often  remains
underutilized,   failing   to   provide   meaningful   insights   into
potential risks [11].
Advanced sensing technologies in underground
environments encounter another significant challenge due to the
incompatibility  among  various  data  sources [12]  .  Traditional
statistical models find it difficult to handle the large volume of
multi-sensor   data,   resulting   in   issues   with   accuracy   and
robustness,  which  hampers  their  ability  to  generalize  across
different projects [13]. Additionally, in the early phases of a new
project, there is typically a scarcity of data available for informed
decision-making, and the transfer of knowledge and experience
from   previous   projects   may   be   flawed [14].   Here   again,
This research is supported by funding from the Australian Research
Council (ARC) under Grant number IH210100048 ARC Research Hub for
Resilient and Intelligent Infrastructure Systems (RIIS).
## 125
2025 10th International Conference on Machine Learning Technologies
## 979-8-3315-3672-5/25/$31.00 ©2025 IEEE
2025 10th International Conference on Machine Learning Technologies (ICMLT) | 979-8-3315-3672-5/25/$31.00 ©2025 IEEE | DOI: 10.1109/ICMLT65785.2025.11193369
Authorized licensed use limited to: Lulea University of Technology. Downloaded on December 25,2025 at 12:26:59 UTC from IEEE Xplore.  Restrictions apply.

professional  expertise  plays  a  pivotal  role,  yet  this  knowledge
can be subjective and susceptible to errors.
This  paper  aims  to  enhance  the  accuracy  and  reliability  of
methane     concentration     monitoring     and     prediction     in
underground  environments  through  the  integration  of  multi-
sensor analysis and online transfer learning techniques. A robust
prediction  model  is  developed  by  leveraging  a  baseline Long
Short-Term Memory (LSTM) model trained on a dataset from a
Polish coal mine, which is then fine-tuned in an online manner
using  a  dataset  from  a  Chinese  coal  mine.  By  combining  data
from various environmental sensors and applying advanced deep
learning  models,  the  paper  captures  the  complex  temporal
patterns and dependencies in methane concentration time series.
Additionally,  the  paper  explores  the  practical  applications  of
online  transfer  learning  to  continuously  adapt and  improve
model  generalization  across  different  underground  scenarios,
ultimately contributing to safer and more efficient underground
monitoring and prediction systems.
## II. BACKGROUND REVIEW
This section provides a concise overview of relevant studies
that  inform  the  integration  of  multi-sensor  analysis  and  deep
transfer learning for enhanced underground monitoring.
A. Multi-Sensor Predictions in Underground Environments
Reference [15] developed  a  combined  prediction  model
based  on   the  dynamic  optimization  of  indicators  and  Bi-
directional   LSTM   networks   (Bi-LSTMs)   to   predict   gas
concentration  in  coal  mines.  The  methodology  involved  using
Spearman’s rank correlation coefficient to dynamically optimize
prediction  indicators  and  then  applying  Bi-LSTMs  to  extract
time series and spatial topology features from these indicators.
The model predicted gas concentration for the next 30 minutes
with  high  accuracy,  showing  an  average  R²  of  0.965  and a
prediction  efficiency  of  79.9%  for  abnormal  or  normal  gas
emissions.    The    outcomes    suggested    that    this    method
significantly   improved   the   accuracy   of   gas   concentration
predictions  compared  to  traditional  methods,  which  enhanced
early  warning  systems  and  safety  measures  in  coal  mines.
Despite   the   widespread   application   of   prediction   models,
especially    data-driven    models,    in    improving    prediction
accuracy, further research was needed to address the cold start
problem when deploying prediction and monitoring systems at
new   underground   sites [16]. Traditional   models   require   a
substantial  amount  of  pre-existing  data  to  train  effectively,
which is not always available at the beginning of new projects.
This  data  scarcity  poses  a  challenge  in  real-time  applications,
highlighting  the  necessity  for  models that  can  adapt  and  learn
incrementally as new data becomes available.
B. Transfer Learning Applications in Monitoring
Transfer learning is a subset of machine learning techniques
where a model developed for a specific task or domain is reused
as the starting point for a model on a different but related task or
domain. Transfer learning is a widely adopted approach for cases
in which the acquisition of data is challenging and the available
data sets are minimal. The applications of this approach extend
to monitoring environmental indicators across multiple domains.
For  example, reference [17] automated the  identification  of
native and invasive plant species using drones and deep transfer
learning.  The  authors  collected  a  dataset  with  10,000  images,
processed and augmented them, and applied several pre-trained
deep convolutional neural network models for feature extraction
and classification. The model, combined with data augmentation
and hyperparameter optimization, achieved the highest accuracy
of 94%.
Underground operations are a domain where data scarcity is
a significant and persistent issue. Reference [18] focused on the
retrieval  of  soil  heavy  metal  content  in  a  mining area  for
environmental  monitoring using  transfer  learning  techniques.
Initially,  a  model  was  pre-trained  with  soil  samples  from  the
source domain in 2017 and then retrained with a smaller set of
samples from the target domain in 2019. This model was utilized
to estimate the content of Cu and Pb at various sites in the study
area  in  2019,  with  the  spatial  distribution  of  these  elements
mapped   accordingly.   While   the   results   demonstrated   the
effectiveness of the model in estimating heavy metal content, the
study  acknowledged  the  need  for  more  soil  samples  to  further
enhance  the  model's  performance. Reference [19] presented  a
framework  for  real-time  heat  release  rate  inversion  of  tunnel
fires using deep learning and transfer learning. The researchers
utilized  large-scale  databases  and  transfer  learning  methods  to
predict tunnel fire states accurately, even in complex scenarios
with double fire sources and limited temperature sensor data. By
training  deep  learning  models  on  rich  source  domain  datasets
and  fine-tuning  them  on  target  domain  datasets,  the  study
successfully extended the applicability of the models to different
full-scale   tunnels   while   reducing   computational   resource
requirements.
Despite  these  advancements,  the  reliance  on  large  initial
datasets  before  implementation  remains  a  critical  limitation.
This paper  addresses  this gap by  incorporating online  learning
techniques with transfer learning, allowing the model to update
continuously  as  new  data  is  collected.  This  approach  not  only
mitigates the data scarcity issue at the beginning of underground
projects  but  also  ensures  that  the  model  remains  adaptable  to
changing  environmental  conditions,  ultimately  improving  the
accuracy  and  reliability of monitoring  systems  in  underground
environments.
## III. EXPERIMENTS AND RESULTS
This section presents the experimental setup, methodologies,
and  results  of  the  study  on  integrating  online  learning  and
transfer   learning   for   enhanced   underground multi-sensor
monitoring.
A. Description of Data Sources
The  first  dataset  used  to  train  the  baseline  LSTM  model
comes  from  an  open-source  dataset  collected  from a  longwall
underground  coal  mine  in  Poland.  It  covers  the  period  from
March  2,  2014,  to  June  16,  2014,  capturing  data  from  28
strategically   positioned   sensors   throughout   the   mine.   This
dataset  consists  of  9,199,930  samples  recorded  at  one-second
intervals and is notable for its completeness and reliability, with
no missing values. This dataset was initially introduced in [20].
In  this  paper,  data  from  five  methane  concentration  sensors,  a
wind speed sensor, and a temperature sensor, all located in the
working face, were used to train the baseline LSTM model.
## 126
Authorized licensed use limited to: Lulea University of Technology. Downloaded on December 25,2025 at 12:26:59 UTC from IEEE Xplore.  Restrictions apply.

A   second   dataset   was   utilized   for   training   the   online
forecasting  model. This  dataset  was obtained  from  a  longwall
underground   coal   mine   in   China.   The   dataset   included
measurements   from   five   methane   concentration   sensors,   a
temperature  sensor, and a  wind  speed  sensor  positioned  at  the
mine's  working  face.  Data  collection  spanned  from  January  3,
2022, to May 12, 2023, encompassing a total of 494 days. Data
were recorded at one-minute intervals, yielding average values
for each sensor, resulting in a dataset comprising 710,367 data
samples.
## B. Data Preprocessing
The  Polish  dataset  was  already  clean  and  free  of  missing
values. In contrast, the Chinese dataset contained missing values
marked as NaN. During data preprocessing, these missing values
were identified and imputed with the most recent valid values.
The  methane concentration sensors in the  Chinese mine were
subjected to regular testing with abnormal accumulation levels.
These  anomalies  were  identified  and  replaced  with previous
valid data    points. Given    the    sensitivity    of    methane
concentrations  near  the  working  face,  the  closest  methane
concentration  sensor  to  the  working  face  in  both  datasets  was
selected  as  the  target  variable.  To  ensure  consistency  between
the  two  datasets, the  order  of  the  sensors  in  each  dataset  was
synchronized based on the similarity of the type and location of
the  sensors. Additionally,  the  Polish  dataset,  which  had  an
original  data  interval  of  one  second,  was  resampled  to  one-
minute  intervals  by  averaging  the  data  points  within  each
minute. Finally,  sliding  time  windows  of  6 minutes were
constructed for both datasets.
## C. Baseline Model Training
Following the preprocessing stage, 153,393 minutes of data
from the Polish database were used to train an LSTM prediction
model. 80% of the initial data was used for the training process,
the next 10% for validating the prediction results, and the final
10% for testing the model.  This model consisted of two LSTM
layers and  two  dense  layers. Each of  these  hidden layers
contained  a  set  of  neurons,  transforming  the  information  from
the previous layer to the next layer [21]. The architecture of the
prediction  model  is  shown  in  Fig. 1.  The  ReLU  activation
function was used for its simplicity and effectiveness in making
the model non-linear. Additionally, the Adam optimizer with a
learning rate of 0.001 and the mean squared error loss function
were used to optimize the model's learning. The batch size was
set  to 256. Hyperparameters  such  as  the  number  of  neurons,
learning  rate,  and  batch  size  were  tuned  using  random  search,
which involved sampling from specified ranges and evaluating
model performance to identify the best combination.
The training process was conducted using the Keras package
in  Python [22]. The  Polish  data  was  fed  into  the  model  in
batches, and the model’s parameters were updated after each
batch to minimize the loss function. The model was trained for
a total of 50 epochs.
To evaluate the performance of the model, three metrics—
Mean Absolute Error (MAE), Mean Squared Error (MSE), and
Coefficient of Determination (R²)—were used. MAE calculates
the  average  of  the  absolute differences between  the  actual and
predicted  values.  MSE  computes  the  average  of  the  squared
differences between the actual and predicted values. R² measures
the proportion of the variance in the dependent variable that is
predictable from the independent variables. An R² score close to
1 indicates a high level of prediction accuracy, while for the first
two metrics, values closer to 0 are more favorable.
Fig. 2 shows the evolution of the training and validation loss
over the 50 epochs, indicating how well the model learned over
time.  The  model's  performance  on  the  validation  set  was
continuously monitored. The  model  with the  lowest  validation
loss was saved as the baseline model. The performance of this
baseline model was then evaluated using the test dataset. Fig. 3
presents a comparison between the actual and predicted methane
concentrations  on  the  test  dataset.  This  plot  illustrates  the
model's  ability to predict  methane  concentration accurately  on
the unseen test data. Additionally, the MAE, MSE, and R² values
were 0.02, 0.03, and 0.97, respectively.
## D. Online Transfer Learning
Online learning is a method of machine learning where the
model incrementally updates its parameters as new data appears
[23].  This  method  is  different  from  traditional  batch  learning
methods, which use the entire dataset at once to train the model.
Online learning is particularly useful for scenarios where data is
continuously  produced.  This  continuous  data  helps  the  model
dynamically  adapt  to  changing  conditions.  Therefore,  online
learning   is   a   suitable   tool   for   monitoring   and   predicting

Fig. 1. Architecture of the baseline LSTM model.

## Input1
st
## LSTM2
nd
## LSTM1
st
## Dense2
nd
DenseOutput
## ......
## 1
## 2
## 3
## 4
## 256
## ...
## 1
## 2
## 3
## 4
## 128
## ...
## 1
## 2
## 3
## 4
## 32
## 1

Fig. 2. Evolution of the training and validation loss of the baseline
LSTM model over epochs.

## 127
Authorized licensed use limited to: Lulea University of Technology. Downloaded on December 25,2025 at 12:26:59 UTC from IEEE Xplore.  Restrictions apply.

conditions  in  underground  environments  where  the  situation
changes rapidly.
In  this  section,  two  scenarios  were  explored  to  predict
methane  concentrations  in  a  Chinese  coal  mine  using  online
learning  with  LSTM  models.  In  the  first  scenario,  an  LSTM
model with the same architecture and hyperparameters depicted
in Fig. 1 was trained exclusively on the Chinese dataset without
any  pre-trained  baseline  model.  Sliding  time  windows  were
sequentially fed into the LSTM model to simulate real-time data
generation and  online  learning conditions.  In  this  way, as new
data  arrived,  the  model  updated  its  parameters  incrementally,
learning    continuously    from    the    incoming    data.    The
train_on_batch function  of  the  Keras  package  in  Python was
utilized for this purpose.
The performance of the LSTM model was evaluated at each
time step using MAE, MSE, and R² metrics. Fig. 4 illustrates the
actual  methane  concentrations  compared  to  those  predicted by
the  online  model.  Initially,  the  model’s performance   was
relatively  poor  due  to  the  lack  of  sufficient  training  data.
However,   as   more   data   were   processed,   the   performance
improved steadily. By the end of the learning process, the MAE
and MSE reached 0.01 and 0.0005, respectively, and R² showed
an acceptable value of 0.93.
In the second scenario, the online learning model benefited
from  transfer  learning  by  leveraging  the  baseline  model  pre-
trained on the Polish dataset. This pre-trained model served as a
starting  point,  providing  an  initial  set  of  parameters  aimed  at
improving the model’s performance during the early stages of
the  online  learning  process.  The  same  sliding  time  windows
were  used  to  update  the  model  with  the  Chinese  dataset,
allowing   it   to   adapt   to   the  new  data   while   retaining  the
knowledge from the Polish dataset.
The  final  results  of  the  online  model  evaluation  in  this
scenario  were  approximately  similar  to  the  results  obtained  in
the  first  scenario,  with  slightly  better metrics  for  the  second
scenario.  This  was  expected  due  to  the  significantly  larger
amount  of  data  in  the  Chinese  dataset  compared  to  the  Polish
dataset.  However,  a  notable  difference  between  the  prediction
results in the two scenarios was that the model with the baseline
achieved higher performance much faster than the model trained
from  scratch  in  the  first  scenario.  The  R
## 2
score  for  the  first
scenario after training the model with the initial 3000 data points
was 0.88, while this metric for the second scenario after the same
period was 0.94. The increase in the initial R
## 2
score compared to
the first scenario was due to the transferred knowledge from the
Polish  dataset,  leading  to  more  reliable  predictions  during  the
initial phase of online monitoring.
E. Discussion and Implications
The  online  transfer  learning  model,  which  was  initially
trained with data from a Polish mine and subsequently refined
using simulated real-time data from a Chinese mine, achieved an
R² score of approximately 0.93. This high accuracy underscores
the  model’s  effectiveness  in  capturing  intricate  temporal
patterns,  which  is  essential  for  reliable  methane  concentration
predictions. Compared to traditional methods, which often rely
heavily   on   extensive   pre-existing   datasets   and   encounter
challenges  with  adaptability,  this  approach  offers  significant
advancements. The model’s ability to rapidly adapt to new data
enhances  safety by enabling  timely  interventions  and reducing
accident risks.  Additionally,  it  improves operational  efficiency
by minimizing unnecessary shutdowns caused by false alarms,
thereby  saving  costs  and  boosting  productivity.  Integrating
historical  data  from  another  mine  to  refine  predictions  in  an
active  mine  demonstrates  the  model's  innovative  use  of  past
experiences to overcome data scarcity and improve monitoring
systems. This approach represents a practical enhancement over
existing  methods  by  addressing  limitations  related  to  data
availability and adaptability.
## IV. CONCLUSION
A baseline LSTM model was trained with open-source data
from  a  Polish  coal  mine.  This  model  was  then  incrementally
fine-tuned  using  an  online  learning  method  with  data  from  a
Chinese  coal  mine.  This  two-step  process  was  designed  to
leverage   transfer   learning  to  improve  the  model’s  initial
performance  and  adaptability.  The  baseline  model,  trained  on
the Polish dataset, provided a strong foundation, while the online
learning component allowed the model  to  continuously update
as new data became available from the Chinese mine.
The results indicated faster improvements in the prediction
accuracy   and   reliability   of   methane   concentration   levels.
Specifically, the model achieved an initial R² value of 0.94 when
using  the  pre-trained  baseline  model for  the  first  3000  data

Fig. 3. Comparison of actual and predicted values by baseline LSTM
model on testing set.

Fig. 4. Comparison of actual and predicted results by the online
LSTM model, without the baseline model.

## 128
Authorized licensed use limited to: Lulea University of Technology. Downloaded on December 25,2025 at 12:26:59 UTC from IEEE Xplore.  Restrictions apply.

points, while the initial R² value for the  online  learning model
without the baseline model was 0.88 for the same period. This
improved  performance  underscores  the  effectiveness  of  the
online  transfer  learning  model  in  addressing  the  initial  data
scarcity problem and maintaining high accuracy as more data are
collected.
This research    enhances    underground    monitoring    by
demonstrating   the   practical   application   of   online   transfer
learning   combined   with   multi-sensor   data   analysis.   The
developed model not only improves the safety and efficiency of
monitoring systems but also offers a  scalable  solution that  can
be  adapted  to  various  underground  settings.  By  continuously
updating the model with new data, this approach ensures that the
monitoring systems remain responsive to dynamic
environmental  conditions,  ultimately  enhancing  overall  risk
assessment and mitigation strategies in underground operations.
Future work will involve validating the approach across diverse
underground  sites,  incorporating  additional  hazardous  gases,
and    analyzing    the    model's    long-term    adaptability    and
performance.
## REFERENCES
[1] M. Q. Huang, J. Ninić, and Q. B. Zhang, "BIM, machine learning and
computer  vision  techniques  in  underground  construction:  Current  status
and future perspectives," Tunnelling and Underground Space Technology,
vol. 108, p. 103677, 2021/02/01/ 2021, doi:
https://doi.org/10.1016/j.tust.2020.103677.
[2] P. G. Ranjith, J. Zhao, M. Ju, R. V. S. De Silva, T. D. Rathnaweera, and
A. K. M. S. Bandara, "Opportunities and Challenges in Deep Mining: A
Brief Review," Engineering, vol. 3, no. 4, pp. 546-551, 2017/08/01/ 2017,
doi: https://doi.org/10.1016/J.ENG.2017.04.024.
[3] Y. Wu, M. Chen, K. Wang, and G. Fu, "A dynamic information platform
for  underground  coal  mine  safety  based  on  internet  of  things," Safety
Science, vol. 113, pp. 9-18, 2019/03/01/ 2019, doi:
https://doi.org/10.1016/j.ssci.2018.11.003.
[4] Y. Liang and Q. Liu, "Early warning and real-time control of construction
safety  risk  of  underground  engineering  based  on  building  information
modeling  and  internet  of  things," Neural  Computing  and  Applications,
vol. 34, no. 5, pp. 3433-3442, 2022/03/01 2022, doi:
https://doi.org/10.1007/s00521-021-05755-8.
[5] J. Brodny, D. Felka, and M. Tutak, "The use of the neuro-fuzzy model to
predict   the   methane   hazard   during   the   underground   coal   mining
production process," Journal of Cleaner Production, vol. 368, p. 133258,
2022/09/25/ 2022, doi: https://doi.org/10.1016/j.jclepro.2022.133258.
[6] S.   Rahimi,   M.   Ataee-pour,   H.   Madani,   and   S.   M.   Aminossadati,
"Investigating   the   impact   of   gas   emission   uncertainty   on   airflow
distribution  in  an  auxiliary  ventilation  system  using  CFD  and  Monte-
Carlo  simulation," Building  and  Environment, vol.  204,  p.  108165,
2021/10/15/ 2021, doi: https://doi.org/10.1016/j.buildenv.2021.108165.
[7] M.  Mousavi,  X.  Shen,  and  B.  Li,  "Online  Safety  Risk  Management  for
Underground  Mining  and  Construction  Based  on  IoT  and  Bayesian
Networks,"   presented   at   the   Proceedings   of   the   40th   International
Symposium on Automation and Robotics in Construction, Chennai, India,
## 2023/07/07, 2023.
[8] M.   Wang   and   X.   Yin,   "Construction   and   maintenance   of   urban
underground  infrastructure  with  digital  technologies," Automation  in
Construction, vol.    141,     p.    104464,    2022/09/01/    2022,     doi:
https://doi.org/10.1016/j.autcon.2022.104464.
[9] C. Zhou and L. Y. Ding, "Safety barrier warning system for underground
construction sites using Internet-of-Things technologies," Automation in
Construction, vol.    83,    pp.    372-389,    2017/11/01/    2017,    doi:
https://doi.org/10.1016/j.autcon.2017.07.005.
[10] M. Mousavi, X. Shen, Z. Zhang, K. Barati, and B. Li, "IoT-Bayes fusion:
Advancing real-time environmental safety risk monitoring in underground
mining  and  construction," Reliability Engineering  &  System Safety, vol.
256, p. 110760, 2025, doi: https://doi.org/10.1016/j.ress.2024.110760.
[11] D. Ślęzak et al., "A framework for learning and embedding multi-sensor
forecasting  models  into  a  decision  support  system:  A  case  study  of
methane  concentration  in  coal  mines," Information  Sciences, vol.  451-
452, pp. 112-133, 2018/07/01/ 2018, doi:
https://doi.org/10.1016/j.ins.2018.04.026.
[12] P. Stothard, A. Squelch, R. Stone, and E. Van Wyk, "Towards sustainable
mixed  reality  simulation  for  the  mining  industry," Mining  Technology,
vol. 128, no. 4, pp. 246-254, 2019/10/02 2019, doi:
## 10.1080/25726668.2019.1645519.
[13] X.  Meng,  H.  Chang,  and  X.  Wang,  "Methane  Concentration  Prediction
Method  Based  on  Deep  Learning  and  Classical  Time  Series  Analysis,"
Energies, vol. 15, no. 6, 2022, doi: https://doi.org/10.3390/en15062262.
[14] K. Zhang, H.-M. Lyu, S.-L. Shen, A. Zhou, and Z.-Y. Yin, "Evolutionary
hybrid  neural  network  approach  to  predict  shield  tunneling-induced
ground  settlements," Tunnelling  and  Underground  Space  Technology,
vol. 106, p. 103594, 2020/12/01/ 2020, doi:
https://doi.org/10.1016/j.tust.2020.103594.
[15] Y.  Peng,  D.  Song,  L.  Qiu,  H.  Wang,  X.  He,  and  Q.  Liu,  "Combined
Prediction  Model  of  Gas  Concentration  Based  on  Indicators  Dynamic
Optimization    and    Bi-LSTMs," Sensors,    vol.    23,    no.    6, doi:
## 10.3390/s23062883.
[16] A. Janusz, M. Grzegorowski, M. Michalak, Ł. Wróbel, M. Sikora, and D.
Ślęzak, "Predicting seismic events in coal mines based on underground
sensor     measurements," Engineering     Applications     of     Artificial
Intelligence, vol. 64, pp. 83-94, 2017/09/01/ 2017, doi:
https://doi.org/10.1016/j.engappai.2017.06.002.
[17]  S.  Sarkar  and  R.  Kelley,  "A  UAV  and  Deep  Transfer  Learning  Based
Environmental  Monitoring:  Application  to  Native  and  Invasive  Species
classification in Southern regions of the USA," in 2023 IEEE Conference
on Technologies for Sustainability (SusTech), 19-22 April 2023 2023, pp.
6-11, doi: 10.1109/SusTech57309.2023.10129545.
[18] Y.  Yang,  Q.  Cui,  R.  Cheng,  A.  Huo,  and  Y.  Wang,  "Retrieval  of  Soil
Heavy  Metal  Content  for  Environment  Monitoring  in  Mining  Area  via
Transfer Learning," Sustainability, vol. 15, no. 15, doi:
## 10.3390/su151511765.
[19] C.  Guo,  L.  Hu,  Y.  Zhang,  H.  Zhu,  and  Z.  Yan,  "Study  on  the  general
framework  for  real-time  heat  release  rate  inversion  of  tunnel  fires  with
deep learning and transfer learning," Tunnelling and Underground Space
Technology, vol.     148,     p.     105751,     2024/06/01/     2024,     doi:
https://doi.org/10.1016/j.tust.2024.105751.
[20] M. Kozielski, M. Sikora, and Ł. Wróbel, "Data on methane concentration
collected  by  underground  coal  mine  sensors," Data  in  Brief, vol.  39,  p.
107457, 2021/12/01/ 2021, doi:
https://doi.org/10.1016/j.dib.2021.107457.
[21] M. Mousavi, A. TohidiFar, and A. Alvanchi, "BIM and machine learning
in  seismic  damage  prediction  for  non-structural  exterior  infill  walls,"
Automation in Construction, vol. 139, p. 104288, 2022/07/01/ 2022, doi:
https://doi.org/10.1016/j.autcon.2022.104288.
[22] A. Gulli and S. Pal, Deep Learning with Keras. Packt Publishing, 2017.
[23] Q. Ren, M. Li, T. Kong, and J. Ma, "Multi-sensor real-time monitoring of
dam behavior using self-adaptive online sequential learning," Automation
in    Construction, vol.    140,    p.    104365,    2022/08/01/    2022,    doi:
https://doi.org/10.1016/j.autcon.2022.104365.

## 129
Authorized licensed use limited to: Lulea University of Technology. Downloaded on December 25,2025 at 12:26:59 UTC from IEEE Xplore.  Restrictions apply.