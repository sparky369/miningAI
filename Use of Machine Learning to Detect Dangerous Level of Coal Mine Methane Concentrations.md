

## Academic Editor: Stefano Mariani
## Published: 7 November 2025
Citation:Mooroogen, R.; Ayomoh,
M.K. Use of Machine Learning to
Detect Dangerous Level of Coal Mine
Methane (CMM) Concentrations
## During Underground Mining
Operations.Eng. Proc.2025,118, 80.
https://doi.org/10.3390/
## ECSA-12-26591
Copyright:© 2025 by the authors.
Licensee MDPI, Basel, Switzerland.
This article is an open access article
distributed under the terms and
conditions of the Creative Commons
Attribution (CC BY) license
## (https://creativecommons.org/
licenses/by/4.0/).
## Proceeding Paper
Use of Machine Learning to Detect Dangerous Level of Coal
Mine Methane (CMM) Concentrations During Underground
## Mining Operations
## †
## Rubeshen Mooroogen
and Michael K. Ayomoh *
Department of Industrial & Systems Engineering, University of Pretoria, Hatfield, Pretoria 0028, South Africa;
mrubeshen@gmail.com
*Correspondence: michael.ayomoh@up.ac.za
## †
Presented at the 12th International Electronic Conference on Sensors and Applications, 12–14 November 2025;
Available online: https://sciforum.net/event/ECSA-12.
## Abstract
Underground coal mining is considered to be a highly dangerous activity and has been
responsible for large amounts of accidents, causing the death of many mine workers. One of
the factors responsible for the fatal aspect of underground coal mining is the presence and
accumulation of toxic gases during underground mining operations. This paper focused its
investigation specifically on coal mine methane (CMM), which is released as a result of the
extraction of coal and the disturbance inflicted to surrounding rock formations during deep
mining operations. Methane is considered a highly dangerous gas as it holds the capacity
to cause explosions due to its highly inflammable nature. It can also displace oxygen, which
eventually leads to asphyxiation. This research was based on the use of machine learning
models to successfully predict dangerous concentrations of methane over the authorized
threshold.  Those predictions were made from a dataset containing information on the
temperature, airflow, humidity, pressure and methane concentration in an underground
coal mine. The temperature, airflow, humidity and pressure measurements were recorded
by a series of sensors, namely anemometers and component sensors THP2/93.  Three
machine learning classification models were implemented and compared, with the objective
to find the best model to predict and detect dangerous levels of coal mine methane. The
models  that  were  investigated  included  naïve  Bayes,  logistic  regression  and  artificial
neural networks (ANNs). This paper concludes with an engineering decision matrix that
illustrates the precision of these models in predicting and detecting dangerous levels
of methane concentrations in underground mines.  Furthermore, recommendations for
capacity improvement towards successfully predicting and detecting dangerous levels of
coal mine methane from an artificial intelligence’s perspective are provided.
Keywords:coal mine methane (CMM); machine learning; artificial intelligence; sensors
## 1. Introduction
There are three types of mining operations to extract ores. These types of operations
are notably open surface mining, deep mining and sea water mining. As for deep mining,
also  known  as  underground  mining  operations,  the  most  common  technique  used  is
longwall mining because it is considered the safest and most productive technique [1].
However,  past research clearly demonstrates that this specific technique of extraction
releases high and dangerous concentrations of methane,  also referred to as coal mine
Eng. Proc.2025,118, 80https://doi.org/10.3390/ECSA-12-26591

