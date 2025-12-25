

## Enhancing  Workers’  Safety
and  Well-Being  in  Hazardous
Environments:  An  IoT-Based  Approach
## Anushka  Bukkawar,  Chandrashish  Kukrety,  Bhawesh  Mishra,
and  Biswajit  Dwivedy
Abstract  This  study  introduces  a  comprehensive  end-to-end  solution,  combining
hardware  and  software,  for  the  collection  and  analysis  of  critical  data  in  mining  envi-
ronments.  It  employs  an  Arduino-based  safety  helmet  to  gather  environmental  data
within  mines  and  subsequently  conducts  data  clustering.  The  analysis  of  data  from  a
Polish  mine,  as  a  proof  of  concept,  reveals  significant  findings.  It  shows  that  miners
were  consistently  exposed  to  high-temperature  environments  for  24.46%  of  their
work  hours,  high  humidity  conditions  for  23.39%,  and  elevated  methane  concentra-
tions  for  25.34%  of  the  time.  As  a  result,  extended  exposure  to  temperatures  above
ambient  mean  values  corresponds  to  a  12%  increase  in  heat-related  illnesses,  while
high  humidity  environments  lead  to  a  7%  rise  in  workplace  injuries.  Environments
with  a  high  methane  concentration  was  linked  to  an  increased  susceptibility  to  cardio-
vascular  diseases.  These  insights  highlight  the  potential  for  real-time  monitoring  and
hazard  mitigation,  offering  substantial  benefits  to  both  miners  and  employers.
Keywords  K-means  clustering ·Data  analytics ·IoT  (Internet  of  Things)
## 1   Introduction
The  well-being  and  safety  of  mine  workers  have  long  been  subjects  of  concern,  given
the  inherently  challenging  and  hazardous  conditions  they  face  within  the  mining  envi-
ronment  [
1].  In  recent  years,  the  rapid  advancement  of  the  Internet  of  Things  (IoT)
technology  has  introduced  transformative  possibilities  for  enhancing  the  safety  and
well-being  of  mine  workers.  By  integrating  IoT  devices  and  sensors  into  mining
operations,  real-time  monitoring  of  crucial  parameters  has  become  feasible,  thereby
## A.  Bukkawar · C.  Kukrety (
## B
## ) · B.  Mishra · B.  Dwivedy
School  of  Electronics  Engineering  (SENSE),  Vellore  Institute  of  Technology,  Vellore,  Tamil
## Nadu,  India
e-mail: chandrashish01@gmail.com
## B.  Dwivedy
e-mail:
biswajit.dwivedy.in@ieee.org
©  The  Author(s),  under  exclusive  license  to  Springer  Nature  Singapore  Pte  Ltd.  2025
S.  K.  Das  and  S.  K.  Behera  (eds.),  Recent  Trends  in  Intelligent  Systems  and  Next
Generation  Wireless  Communication,  Lecture  Notes  in  Networks  and  Systems  1329,
https://doi.org/10.1007/978-981-96-4741-5_15
## 165