## Eng. Proc.2025,118, 80
2 of 12
methane (CMM), in the surrounding underground environment [2]. CMM, owing to its
inflammable nature, has been responsible for a large number of lethal explosions around the
world. A document signed by the United Nations detailed those fatal accidents as follows:
214 deaths on 14 February 2005 in the Sunjlawan mine of China; 108 deaths on 19 March
2007 in Ulyanovskaya mine of Russia; 80 deaths on 19 November 2007 in Zasyadko mine
of Ukraine; 43 deaths on 20 September 2006 in Lenina mine of Kazakhstan; 29 fatalities in
Upper Big Branch, West Virginia, United states of America, on 5 April 2010; and 12 deaths
also in West Virginia, most precisely in Sago, on 14 February 2005 [3]. As a result, CMM
explosions are considered amongst the most lethal accidents when it comes to underground
or deep mining operations, hindering the safety and productivity of mining environments
as well as its industry.  One way to ensure that the concentration of coal mine methane
does not exceed the safe and permissible threshold is the use of ventilation.  According
to a study performed on the safety of longwall mining, researchers supported the use of
ventilation as the most effective method for the control of gases, with a special focus on
coal mine methane, known to be present and released in large volumes during longwall
mining activities [4].
To achieve optimal ventilation in underground mining regions, it is important to
localize the regions that present high concentrations of CMM. This is achieved by the
implementation of a sensing and metrification strategy. Since the concentration of CMM
is largely attributed to its capacity to accumulate and disperse, which itself is dependent
on physical  parameters like  temperature,  humidity,  pressure and  airflow,  sensors  are
placed in various locations of underground mines to collect data, which contributes to
better  management  of  CMM  through  optimal  ventilation  usage.   The  type  of  sensors
commonly used are normally threshold triggering and continuous monitoring. Threshold
triggering sensors normally emit an output whenever the measured parameter exceeds the
permissible threshold. On the other hand, continuous monitoring sensors collect real-time
data over a period of time. The use of triggering sensors in the management of CMM in
underground mining conditions comes with its own set of challenges and disadvantages
that compromise the safety of the mines as well as their productivity. Triggering sensors
emit an alarm only when the maximum permissible CMM threshold has been exceeded.
This type of system only allows for reactive measures, which leave little to no time to
respond efficiently to a hazardous situation.  This can lead to a fatal occurrence in the
case of late activation of the sensors.  Past studies demonstrate that under deep mining
conditions, the response time of a sensor varies between 210 and 257 s while the recovery
time sits between 142 and 241 s [5]. These data clearly show that it takes too much time
for a triggering sensor to pick up high concentrations of CMM, hence increasing the risk
of explosions in underground mines. A study focused on the influence of environmental
factors like humidity, alongside pressure, concluded that those natural factors interfere
with the capacity of these sensors by introducing an element of delay leading to late
alarms [6]. As a result, the reactive cognition aspect of the methane management system
is heavily compromised and highly hazardous and dangerous situations are not dealt
with appropriately, leading to explosions.  To improve the detection of CMM, artificial
intelligence models are employed to predict dangerous concentrations of CMM with a high
level of precision and accuracy. This improves the cognition attribute of underground CMM
management by replacing reactive decisions with proactive ones. Tutak, Krenicky, Pirnik,
Brodny and Grebski proposed a Multi-Layer Perceptron Neural Network for predictions of
CMM in underground coal mining [7]. This research was focused on longwall mining and
concluded that it was possible to generate forecasts of CMM with a high level of accuracy.
According this paper, predictions made within a forecast window ranging from 5 to 60 min
were considered as acceptable.  A different study performed in China, most precisely at

## Eng. Proc.2025,118, 80
3 of 12
the Buertai Coal Mine, proposed a prediction model for methane concentration, namely an
Improved Black Kite Algorithm (BKA) working together with an Informer Bidirectional
Long Short Term Memory algorithm [8].  This proposed algorithm made use of several
features, which include historical data on methane concentrations, temperature as well as
wind speed, and results obtained indicated a high predictive accuracy of the model in terms
of convergence and speed as well as an elevated degree of robustness. Nie et al. [9] studied
the characteristics of the surrounding mining environment with the objective of better
understanding the manner in which CMM spreads in underground mines. This allowed
the researchers to present a methane prediction model based on the Gaussian plume model,
genetic algorithms and BP neural networks (Back Propagation Neural Network).  This
model presented a high level of accuracy in monitoring the level of CMM and is considered
reliable due to its ability to continuously train on daily real-time data. Another machine
learning technique that was used successfully in methane prediction is the support vector
machine algorithm [10]. This research focused on building a multi-sensor prediction model
for methane predictions by combining methodologies from information fusion alongside
support vector machines. To achieve a high predictive accuracy of coal mine methane, it is
common and highly advisable to use a palette of features as demonstrated by Zhiqiang
Luo et al. [11] in building their eXtreme Gradient Boosting algorithm (XG Boost). For this
model, the researchers chose to make sure that natural parameters like temperature and
past historical data of methane concentrations were used to train and test their machine
learning models. The results obtained indicated that the tested models had faster training
speeds compared to existing ones and a lower percentage of prediction errors.
From the above, it is clear that a robust artificial intelligent mode with a high degree
of accuracy can successfully predict dangerous concentrations of methane, enhancing the
safety of underground mining operations. This paper analyzed the computational ability
and reliability of three machine learning classification models that successfully predict and
classify dangerous concentrations of coal mine methane in underground mines. Those three
machine learning classification models are naïve Bayes, logistic regression and artificial
neural network. The aim of this paper is to perform a comparative analysis of these three
algorithms in regard to their capacity to predict dangerous levels of concentrations of
CMM with a high degree of accuracy. This paper, with the results obtained, will lay the
foundation for building improved machine learning algorithms with higher degrees of
accuracy in regard to the prediction of dangerous concentrations of CMM.
## 2. Research Methodology
The research methodology is divided into two parts: the first part being preparing the
sensing dataset in order to be used as input for the classification models and the second
part being the design and implementation of the three above discussed machine learning
classification models.
2.1. Description of the Sensing Data and Machine Learning Algorithms
This study investigated and compared the use of three machine learning classification
models, namely naïve Bayes, logistic regression and artificial neural network to predict
and efficiently classify concentrations of methane into safe and unsafe categories. These
predictions were made based on data from sensing data:  past historical concentrations
of  methane,  temperature,  humidity,  airflow  and  pressure.   These  data  were  obtained
from 28 different sensors placed at different locations in the underground mine [12]. The
underground mine that was used for this study is located in the Upper Silesian coal basin,
in the region of Voivodeship in Poland. The data was recorded every 1 s, and two groups
of data were recorded, with the first one focusing on climatic parameters like temperature

## Eng. Proc.2025,118, 80
4 of 12
and the second group focusing on activities focusing on the cutter loader operation. For
the purpose of this research paper, only the climatic conditions of temperature, pressure,
humidity and airflow were considered as input to the different machine learning models.
This is in line with the philosophy of the research to test the predictability of those machine
learning models from a pure climatic and environmental perspective before introducing
other input that relate to the human activities performed in mines. The following section
depicts the data handling procedure of this research:
1.The dataset was cleaned to ensure that there were no missing values, and any dupli-
cated readings were removed.
2.The required features that will serve as input to the machine learning classification
models were selected. Those features are pressure, temperature, humidity and airflow.
3.The required methane meters and associated historical data were selected as output.
4.Based on a chosen threshold (e.g., 1.0), methane’s concentration was classified as safe
and unsafe.
5.Checks were performed on different portions of the dataset to check the number of
safe and unsafe cases in each data cluster.
6.The data were used as input to three different machine learning classification models.
Those models are naïve Bayes, logistic regression and artificial neural networks.
7.The classification report was then printed out to display the values for the statistical
parameters.
The following section addresses the development of the three machine learning classi-
fication algorithms that are deployed for this research.
## 2.1.1. Naïve Bayes Machine Learning Classification Model
The naïve Bayes classification model is used as a first baseline model for the purpose
of this research and is based on the assumption of attribute independence. This means that
all the features or attributes are not related to each other.  Naïve Bayes is built from the
Bayes theorem, as shown below by Equation (1):
## P
## (
## C
## |
## X
## )
## =
## P
## (
## X
## |
## C
## )
## ×P
## (
## C
## )
## P
## (
## X
## )
## (1)
The Bayes theorem above consists of two parameters, which areCandX.Crepresents
the class that needs to be predicted, whileXrepresents the different features that are used as
inputs.P
## (
## C
## |
## X
## )
indicates the probability of an eventChappening givenXhas happened. In
order to form the naïve Bayes equation, it is assumed that each feature ofxis independent
of each other, giving the following equation:
## P
## (
x
## 1
## ,x
## 2
## , . . . ,x
n
## |
## C
## )
## =
## P
## (
## C
## )
## ×
## ∏
n
i=1
## P
## (
x
i
## |
## C
## )
## P
## (
x
## 1
## ,x
## 2
## , . . . ,x
n
## )
## (2)
For the purpose of this study, thexparameter will relate to the climatic conditions
of the underground mine, which are temperature, pressure, airflow and humidity.Cwill
relate to the different categories of CMM concentrations in underground mines.   Two
categories will be used for this paper, and they are safe and unsafe.  The purpose of the
naïve Bayes classification algorithm will be to use the different input parameters such as
temperature, pressure, humidity and airflow to predict and classify CMM concentrations
as safe or unsafe.
Algorithm 1, as shown below, illustrates the pseudo code for the proposed model
that was built to implement the naïve Bayes algorithm for predicting and classifying the
concentrations of CMM as safe or unsafe during underground mining operations.