166A. Bukkawar et al.
enabling  timely  responses  to  potential  hazards.  Following  this,  a  helmet  was  designed
consisting  of  temperature  and  humidity  sensors  to  take  real-time  readings  from  the
mine  [
2].  Another  such  helmet  was  proposed  which  employed  ATmega328  micro-
controller,  collision  sensor,  MQ5  gas  sensor,  humidity  sensor,  and  RF  transmitter
## [
3].  After  identifying  already  existing  hardware,  some  research  articles  have  also
been  identified  that  helped  to  understand  the  effect  of  increasing  temperature  in
several  workplaces  around  the  world.  A  study  aimed  to  explore  the  link  between
outdoor  temperatures  in  summer  and  job-based  heat-related  illnesses  was  conducted
in  Quebec,  Canada.  Compelling  statistics  analyzing  reported  heat-related  illnesses
revealed  that  a  1-degree  Celsius  temperature  increase  correlated  with  a  substantial
12%  rise  in  heat-related  illnesses  among  workers.  Remarkably,  risk  surged  at  specific
thresholds,  escalating  by  25%  at  30  degrees  Celsius  and  a  notable  45%  beyond  35
degrees  Celsius  [
4].  Another  research  investigates  the  association  between  very  high
heat  and  direct  heat-related  illnesses  in  Ningbo,  China.  Using  data  from  the  Chinese
Center  for  Disease  Control  and  Prevention’s  national  heat-related  illness  surveil-
lance  system,  the  research  analyzed  daily  heat-related  cases.  Both  mild  and  severe
cases  surge  during  extreme  temperature  periods,  especially  affecting  the  elderly  due
to  illness  severity  and  age  [
5].  In  another  research,  using  a  case-crossover  design,
injury  cases  were  reviewed,  coupled  with  meteorological  data  analysis  for  ambient
temperature  and  humidity  from  local  weather  stations.  The  study  underscored  that
temperatures  above  32  degrees  Celsius  correlated  with  a  2.5-fold  higher  risk,  with
a  30%  increase  during  afternoon  hours.  Task-specific  risks,  like  manual  labor  under
direct  sunlight,  were  also  identified  [
## 6
].  A  research  conducted  by  Miriam  Levi
et  al.  employed  three  targeted  search  strategies  in  PubMed,  focusing  on  heat-related
illness  and  other  conditions.  SCOPUS  and  EMBASE  were  also  utilized,  applying
specific  inclusion  and  exclusion  criteria.  Among  these,  six  out  of  eleven  articles
discussed  that  an  upsurge  in  chronic  kidney  disease  has  been  observed  since  the  early
## 2000s  [
## 7
].  Another  research  employed  workers’  compensation  claims  to  examine
injuries  related  to  workplace  in  Guangzhou,  China  (2011–2012)  during  warmer
seasons  (May–October).  Using  a  time-stratified  case-crossover  design,  conditional
Poisson  regression  models  were  employed.  Both  minimum  and  maximum  temper-
atures  exhibited  significant  associations  with  work-related  injuries  in  the  claims.  A
1  °C  rise  in  maximum  temperature  corresponded  to  a  1.4%  increase  in  daily  injury
claims  [
## 8
].  In  another  study,  they  performed  a  systematic  review  and  meta-analysis
adhering  to  PRISMA  guidelines  and  evaluated  occupational  heat  strain’s  impact  on
worker  health  and  productivity.  This  involved  comparing  heat  strain  occurrences
during  work  shifts  under  heat  stress  conditions  (WBGT,  26·2–26·4  °C;  air  tempera-
ture,  37·3–150·0  °C)  with  thermoneutral  conditions.  Workers  under  heat  stress  condi-
tions  faced  a  fourfold  higher  likelihood  of  experiencing  occupational  heat  strain  at  the
shift’s  end  compared  to  those  in  thermoneutral  conditions.  Notably,  a  14.5%  increase
in  urine  specific  gravity  was  observed  [
9].  The  research  examined  humidex’s  impact
on  injuries  in  Washington  State  Fund  outdoor  construction  workers.  Maximum  daily
humidex’s  connection  to  injuries  was  assessed  through  logistic  regression.  63,720
eligible  traumatic  injury  claims  were  identified.  Traumatic  injury  odds  were  1.005
(95%  CI  1.003–1.007)  per  one  °C  humidex  change  [
10].  Another  study  harnessed