## Eng. Proc.2025,118, 80
5 of 12
Algorithm 1:Pseudo code for the proposed detection of dangerous level of coal mine
methane based on a Naïve-Bayes classifier
Input: sensor data (methane_1, methane_2, methane_3, temperature, pressure, airflow,
humidity).
Output: Accuracy, Precision, recall, f1-score, support.
## BEGIN
LOADcsv_file→df
Sample size←size (df)
FOReach row in df, D
mean _ methane←(methane_1 + methane_2 + methane_3)/3
df [‘average methane’]←mean_methane
IFmean_methane > 1 THEN
condition←“Unsafe”
## ELSE
conditon←“Safe”
## END IF
df [‘condition’]←condition
## END FOR
FILTERdf to RETAIN:
{seconds, temperature, airflow,pressure, humidity,methane_1,methane_2,
methane_3, average_methane,condition}
DISPLAYhead (df)
X←{ seconds, temperature, airflow, pressure, humidity, methane_1,methane_2
methane_3, average_,methane, condition}
## Y←condition
## ENCODEY:
## Safe = 0
## Unsafe = 1
SPLITdatasetINTO( X_train, Y_train) and (X_test, Y_test)WITHratio 70:30
MODEL←GaussianNaiveBayes()
FIT MODEL ON (X_train,Y_train)
Y_pred←PREDICT MODEL ON X_test
## COMPUTE:
Accuracy (Y_test, Y_pred)
Precision (Y_test, Y_pred)
Recall (Y_test, Y_pred)
F1-Score (Y_test, Y_pred)
Support (Y_test, Y_pred)
## END
## 2.1.2. Logistic Regression Machine Learning Classification Model
The second model that was implemented is known as the logistic regression classi-
fication model. This model is, by nature, a statistical classification model which outputs
a probability that sits between zero and one. Compared to naïve Bayes, this model does
not require the assumption of independence between the input features, hence making it a
more robust alternative compared to the previous model.
Algorithm 2 as shown below, illustrates the proposed model that was built to imple-
ment the logistic regression algorithm in predicting and classifying the concentrations of
CMM as safe or unsafe during underground mining operations.

## Eng. Proc.2025,118, 80
6 of 12
Algorithm 2:Pseudo code for the proposed detection of dangerous level of coal mine
methane based on a Logistic Regression classifier
Input: sensor data (methane_1, methane_2, methane_3,temperature, pressure, airflow,
humidity).
Output: Accuracy, Precision, recall, f1-score, support.
## BEGIN
LOADcsv_file→df
Sample size←size (df)
FOReach row in df, D
mean _ methane←(methane_1 + methane_2 + methane_3)/3
df [‘average methane’]←mean_methane
IFmean_methane > 1 THEN
condition←“Unsafe”
## ELSE
conditon←“Safe”
## END IF
df [‘condition’]←condition
## END FOR
FILTERdf to RETAIN:
{seconds, temperature, airflow,pressure, humidity,methane_1,methane_2,
methane_3, average_methane,condition}
DISPLAYhead (df)
X←{ seconds, temperature, airflow, pressure, humidity, methane_1,methane_2
methane_3, average_,methane, condition}
## Y←condition
## ENCODEY:
## Safe = 0
## Unsafe = 1
SPLITdatasetINTO( X_train, Y_train) and (X_test, Y_test)WITHratio 70:30
MODEL←LogisticRegression (
class_weight = “balanced”,
max_iter = 10000
solver = “liblinear”)
## )
FIT MODEL ON (X_train,Y_train)
Y_pred←PREDICT MODEL ON X_test
## COMPUTE:
Accuracy (Y_test, Y_pred)
Precision (Y_test, Y_pred)
Recall (Y_test, Y_pred)
F1-Score (Y_test, Y_pred)
Support (Y_test, Y_pred)
## END
2.1.3. Artificial Neural Network (ANN) Classification Model
The third model that was implemented is known as the artificial neural network
(ANN) classification model. The latter was chosen as it has the inherent capacity to learn
and simulate models where relationships between input’s structures are, by nature, non-
linear, hence raising the level of complexity of predictions and, by default, being a better

## Eng. Proc.2025,118, 80
7 of 12
alternative than the logistic regression model. It is also an upgrade over the naïve Bayes as
it does not assume independence of features.
Algorithm 3, as shown below, illustrates the pseudo code for the model that was
built to implement the artificial neural network algorithm in predicting and classifying the
concentrations of CMM as safe or unsafe during underground mining operations.
Algorithm 3:Pseudo code for the proposed detection of dangerous level of coal mine methane based on an
Artificial Neural Network classifier
Input: sensor data (methane_1, methane_2, methane_3,temperature, pressure, airflow, humidity).
Output: Accuracy, Precision, recall, f1-score, support.
## BEGIN
LOADcsv_file→df
Sample size←size (df)
FOReach row in df, D
mean _ methane←(methane_1 + methane_2 + methane_3)/3
df [‘average methane’]←mean_methane
IFmean_methane > 1 THEN
condition←“Unsafe”
## ELSE
conditon←“Safe”
## END IF
df [‘condition’]←condition
## END FOR
FILTERdf to RETAIN:
{seconds, temperature, airflow,pressure, humidity,methane_1,methane_2,
methane_3, average_methane,condition}
DISPLAYhead (df)
X←{ seconds, temperature, airflow, pressure, humidity, methane_1,methane_2
methane_3, average_methane, condition}
## Y←condition
## ENCODEY:
## Safe = 0
## Unsafe = 1
SPLITdatasetINTO( X_train, Y_train) and (X_test, Y_test)WITHratio 70:30
MODEL←Sequential ()
ADDHidden layer to ANN:
neurons = 32
activation = ReLU
input_shape = 8
ADDOutput Layer to ANN
neurons = 1
activation = Sigmoid
## COMPILEMODEL WITH:
optimizer = Adam
loss= Binary Cross Entropy
metric = Accuracy
SETEarlyStopping
patience = 20 epochs
min_delta = 0.001
FIT MODEL ON (X_train,Y_train)
Y_pred←PREDICT MODEL ON X_test
## COMPUTE:
Accuracy (Y_test, Y_pred)
Precision (Y_test, Y_pred)
Recall (Y_test, Y_pred)
F1-Score (Y_test, Y_pred)
Support (Y_test, Y_pred)
## END