Enhancing Workers’ Safety and Well-Being in Hazardous Environments ...167
data  from  the  Korean  National  Health  Insurance  Service  (KNHIS)  database  and  the
National  Statistical  Office  to  investigate  the  impact  of  heat  exposure  on  worker  health
in  Korea.  They  employed  generalized  additive  models  (GAM)  and  distributed  lag
nonlinear  models.  Elevated  MaxT  correlated  with  higher  overall  and  outdoor  death
risks.  Medical  facility  visits  increased  for  infectious  and  parasitic  diseases,  cardio
and  cerebrovascular  diseases,  genitourinary  system  diseases,  injury-related  cases,
and  the  effects  of  heat  and  light  for  each  1  °C  MaxT  increase  [
11].  High  methane
concentration  environments  were  also  linked  to  increased  risks  of  cardiovascular
diseases  [
12].  The  reviewed  studies  collectively  explore  the  relationship  between
heat  exposure  and  health  outcomes  in  various  occupational  settings.  The  research
emphasizes  a  consistent  association  between  increased  temperatures  and  higher
risks  of  heat-related  illnesses  and  injuries  among  workers.  Notably,  vulnerability
varies  across  demographic  groups  with  certain  sectors  being  particularly  affected.
Research  reviewed  existing  literature  regarding  heat-related  workplace  injuries.  It
high-lighted  the  urgency  of  addressing  heat-related  occupational  health  challenges,
given  the  expected  rise  in  temperatures  and  extreme  events.  Effective  strategies
should  be  enforced.  Collaboration  across  disciplines  and  inclusive  participation  is
crucial,  requiring  approaches  led  by  occupational  health  experts  [
## 13].
The  mining  industry,  a  pivotal  component  of  global  economies,  has  historically
been  recognized  as  a  hazardous  occupation.  Despite  its  longstanding  status  as  a
major  heavy  industry,  it  continues  to  pose  significant  risks  to  workers,  as  high-
lighted  by  the  International  Labor  Organization  (ILO).  This  study  utilizes  exten-
sive  medical  datasets  and  records  from  analogous  operations  to  identify  emerging
illnesses  attributed  to  prolonged  exposure  to  harsh  working  conditions.  The  predom-
inant  etiological  factor  for  the  majority  of  these  maladies  is  identified  as  inadequate
working  conditions.  The  research  proposes  a  potential  methodology  aimed  at  early
detection  and  prediction  of  diseases  through  the  systematic  monitoring  of  workers’
working  conditions.  This  proactive  approach  seeks  to  empower  workers  with  aware-
ness  regarding  their  occupational  environment,  thereby  facilitating  the  prevention
of  these  ailments.  A  comprehensive  inference  from  various  literature  is  shown  in
## Table
## 1.
Table  1   Relationship  between  increase  in  physical  parameters  and  diseases
## Ref.no
ParameterRisk
## [4
## ]
1°C  increase  in  average  temperature
and  average  temperature  over  35°C
12%  increased  risk  of  heat  related  illness  and  45%
increased  risk  of  heat-related  illness,  respectively
## [7
## ]
1°C  increase  in  daily  minimum
temperaTure
1%  increase  in  odds  of  injury
## [9]
Long  work  duration  in  heat  stress
conditions
4  times  more  likely  to  suffer  from  occupational
heat  strain
## [11
## ]
1°C  Rise  in  average  temperatureIncreased  cases  of  cardio  and  cerebrovascular
diseases

168A. Bukkawar et al.
2   Design  and  Implementation
This  research  endeavors  to  address  the  multifarious  safety  concerns  prevalent  in
mining  operations  by  proposing  the  development  and  implementation  of  an  advanced
safety  helmet.  This  innovative  helmet  is  equipped  with  an  array  of  sensors,  including
an  Orientation  and  Acceleration  Sensor,  a  methane  gas  sensor,  a  temperature  and
humidity  sensor,  and  a  GPS  module.  The  hardware  underpinning  this  safety  helmet
is  founded  upon  the  robust  Arduino  Uno  microcontroller,  establishing  itself  as  the
central  processing  unit  responsible  for  aggregating  data  from  the  array  of  sensors.  The
primary  objective  of  the  helmet  revolves  around  the  real-time  acquisition  and  trans-
mission  of  critical  data  to  facilitate  the  prompt  detection  of  potential  hazards,  thereby
enabling  timely  intervention  when  necessary.  Furthermore,  the  data  collected  by  this
device  serves  the  dual  purpose  of  generating  personalized  datasets  for  individual
miners,  thus  maintaining  an  accurate  medical  history  documenting  their  exposure  to
environmental  conditions.
Subsequently,  this  amalgamated  data  is  seamlessly  transmitted  to  a  cloud-based
service,  where  it  finds  its  repository  for  visualization  and  rigorous  data  processing.
For  this  project,  an  IoT  platform  called  KaaIoT  was  used  to  store  the  data  collected
by  the  helmet.  However,  implementations  with  local  storage  servers  to  maintain  the
privacy  of  the  workers  can  be  easily  arranged.  The  block  diagram  for  the  system  can
be  seen  in  Fig.
-  Within  the  cloud  environment,  the  data  undergoes  visualization
processes  facilitated  by  a  dedicated  dashboard  service.  This,  in  turn,  empowers  mine
supervisors  and  safety  personnel  to  closely  monitor  the  real-time  activities  of  miners
within  the  subterranean  confines,  thereby  enabling  swift  intervention  in  the  event  of
any  detected  anomalies.  The  data  transmitted  to  the  cloud  is  then  analyzed  to  infer
its  effect  on  the  health  of  the  miners.
Fig.  1  Block  diagram  of  the  proposed  safety  helmet  system  for  miners

Enhancing Workers’ Safety and Well-Being in Hazardous Environments ...169
Fig.  2  Prototype  circuit  of
the  proposed  helmet  system
The designed helmet is not used to generate a dataset. Even though the circuit of the
helmet  has  been  tested  in  real  time,  the  entire  system  has  yet  to  be  tested  in  a  mining
application.  All  the  components  used  in  the  circuit  have  a  standard  operating  range
from  –40  °C  to  75  °C,  which  makes  them  to  be  used  in  mining  conditions.  Rather,  a
similar  dataset  from  a  mine  in  Poland  was  utilized  to  be  used  for  the  deployment  of  the
clustering  algorithm-based  analysis.  The  dataset  features  readings  that  were  recorded
at  a  frequency  of  1  Hz  over  a  period  spanning  107  days.  The  focus  within  this  dataset
was  directed  toward  a  select  subset  of  readings  obtained  from  a  single  temperature
sensor  named  TP1721,  one  humidity  sensor  named  RH1712,  and  a  methane  sensor
named  MM261.
The  daily  data  is  subjected  to  the  K-means  clustering  algorithm.  The  optimum
number  of  clusters  is  calculated  using  the  Gap-Statistic  method  where  the  within-
cluster  variation  of  the  data  is  compared  for  different  values  of  k  (the  number  of
clusters)  with  the  expected  variation  under  a  null  reference  distribution.  The  optimal
number  of  clusters  is  typically  the  one  where  the  gap  statistic  is  maximized.
Post-clustering,  clusters  were  discerned  based  on  their  respective  centroid  values.
The first and third quartile values for each of the three centroid fields namely humidity,
temperature,  and  methane  concentration  were  calculated.  Subsequently,  centroids
were  assigned  categorical  labels,  namely  “High,”  “Medium,”  or  “Low,”  contingent
upon  their  positioning  relative  to  the  third  quartile  value,  within  the  inter-quartile
range,  or  below  the  first  quartile  value,  respectively.
The  categorized  clusters  visualized  in  Figs. 3, 4,  and 5 were  subsequently  prepared
for  utilization  in  the  identification  and  correlation  with  diseases.  This  application
entails  the  use  of  pre-existing  datasets,  as  well  as  the  potential  inclusion  of  novel
datasets  intended  for  classifying  diseases  arising  from  prolonged  exposure  to  specific
environmental  conditions.

170A. Bukkawar et al.
Fig.  3  Histogram  plot  of
density  of  classification  tag
versus  humidity  data
Fig.  4  Histogram  plot  of
density  of  classification  tag
versus  temperature  data
Significantly,  the  findings  uncovered  a  substantial  increase  in  the  risk  of
various  disease  manifestations  as  a  consequence  of  prolonged  exposure  to  elevated
temperatures  and  heightened  humidity  levels.
## 3   Dataset  Description
The  dataset  under  scrutiny  originates  from  an  underground  coal  mine  in  Poland,  span-
ning  a  period  between  March  2,  2014  and  June  16,  2014,  and  comprising  a  substan-
tial  9,199,930  data  examples  [
14].  Each  example  is  characterized  by  a  timestamp,

Enhancing Workers’ Safety and Well-Being in Hazardous Environments ...171
Fig.  5  Histogram  plot  of
density  of  classification  tag
versus  methane
concentration  data
Table  2   Sensors  used  for
data  analytics
Sensor  name
ParameterMinimum Maximum
## TP1721
Temperature0°C27.9  °C
RH1712Relative  humidity0%86%
## MM261
Methane  concentration 0%30%
consisting  of  six  attributes  (year,  month,  day,  hour,  minute,  second),  and  measure-
ments  acquired  from  28  distinct  sensors.  This  data  is  meticulously  sampled  at  one-
second  intervals  and  is  presented  in  a  CSV  format.  Three  out  of  the  28  sensors  have
been  selected  to  perform  data  analytical  operations.  The  mentioned  sensors  are  shown
in  Table
-  Standardization  procedures  were  applied  to  ensure  all  measurements
corresponded  to  one-second  intervals,  with  missing  cutter  loader  values  replaced  by
“0”  to  signify  no  work,  and  missing  sensor  values  substituted  with  the  last  known
value.  Importantly,  there  are  no  missing  values  in  the  continuous  operation  of  the
methane  systems,  reflecting  the  critical  nature  of  maintaining  uninterrupted  data
streams  for  safety  and  monitoring  in  underground  coal  mines.
4   Results  and  Discussion
The  analysis  of  the  clustered  dataset  has  revealed  several  important  findings.  A
sample  plot  depicting  the  clusters  formed  on  2014/04/01  is  shown  in  Fig.
## 6.  Similar
clustering  was  performed  on  daily  datasets,  leading  to  multiple  significant  insights.
A  partial  representation  of  the  clustered  dataset  and  its  corresponding  classifica-
tion  is  displayed  in  Fig.
-  After  the  classification,  it  became  evident  that  the  mine

172A. Bukkawar et al.
Fig.  6  Visualization  of  clusters  for  a  typical  day  (2014/04/01)
workers  were  exposed  to  high  environmental  factors  for  substantial  durations.  Specif-
ically,  they  experienced  high  temperatures  for  24.46%  of  their  working  time,  high
humidity  for  23.39%,  and  elevated  methane  concentrations  for  25.34%  of  their  work
hours.  These  findings  strongly  indicate  that  the  workforce  consistently  encountered
environmental  conditions  significantly  above  the  average  ambient  values  for  these
parameters.
It is worth noting that in the context of Canadian laborers, a 1°C increase in ambient
temperatures  is  associated  with  a  statistically  significant  12%  rise  in  the  incidence
of  heat-related  illnesses  among  workers.  Elevated  humidity  levels  are  linked  to  a  7%
increase  in  the  risk  of  workplace  injuries.  Furthermore,  exposure  to  high  methane
concentrations  has  been  associated  with  an  increased  risk  of  cardiovascular  diseases.
Therefore,  it  can  be  inferred  that  the  workers  in  this  Polish  mine  were  subjected  to
working  conditions  that  have  been  associated  with  various  health-related  issues  and
risks.  This  information  underscores  the  need  for  further  investigation  and  potential
intervention  to  ensure  the  safety  and  well-being  of  these  workers.  It  is  expected  that
with  further  analysis  of  the  health  data  of  the  workers,  the  damage  caused  to  the
workers  due  to  the  working  conditions  can  be  reduced  by  taking  measures  to  prevent
exposure  to  harsh  conditions.

Enhancing Workers’ Safety and Well-Being in Hazardous Environments ...173
Fig.  7  Section  of  the  processed  and  classified  dataset
## 5   Conclusion
A  safety  helmet  was  designed  successfully  which  was  able  to  create  a  dataset  that
could  be  used  for  data  analytics.  Using  the  available  dataset  of  a  mine,  meticu-
lous  analysis  was  done  to  reveal  that  variation  in  physical  parameters  adversely
affected  the  health  of  workers.  Further  collection  and  analysis  of  location-specific
health  data,  in  conjunction  with  the  corresponding  physical  parameters,  will  facili-
tate  a  more  robust  correlation  between  diseases  and  workplace  conditions,  ultimately
contributing  to  the  establishment  of  safer  environments  for  high-risk  occupations.
This  research  aims  to  propose  a  system  that  can  be  utilized  by  the  industry,  to  keep
track  of  the  working  conditions  of  its  employees,  so  that  any  possible  diseases  can
be  predicted  for  the  employees,  and  preventive  measures  can  be  employed.  More-
over,  the  designed  model  can  also  be  deployed  in  parallel  high-risk  industries  such
as  construction  and  manufacturing  to  provide  a  safer  working  environment  to  the
workers  and  minimize  the  risk  of  unknowingly  dangerous  working  conditions.
## References
- Mining:  a  hazardous  work. https://www.ilo.org/global/topics/safety-and-health-at-work/areaso
fwork/hazardous-work/WCMS_356567/lang--en/index.htm
- Khamis  YI,  Alawi  M,  Athumani  R,  Sanya  WM  (2022)  An  iot  based  worker  safety  helmet  using
cloud  computing  technology.  Tanzan  J  Eng  Technol  41(1)
- Suriyakrishnaan  K  et  al  (2021)  Smart  safety  helmet  in  coal  mining  using  arduino.  Turk  J
Comput  Math  Educ  (TURCOMAT)  12(11):5481–5486

174A. Bukkawar et al.
- Adam-Poupart  A,  Smargiassi  A,  Busque  MA,  Duguay  P,  Fournier  M,  Zayed  J,  Labrèche  F
(2014) Summer outdoor temperature and occupational heat-related illnesses in quebec (canada).
## Environ  Res  134,  339–344
- Bai  L,  Ding  G,  Gu  S,  Bi  P,  Su  B,  Qin  D,  Xu  G,  Liu  Q  (2014)  The  effects  of  summer  temperature
and  heat  waves  on  heat-related  illness  in  a  coastal  city  of  china,  2011–2013.  Environ  Res
## 132:212–219
- Spector  JT,  Bonauto  DK,  Sheppard  L,  Busch-Isaksen  T,  Calkins  M,  Adams  D,  Lieblich
M,  Fenske  RA  (2016)  A  case-crossover  study  of  heat  exposure  and  injury  risk  in  outdoor
agricultural  workers.  PLoS  ONE  11(10):e0164498
- Levi  M,  Kjellstrom  T,  Baldasseroni  A  (2018)  Impact  of  climate  change  on  occupa- tional
health  and  productivity:  a  systematic  literature  review  focusing  on  workplace  heat.  Med  Lav
## 109(3):163
- Sheng  R,  Li  C,  Wang  Q,  Yang  L,  Bao  J,  Wang  K,  Ma  R,  Gao  C,  Lin  S,  Zhang  Y  et  al  (2018)
Does  hot  weather  affect  work-related  injury?  a  case-crossover  study  in  guangzhou,  china.  Int
## J  Hyg  Environ  Health  221(3):423–428
- Flouris  AD,  Dinas  PC,  Ioannou  LG,  Nybo  L,  Havenith  G,  Kenny  GP,  Kjellstrom  T  (2018)
Workers’  health  and  productivity  under  occupational  heat  strain:  a  systematic  review  and  meta-
analysis.  The  Lancet  Planetary  Health  2(12):e521–e531
- Calkins  MM,  Bonauto  D,  Hajat  A,  Lieblich  M,  Seixas  N,  Sheppard  L,  Spector  JT  (2019)  A
case-crossover  study  of  heat  exposure  and  injury  risk  among  out- door  construction  workers  in
washington  state.  Scand  J  Work  Environ  Health  45(6):588–599
- Yoon  JH,  Lee  WT,  Yoon  MJ,  Lee  W  (2021)  Risk  of  heat-related  mortality,  disease,  accident,  and
injury  among  korean  workers:  a  national  representative  study  from  2002  to  2015.  Geohealth
5(12):e2021GH000516
- Mendoza-Cano  O,  Trujillo  X,  Huerta  M,  Ríos-Silva  M,  Lugo-Radillo  A,  Bricio-Barrios  JA,
Rueda-Abad  JC,  Pérez-Rodríguez  RY,  Quintanilla- Montoya  AL,  Uribe-Ramos  JM  et  al
(2023)  Assessing  the  relationship  between  energy-related  methane  emissions  and  the  burden
of  cardiovascular  diseases:  a  cross-sectional  study  of  73  countries.  Sci  Rep  13(1):13515
- Spector  JT,  Masuda  YJ,  Wolff  NH,  Calkins  M,  Seixas  N  (2019)  Heat  exposure  and  occupational
injuries:  review  of  the  literature  and  implications.  Curr  Environ  Health  Rep  6:286–296
- Kozielski  M,  Sikora  M, Łukasz  W  (2021)  Data  on  methane  concentration  collected  by  under-
ground  coal  mine  sensors.  Data  Brief  39:107457.
https://www.sciencedirect.com/science/art
icle/pii/S2352340921007393