## Eng. Proc.2025,118, 80
8 of 12
- Results and Discussions
This section summarizes the results obtained after deploying the three classification
machine learning models (naïve Bayes, logistic regression and artificial neural network).
The  naïve  Bayes  model  was  deployed,  and  simulations  were  performed  on  the
dataset,  consisting  of  9,197,561  safe  events  indicating  a  safe  level  of  CMM  concen-
trations  and  2369  unsafe  events  indicating  a  dangerous  level  of  CMM  concentration.
Simulations were performed on different sample sizes in the following combinations:
1,000,000,  2,000,000,  3,000,000,  4,000,000,  5,000,000,  6,000,000,  7,000,000,  8,000,000  and
9,199,930. The detailed results for those simulations are illustrated as shown below by both
Tables 1 and 2 respectively:
Table 1.Simulation Results for Safe Cases using Naïve Bayes.
## Total Number
of Simulations
Number of
## Safe Cases
PrecisionRecallF1-Score
## 1,000,000999,812111
## 2,000,0001,999,798111
## 3,000,0002,999,526111
## 4,000,0003,998,436111
## 5,000,0004,997,965111
## 6,000,0005,997,935111
## 7,000,0006,997,935111
## 8,000,0007,997,817111
## 9,199,9309,197,561111
Table 2.Simulation Results for Un Safe Cases using Naïve Bayes.
Total Number of
## Simulations
Number of
## Unsafe Cases
PrecisionRecallF1-Score
## 1,000,0001880.1610.28
## 2,000,0002020.3710.54
## 3,000,0004740.3010.46
## 4,000,00015640.2210.37
## 5,000,00020350.2210.36
## 6,000,00020650.1510.27
## 7,000,00020650.1310.23
## 8,000,00021830.1510.25
## 9,199,93023690.1510.26
In the second part of this section, the logistic regression model was deployed, and
simulations were performed on the dataset, consisting of 9,197,561 safe events indicating
a safe level of CMM concentrations and 2369 unsafe events indicating a dangerous level
of CMM concentration.   Simulations were performed on different sample sizes in the
following combinations:  1,000,000,  2,000,000,  3,000,000,  4,000,000,  5,000,000,  6,000,000,
7,000,000, 8,000,000 and 9,199,930. The detailed results for those simulations are illustrated
as shown below by Tables 3 and 4, respectively:

## Eng. Proc.2025,118, 80
9 of 12
Table 3.Simulation Results for Safe Cases using Logistic Regression.
Total Number of
## Simulations
Number of Safe
## Cases
PrecisionRecallF1-Score
## 1,000,000999,812111
## 2,000,0001,999,798111
## 3,000,0002,999,526111
## 4,000,0003,998,436111
## 5,000,0004,997,965111
## 6,000,0005,997,935111
## 7,000,0006,997,935111
## 8,000,0007,997,817111
## 9,199,9309,197,561111
Table 4.Simulation Results for Un Safe Cases using Logistic Regression.
Total Number of
## Simulations
Number of
## Unsafe Cases
PrecisionRecallF1-Score
## 1,000,0001880.5610.72
## 2,000,0002020.4610.63
## 3,000,0004740.4010.57
## 4,000,00015640.5110.67
## 5,000,00020350.5310.69
## 6,000,00020650.5710.72
## 7,000,00020650.5110.67
## 8,000,00021830.5210.68
## 9,199,93023690.5310.69
In the third part of this section, the artificial neural network model was deployed, and
simulations were performed on the dataset, consisting of 9,197,561 safe events indicating
a safe level of CMM concentrations and 2369 unsafe events indicating a dangerous level
of CMM concentration.   Simulations were performed on different sample sizes in the
following combinations:  1,000,000,  2,000,000,  3,000,000,  4,000,000,  5,000,000,  6,000,000,
7,000,000, 8,000,000 and 9,199,930. The detailed results for those simulations are illustrated
as shown below by Tables 5 and 6 respectively:
Table 5.Simulation Results for Safe Cases using Artificial Neural Network.
Total Number of
## Simulations
Number of Safe
## Cases
PrecisionRecallF1-Score
## 1,000,000999,812111
## 2,000,0001,999,798111
## 3,000,0002,999,526111
## 4,000,0003,998,436111
## 5,000,0004,997,965111
## 6,000,0005,997,935111
## 7,000,0006,997,935111
## 8,000,0007,997,817111
## 9,199,9309,197,561111

## Eng. Proc.2025,118, 80
10 of 12
Table 6.Simulation Results for Un Safe Cases using Artificial Neural Network.
Total Number of
## Simulations
Number of
## Unsafe Cases
PrecisionRecallF1-Score
## 1,000,0001881.000.830.91
## 2,000,0002021.000.480.64
## 3,000,0004741.000.550.71
## 4,000,00015640.960.820.88
## 5,000,00020350.960.870.91
## 6,000,00020650.960.740.83
## 7,000,00020650.900.850.87
## 8,000,00021830.990.760.86
## 9,199,93023690.900.810.85
Based on the results above, it is clear that all three models perform really well in
predicting safe events but does that mean that they are all robust and efficient enough
in detecting and predicting dangerous concentrations of methane?  The answer to this
question is no. There is a major imbalance in the dataset, as shown in the figure above. If
we consider the dataset in its totality, there are 2369 cases of unsafe cases over a total of
9,199,930 cases, and that amounts to only 0.026%. As a result, if one takes the accuracy of
these models as a metric to measure their strength, it will lead to an erroneous conclusion
as the accuracy tells us how well the model performs, and in this case, that will relate to
how good the model is at picking up safe cases. The minority class of unsafe classes will
therefore be overlooked in such an analysis, and that will not contribute to creating an
algorithm that is good at detecting unsafe concentrations of methane.  Therefore, other
metrics need to be employed to correctly assess the robustness and efficiency of the above
tested models in terms of their predictability capacity. The metric that has been considered
is precision. The precision parameter contributed to answering the following question: Out
of all the unsafe events detected, how many are really unsafe events? Basically, it ensures
that only real cases of unsafe events are picked up and all false alarms are filtered out.
Table  2 clearly  shows  that for  the  simulation  of the  naïve  Bayes algorithms,  low
precision was achieved across the different sample sizes.  This indicates that the model
performed poorly in detecting real cases of unsafe events,  and this generated a lot of
false alarms.   This is an example of an algorithm that cannot be applied in a real-life
situation because it will wrongly flag standard cases as unsafe ones, causing unnecessary
disruptions during underground mining operations.  Table 4 shows an improvement in
the predictive capacity of the model when a logistic regression algorithm is used.  The
precision presents a maximum value of 0.57 and a minimum value of 0.40.  Despite this
improvement, the logistic regression algorithm still performs poorly as those values indicate
that around approximately half of the predictions made are actually made up of false
positives.  However, Table 6 shows a drastic improvement in the predictive capacity to
detect dangerous concentrations of methane when an artificial neural network is deployed.
The minimum value recorded is 0.90, and a maximum value of 1.0 was recorded in three
different simulations over three different slices of the dataset. This indicates that in three
different  instances,  the  algorithm  correctly  identified  all  the  different  unsafe  cases  of
methane without any false positives. In order to improve those predictions, it must be noted
that since the dataset is very imbalanced in nature, it is therefore highly recommended that
resampling methods like SMOTE be applied in order to improve the machine intelligence

## Eng. Proc.2025,118, 80
11 of 12
algorithms in their learning capacity towards the minority class, precisely the unsafe class
for this specific research.
## 4. Conclusions
This research presents an approach to comparing three machine learning models with
the objective of building a classification model down the line that has high predictability
for detecting dangerous or unsafe concentrations of methane. The research started with
handling a dataset containing records of methane concentrations, environmental or climatic
factors, as well as physical factors.  Since there was a desire to build predictive models
that are climatic or environmentally oriented for the prediction of coal mine methane, the
assumption was made that the only inputs to the machine learning model that will be
considered are temperature, airflow, pressure as well as humidity. The dataset was cleaned,
and the required content was extracted to serve as input to the different machine learning
models. The three models were tested on different sample sizes of data, and a classification
report was issued after each simulation with the necessary statistical parameters to evaluate
the robustness and reliability of these models.  The parameters that were used were the
precision, f1 score and recall. These parameters were selected as they can provide a robust
answer to the question “How efficient are the models in picking up unsafe situations,
keeping in mind that there is a major imbalance favoring safe classes over the unsafe ones?”
The evidence displayed by Tables 2, 4 and 6 indicates that the artificial neural network
(ANN) performed better compared to naïve Bayes and logistic regression when it came to
the prediction of unsafe cases. This research indicates that machine learning models built
on neural networks algorithms perform better in their predictive capability in this type of
situation. A further study into this research will include the use of more advanced deep
learning models working in a hybrid approach with optimization algorithms like the Black
Kite Algorithm (BKA).
Author Contributions:Initial concept, M.K.A.; formal analysis and investigation, R.M.; writing—
original draft preparation, R.M.; writing—review and editing, R.M. and M.K.A.; supervision and
guidance, M.K.A. All authors have read and agreed to the published version of the manuscript.
Funding:This research received no external funding.
Institutional Review Board Statement:Not applicable.
Informed Consent Statement:Not applicable.
Data Availability Statement:No additional data is available other than the dataset presented in the
body of this work.
Conflicts of Interest:The authors declare no conflicts of interest.
## References
1.Peng, S.Longwall Mining; CRC Press: Boca Raton, FL, USA, 2019.
## 2.
Demirkan,  D.C.;  Duzgun,  S.;  Juganda,  A.;  Brune,  J.;  Bogin,  G.  Evaluation  of  time  series  artificial  intelligence  models  for
real-time/near-real-time methane prediction in coal mines.CIM J.2022,13, 97–106. [CrossRef]
3.United Nations: Economic Commission for Europe.Best Practice Guidance for Effective Methane Drainage and Use in Coal Mines;
United Nations: New York, NY, USA, 2010.
4.Gangrade, V.; Schatzel, S.; Harteis, S.; Addis, J. Investigating the impact of caving on longwall mine ventilation using scaled
physical modeling.Min. Metall. Explor.2019,36, 729–740. [PubMed]
## 5.
Kimiagar, S.; Najafi, V.; Witkowski, B.; Pietruszka, R.; Godlewski, M. High performance and low temperature coal mine gas
sensor activated by UV-irradiation.Sci. Rep.2018,8, 16298. [CrossRef] [PubMed]
## 6.
Wu, X.; Cui, J.; Tong, R.; Li, Q. Research on Methane Measurement and Interference Factors in Coal Mines.Sensors2022,22, 5608.
[CrossRef] [PubMed]

## Eng. Proc.2025,118, 80
12 of 12
7.Tutak, M.; Krenicky, T.; Pirník, R.; Brodny, J.; Grebski, W.W. Predicting Methane Concentrations in Underground Coal Mining
Using a Multi-Layer Perceptron Neural Network Based on Mine Gas Monitoring Data.Sustainability2024,16, 8388. [CrossRef]
## 8.
Qu, H.; Shao, X.; Gao, H.; Chen, Q.; Guang, J.; Liu, C. A Prediction Model for Methane Concentration in the Buertai Coal Mine
Based on Improved Black Kite Algorithm–Informer–Bidirectional Long Short-Term Memory.Processes2025,13, 205. [CrossRef]
## 9.
Nie, Z.; Ma, H.; Zhang, Y. Research on Gaussian Plume Model of Gas Diffusion in Coal Mine Roadway Based on BP Neural
Network Optimized by Genetic Algorithm.Proc. IOP Conf. Ser. Earth Environ. Sci.2020,526, 012158. [CrossRef]
10.Guo, R.; Xu, G. Research on coal mine gas concentration multi-sensor prediction model based on information fusion and GA-SVM.
## China Saf. Sci. J.2013,23, 34–38.
11.Luo, Z.; Zhai, H.; Tong, J. Incorporating multi-features and XGBoost algorithm for gas concentration prediction.China Min. Mag.
## 2024,33, 359–363, 370.
12.Kozielski, M.; Sikora, M.; Wróbel, Ł. Data on methane concentration collected by underground coal mine sensors.Data Brief2021,
39, 107457. [CrossRef] [PubMed]
Disclaimer/Publisher’s Note:The statements, opinions and data contained in all publications are solely those of the individual
author(s) and contributor(s) and not of MDPI and/or the editor(s). MDPI and/or the editor(s) disclaim responsibility for any injury to
people or property resulting from any ideas, methods, instructions or products referred to in the content.