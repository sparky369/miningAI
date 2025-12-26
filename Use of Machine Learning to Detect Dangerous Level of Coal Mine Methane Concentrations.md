Proceeding Paper

### Use of Machine Learning to Detect Dangerous Level of Coal Mine Methane(CMM) Concentrations During Underground Mining Operations  ${}^{+}$ 

 Rubeshen Mooroogen D and Michael K. Ayomoh* D

 Department of Industrial& Systems Engineering, University of Pretoria, Hatfield, Pretoria 0028, South Africa;mrubeshen@gmail.com

* Correspondence: michael.ayomoh@up.ac.za

 ${}^{\dagger}$  Presented at the 12th International Electronic Conference on Sensors and Applications, 12-14 November 2025;Available online: https://sciforum.net/event/ECSA-12.

### Abstract

Underground coal mining is considered to be a highly dangerous activity and has been responsible for large amounts of accidents, causing the death of many mine workers. One of the factors responsible for the fatal aspect of underground coal mining is the presence and accumulation of toxic gases during underground mining operations. This paper focused its investigation specifically on coal mine methane(CMM), which is released as a result of the extraction of coal and the disturbance inflicted to surrounding rock formations during deep mining operations. Methane is considered a highly dangerous gas as it holds the capacity to cause explosions due to its highly inflammable nature. It can also displace oxygen, which eventually leads to asphyxiation. This research was based on the use of machine learning models to successfully predict dangerous concentrations of methane over the authorized threshold. Those predictions were made from a dataset containing information on the temperature, airflow,humidity, pressure and methane concentration in an underground coal mine. The temperature, airflow, humidity and pressure measurements were recorded by a series of sensors, namely anemometers and component sensors THP2/93. Three machine learning classification models were implemented and compared, with the objective to find the best model to predict and detect dangerous levels of coal mine methane. The models that were investigated included naive Bayes, logistic regression and artificial neural networks(ANNs). This paper concludes with an engineering decision matrix that illustrates the precision of these models in predicting and detecting dangerous levels of methane concentrations in underground mines. Furthermore, recommendations for capacity improvement towards successfully predicting and detecting dangerous levels of coal mine methane from an artificial intelligence's perspective are provided.

Keywords: coal mine methane(CMM); machine learning; artificial intelligence; sensors

### 1. Introduction

 There are three types of mining operations to extract ores. These types of operations are notably open surface mining, deep mining and sea water mining. As for deep mining,also known as underground mining operations, the most common technique used is longwall mining because it is considered the safest and most productive technique[1].However, past research clearly demonstrates that this specific technique of extraction releases high and dangerous concentrations of methane, also referred to as coal mine

methane(CMM), in the surrounding underground environment[2]. CMM, owing to its inflammable nature, has been responsible for a large number of lethal explosions around the world. A document signed by the United Nations detailed those fatal accidents as follows:214 deaths on 14 February 2005 in the Sunjiawan mine of China; 108 deaths on 19 March 2007 in Ulyanovskaya mine of Russia; 80 deaths on 19 November 2007 in Zasyadko mine of Ukraine; 43 deaths on 20 September 2006 in Lenina mine of Kazakhstan; 29 fatalities in Upper Big Branch, West Virginia, United states of America, on 5 April 2010; and 12 deaths also in West Virginia, most precisely in Sago, on 14 February 2005[3]. As a result,CMM explosions are considered amongst the most lethal accidents when it comes to underground or deep mining operations, hindering the safety and productivity of mining environments as well as its industry. One way to ensure that the concentration of coal mine methane does not exceed the safe and permissible threshold is the use of ventilation. According to a study performed on the safety of longwall mining, researchers supported the use of ventilation as the most effective method for the control of gases, with a special focus on coal mine methane, known to be present and released in large volumes during longwall mining activities[4].

To achieve optimal ventilation in underground mining regions, it is important to localize the regions that present high concentrations of CMM. This is achieved by the implementation of a sensing and metrification strategy. Since the concentration of CMM is largely attributed to its capacity to accumulate and disperse, which itself is dependent on physical parameters like temperature, humidity, pressure and airflow, sensors are placed in various locations of underground mines to collect data, which contributes to better management of CMM through optimal ventilation usage. The type of sensors commonly used are normally threshold triggering and continuous monitoring. Threshold triggering sensors normally emit an output whenever the measured parameter exceeds the permissible threshold. On the other hand, continuous monitoring sensors collect real-time data over a period of time. The use of triggering sensors in the management of CMM in underground mining conditions comes with its own set of challenges and disadvantages that compromise the safety of the mines as well as their productivity. Triggering sensors emit an alarm only when the maximum permissible CMM threshold has been exceeded.This type of system only allows for reactive measures, which leave little to no time to respond efficiently to a hazardous situation. This can lead to a fatal occurrence in the case of late activation of the sensors. Past studies demonstrate that under deep mining conditions, the response time of a sensor varies between 210 and 257 s while the recovery time sits between 142 and 241 s[5]. These data clearly show that it takes too much time for a triggering sensor to pick up high concentrations of CMM, hence increasing the risk of explosions in underground mines. A study focused on the influence of environmental factors like humidity, alongside pressure, concluded that those natural factors interfere with the capacity of these sensors by introducing an element of delay leading to late alarms[6]. As a result, the reactive cognition aspect of the methane management system is heavily compromised and highly hazardous and dangerous situations are not dealt with appropriately, leading to explosions. To improve the detection of CMM, artificial intelligence models are employed to predict dangerous concentrations of CMM with a high level of precision and accuracy. This improves the cognition attribute of underground CMM management by replacing reactive decisions with proactive ones. Tutak, Krenicky,Pirnik,Brodny and Grebski proposed a Multi-Layer Perceptron Neural Network for predictions of CMM in underground coal mining[7]. This research was focused on longwall mining and concluded that it was possible to generate forecasts of CMM with a high level of accuracy.According this paper, predictions made within a forecast window ranging from 5 to 60 min were considered as acceptable. A different study performed in China, most precisely at

the Buertai Coal Mine, proposed a prediction model for methane concentration, namely an Improved Black Kite Algorithm(BKA) working together with an Informer Bidirectional Long Short Term Memory algorithm[8]. This proposed algorithm made use of several features, which include historical data on methane concentrations, temperature as well as wind speed, and results obtained indicated a high predictive accuracy of the model in terms of convergence and speed as well as an elevated degree of robustness. Nie et al.[9] studied the characteristics of the surrounding mining environment with the objective of better understanding the manner in which CMM spreads in underground mines. This allowed the researchers to present a methane prediction model based on the Gaussian plume model,genetic algorithms and BP neural networks(Back Propagation Neural Network). This model presented a high level of accuracy in monitoring the level of CMM and is considered reliable due to its ability to continuously train on daily real-time data. Another machine learning technique that was used successfully in methane prediction is the support vector machine algorithm[10]. This research focused on building a multi-sensor prediction model for methane predictions by combining methodologies from information fusion alongside support vector machines. To achieve a high predictive accuracy of coal mine methane, it is common and highly advisable to use a palette of features as demonstrated by Zhiqiang Luo et al.[11] in building their eXtreme Gradient Boosting algorithm(XG Boost). For this model, the researchers chose to make sure that natural parameters like temperature and past historical data of methane concentrations were used to train and test their machine learning models. The results obtained indicated that the tested models had faster training speeds compared to existing ones and a lower percentage of prediction errors.

From the above, it is clear that a robust artificial intelligent mode with a high degree of accuracy can successfully predict dangerous concentrations of methane, enhancing the safety of underground mining operations. This paper analyzed the computational ability and reliability of three machine learning classification models that successfully predict and classify dangerous concentrations of coal mine methane in underground mines. Those three machine learning classification models are naive Bayes, logistic regression and artificial neural network. The aim of this paper is to perform a comparative analysis of these three algorithms in regard to their capacity to predict dangerous levels of concentrations of CMM with a high degree of accuracy. This paper, with the results obtained, will lay the foundation for building improved machine learning algorithms with higher degrees of accuracy in regard to the prediction of dangerous concentrations of CMM.

### 2. Research Methodology

The research methodology is divided into two parts: the first part being preparing the sensing dataset in order to be used as input for the classification models and the second part being the design and implementation of the three above discussed machine learning classification models.

### 2.1. Description of the Sensing Data and Machine Learning Algorithms

This study investigated and compared the use of three machine learning classification models, namely naive Bayes, logistic regression and artificial neural network to predict and efficiently classify concentrations of methane into safe and unsafe categories. These predictions were made based on data from sensing data: past historical concentrations of methane, temperature, humidity, airflow and pressure. These data were obtained from 28 different sensors placed at different locations in the underground mine[12]. The underground mine that was used for this study is located in the Upper Silesian coal basin,in the region of Voivodeship in Poland. The data was recorded every 1 s, and two groups of data were recorded, with the first one focusing on climatic parameters like temperature

and the second group focusing on activities focusing on the cutter loader operation. For the purpose of this research paper, only the climatic conditions of temperature, pressure,humidity and airflow were considered as input to the different machine learning models.This is in line with the philosophy of the research to test the predictability of those machine learning models from a pure climatic and environmental perspective before introducing other input that relate to the human activities performed in mines. The following section depicts the data handling procedure of this research:

1. The dataset was cleaned to ensure that there were no missing values, and any dupli-cated readings were removed.

2. The required features that will serve as input to the machine learning classification models were selected. Those features are pressure, temperature, humidity and airflow.

3.The required methane meters and associated historical data were selected as output.

4.Based on a chosen threshold(e.g., 1.0), methane's concentration was classified as safe and unsafe.

5.Checks were performed on different portions of the dataset to check the number of safe and unsafe cases in each data cluster.

6.The data were used as input to three different machine learning classification models.Those models are naive Bayes, logistic regression and artificial neural networks.

7. The classification report was then printed out to display the values for the statistical parameters.

The following section addresses the development of the three machine learning classi-fication algorithms that are deployed for this research.

### 2.1.1. Naive Bayes Machine Learning Classification Model

The naive Bayes classification model is used as a first baseline model for the purpose of this research and is based on the assumption of attribute independence. This means that all the features or attributes are not related to each other. Naive Bayes is built from the Bayes theorem, as shown below by Equation(1):

$$
P(C\mid X)=\frac{P(X\mid C)\times P(C)}{P(X)}\qquad(1)
$$

The Bayes theorem above consists of two parameters, which are C and X. C represents the class that needs to be predicted, while X represents the different features that are used as inputs.  $P(C\mid X)$  indicates the probability of an event C happening given X has happened. In order to form the naive Bayes equation, it is assumed that each feature of x is independent of each other, giving the following equation:

$$
P\left(x_{1}, x_{2},\ldots, x_{n}\mid C\right)=\frac{P(C)\times\prod_{i=1}^{n} P\left(x_{i}\mid C\right)}{P\left(x_{1}, x_{2},\ldots, x_{n}\right)}\qquad(2)
$$

For the purpose of this study, the x parameter will relate to the climatic conditions of the underground mine, which are temperature, pressure, airflow and humidity. C will relate to the different categories of CMM concentrations in underground mines. Two categories will be used for this paper, and they are safe and unsafe. The purpose of the naive Bayes classification algorithm will be to use the different input parameters such as temperature, pressure, humidity and airflow to predict and classify CMM concentrations as safe or unsafe.

Algorithm 1, as shown below, illustrates the pseudo code for the proposed model that was built to implement the naive Bayes algorithm for predicting and classifying the concentrations of CMM as safe or unsafe during underground mining operations.

### Algorithm 1: Pseudo code for the proposed detection of dangerous level of coal mine methane based on a Naive-Bayes classifier

Input: sensor data(methane_1, methane_2, methane_3, temperature, pressure, airflow,humidity).

Output: Accuracy, Precision, recall, f1-score, support.

### BEGIN

LOAD csv_file  $\rightarrow$  df

 Sample size  $\leftarrow$  size(df)

FOR each row in df, D

 mean_ methane  $\leftarrow$  (methane_1+ methane_2+ methane_3)/ 3

df  $\left[{}^{\prime}\right.$  average methane  ${}^{\prime}\right]\leftarrow$  mean_methane

 IF mean_methane  $>1$  THEN

 condition  $\leftarrow$  "Unsafe"

ELSE

 condition  $\leftarrow$  "Safe"

END IF

 df['condition']  $\leftarrow$  condition

### END FOR

 FILTER df to RETAIN:

{seconds, temperature, airflow,pressure, humidity,methane_1,methane_2,

methane_3, average_methane,condition\}

DISPLAY head(df)

 $X\leftarrow\{$  seconds, temperature, airflow, pressure, humidity, methane_1, methane_2

methane_3, average_, methane, condition}\}

 $Y\leftarrow$  condition

 ENCODE Y:

Safe= 0

Unsafe=1

SPLIT dataset INTO( X_train, Y_train) and(X_test, Y_test) WITH ratio 70:30

MODEL  $\leftarrow$  GaussianNaiveBayes()

FIT MODEL ON(X_train,Y_train)

Y_pred  $\leftarrow$  PREDICT MODEL ON X_test

 COMPUTE:

Accuracy(Y_test, Y_pred)

Precision(Y_test, Y_pred)

Recall(Y_test, Y_pred)

F1-Score(Y_test, Y_pred)

Support(Y_test, Y_pred)

### 2.1.2. Logistic Regression Machine Learning Classification Model

The second model that was implemented is known as the logistic regression classi-fication model. This model is, by nature, a statistical classification model which outputs a probability that sits between zero and one. Compared to naive Bayes, this model does not require the assumption of independence between the input features, hence making it a more robust alternative compared to the previous model.

Algorithm 2 as shown below, illustrates the proposed model that was built to imple-ment the logistic regression algorithm in predicting and classifying the concentrations of CMM as safe or unsafe during underground mining operations.

Algorithm 2: Pseudo code for the proposed detection of dangerous level of coal mine methane based on a Logistic Regression classifier

 Input: sensor data(methane_1, methane_2, methane_3,temperature, pressure, airflow,humidity).

Output: Accuracy, Precision, recall, f1-score, support.

### BEGIN

LOAD csv_file  $\rightarrow$  df

 Sample size  $\leftarrow$  size(df)

FOR each row in df, D

 mean_ methane  $\leftarrow$  (methane_1+ methane_2+ methane_3)/ 3

df['average methane']  $\leftarrow$  mean_methane

 IF mean_methane  $>1$  THEN

 condition  $\leftarrow$  "Unsafe"

ELSE

condition  $\leftarrow$  "Safe"

 END IF

 df['condition']  $\leftarrow$  condition

### END FOR

 FILTER df to RETAIN:

{seconds, temperature, airflow,pressure, humidity,methane_1,methane_2,methane_3, average_methane,condition\}

DISPLAY head(df)

 $X\leftarrow\{$  seconds, temperature, airflow, pressure, humidity, methane_1, methane_2 methane_3, average_, methane, condition}\}

Y\leftarrow condition

 ENCODE Y:

Safe=0

Unsafe=1

SPLIT dataset INTO( X_train, Y_train) and(X_test, Y_test) WITH ratio 70:30

MODEL  $\leftarrow$  LogisticRegression(

class_weight="balanced",

$$
\max\_iter=10000
$$

solver="liblinear")

FIT MODEL ON(X_train,Y_train)

Y_pred  $\leftarrow$  PREDICT MODEL ON X_test

 COMPUTE:

Accuracy(Y_test, Y_pred)

Precision(Y_test, Y_pred)

Recall(Y_test, Y_pred)

F1-Score(Y_test, Y_pred)

Support(Y_test, Y_pred)

END

### 2.1.3. Artificial Neural Network(ANN) Classification Model

 The third model that was implemented is known as the artificial neural network(ANN) classification model. The latter was chosen as it has the inherent capacity to learn and simulate models where relationships between input's structures are, by nature, non-linear, hence raising the level of complexity of predictions and, by default, being a better

alternative than the logistic regression model. It is also an upgrade over the naive Bayes as it does not assume independence of features.

Algorithm 3, as shown below, illustrates the pseudo code for the model that was built to implement the artificial neural network algorithm in predicting and classifying the concentrations of CMM as safe or unsafe during underground mining operations.



| Algorithm 3: Pseudo code for the proposed detection Artificial Neural Network classifier | on of dangerous level of coal mine methane based on an |
| --- | --- |
| Input: sensor data(methane_1, methane_2, methar_ Output: Accuracy, Precision, recall, f1-score, suppcrt. BEGIN | e_3,temperature, pressure, airflow, humidity). Output: Accuracy, Precision, recall, f1-score, suppcrt. |
| LOAD csv_file  $\rightarrow$  df |  |
| Sample size  $\leftarrow$  size(df) |  |
| FOR each row in df, D |  |
| mean_ methane  $\leftarrow$  (methane_1+ methane_2+ methane_3)/3 | mean_ methane  $\leftarrow$  (methane_1+ methane_2+ methane_3)/3 |
| df['average methane']  $\leftarrow$  mean_meth | df['average methane']  $\leftarrow$  mean_meth  $\cdot$  ne |
| IF mean_methane> 1 THEN |  |
| condition  $\leftarrow$  "Unsafe" |  |
| ELSE |  |
| condition  $\leftarrow$  "Safe" |  |
| END IF |  |
| df['condition']  $\leftarrow$  condition |  |
| END FOR |  |
| FILTER df to RETAIN: |  |
| {seconds, temperature, airflow,pressun | , humidity,methane_1,methane_2, |
| methane_3 , average_methane, | , average_methane,:ondition\} |
| DISPLAY head(df) |  |
|  $X\leftarrow\{$  seconds, temperature, airflow, pressure, humidity, methane_1, methane_2 |  $X\leftarrow\{$  seconds, temperature, airflow, pressure, humidity, methane_1, methane_2 |
| methane_3, average_methane, condition  $\}$  | methane_3, average_methane, condition\} |
|  $Y\leftarrow$  condition |  |
| ENCODE Y: |  |
| Safe= 0 |  |
| Unsafe=1 |  |
| SPLIT dataset INTO(X_train, Y_train) and( | (_test, Y_test) WITH ratio 70:30 |
| MODEL  $\leftarrow$  Sequential() |  |
| ADD Hidden layer to ANN: |  |
| neurons=32 |  |
| activation= ReLU |  |
| input_shape=8 |  |
| ADD Output Layer to ANN |  |
| neurons=1 |  |
| activation=Sigmoid |  |
| COMPILE MODEL WITH: |  |
| optimizer=Adam |  |
| loss= Binary Cross Entropy |  |
| metric=Accuracy |  |
| SET EarlyStopping |  |
| patience=20 epochs |  |
| $$\min\_\text{delta}=0.001$$ |  |
| FIT MODEL ON(X_train,Y_train) |  |
| Y_pred  $\leftarrow$  PREDICT MODEL ON X_test |  |
| COMPUTE: |  |
| Accuracy(Y_test, Y_pred) |  |
| Precision(Y_test,Y_pred) |  |
| Recall(Y_test,Y_pred) |  |
| F1-Score(Y_test, Y_pred) |  |
| Support(Y_test,Y_pred) |  |
| END |  |

### 3. Results and Discussions

This section summarizes the results obtained after deploying the three classification machine learning models(naive Bayes, logistic regression and artificial neural network).

The naive Bayes model was deployed, and simulations were performed on the dataset, consisting of 9,197,561 safe events indicating a safe level of CMM concen-trations and 2369 unsafe events indicating a dangerous level of CMM concentration.Simulations were performed on different sample sizes in the following combinations:1,000,000,2,000,000,3,000,000,4,000,000,5,000,000,6,000,000,7,000,000,8,000,000 and 9,199,930. The detailed results for those simulations are illustrated as shown below by both Tables 1 and 2 respectively:

Table 1. Simulation Results for Safe Cases using Naive Bayes.



| Total Number of Simulations | Number of Safe Cases | Precision | Recall | F1-Score |
| --- | --- | --- | --- | --- |
| 1,000,000 | 999,812 | 1 | 1 | 1 |
| 2,000,000 | 1,999,798 | 1 | 1 | 1 |
| 3,000,000 | 2,999,526 | 1 | 1 | 1 |
| 4,000,000 | 3,998,436 | 1 | 1 | 1 |
| 5,000,000 | 4,997,965 | 1 | 1 | 1 |
| 6,000,000 | 5,997,935 | 1 | 1 | 1 |
| 7,000,000 | 6,997,935 | 1 | 1 | 1 |
| 8,000,000 | 7,997,817 | 1 | 1 | 1 |
| 9,199,930 | 9,197,561 | 1 | 1 | 1 |

Table 2. Simulation Results for Un Safe Cases using Naive Bayes.



| Total Number of Simulations | Number of Unsafe Cases | Precision | Recall | F1-Score |
| --- | --- | --- | --- | --- |
| 1,000,000 | 188 | 0.16 | 1 | 0.28 |
| 2,000,000 | 202 | 0.37 | 1 | 0.54 |
| 3,000,000 | 474 | 0.30 | 1 | 0.46 |
| 4,000,000 | 1564 | 0.22 | 1 | 0.37 |
| 5,000,000 | 2035 | 0.22 | 1 | 0.36 |
| 6,000,000 | 2065 | 0.15 | 1 | 0.27 |
| 7,000,000 | 2065 | 0.13 | 1 | 0.23 |
| 8,000,000 | 2183 | 0.15 | 1 | 0.25 |
| 9,199,930 | 2369 | 0.15 | 1 | 0.26 |

In the second part of this section, the logistic regression model was deployed, and simulations were performed on the dataset, consisting of 9,197,561 safe events indicating a safe level of CMM concentrations and 2369 unsafe events indicating a dangerous level of CMM concentration. Simulations were performed on different sample sizes in the following combinations: 1,000,000,2,000,000,3,000,000,4,000,000,5,000,000,6,000,000,7,000,000,8,000,000 and 9,199,930. The detailed results for those simulations are illustrated as shown below by Tables 3 and 4, respectively:

Table 3. Simulation Results for Safe Cases using Logistic Regression.



| Total Number of Simulations | Number of Safe Cases | Precision | Recall | F1-Score |
| --- | --- | --- | --- | --- |
| 1,000,000 | 999,812 | 1 | 1 | 1 |
| 2,000,000 | 1,999,798 | 1 |  | 1 |
| 3,000,000 | 2,999,526 | 1 | 1 | 1 |
| 4,000,000 | 3,998,436 | 1 | 1 | 1 |
| 5,000,000 | 4,997,965 | 1 | 1 | 1 |
| 6,000,000 | 5,997,935 | 1 |  | 1 |
| 7,000,000 | 6,997,935 | 1 |  | 1 |
| 8,000,000 | 7,997,817 | 1 | 1 | 1 |
| 9,199,930 | 9,197,561 | 1 | 1 | 1 |

Table 4. Simulation Results for Un Safe Cases using Logistic Regression.



| Total Number of Simulations | Number of Unsafe Cases | Precision | Recall | F1-Score |
| --- | --- | --- | --- | --- |
| 1,000,000 | 188 | 0.56 | 1 | 0.72 |
| 2,000,000 | 202 | 0.46 | 1 | 0.63 |
| 3,000,000 | 474 | 0.40 | 1 | 0.57 |
| 4,000,000 | 1564 | 0.51 |  | 0.67 |
| 5,000,000 | 2035 | 0.53 |  | 0.69 |
| 6,000,000 | 2065 | 0.57 |  | 0.72 |
| 7,000,000 | 2065 | 0.51 | 1 | 0.67 |
| 8,000,000 | 2183 | 0.52 | 1 | 0.68 |
| 9,199,930 | 2369 | 0.53 | 1 | 0.69 |

In the third part of this section, the artificial neural network model was deployed, and simulations were performed on the dataset, consisting of 9,197,561 safe events indicating a safe level of CMM concentrations and 2369 unsafe events indicating a dangerous level of CMM concentration. Simulations were performed on different sample sizes in the following combinations: 1,000,000,2,000,000,3,000,000,4,000,000,5,000,000,6,000,000,7,000,000,8,000,000 and 9,199,930. The detailed results for those simulations are illustrated as shown below by Tables 5 and 6 respectively:

Table 5. Simulation Results for Safe Cases using Artificial Neural Network.



| Total Number of Simulations | Number of Safe Cases | Precision | Recall | F1-Score |
| --- | --- | --- | --- | --- |
| 1,000,000 | 999,812 | 1 | 1 | 1 |
| 2,000,000 | 1,999,798 | 1 |  | 1 |
| 3,000,000 | 2,999,526 | 1 | 1 | 1 |
| 4,000,000 | 3,998,436 | 1 | 1 | 1 |
| 5,000,000 | 4,997,965 | 1 | 1 | 1 |
| 6,000,000 | 5,997,935 | 1 | 1 | 1 |
| 7,000,000 | 6,997,935 | 1 | 1 | 1 |
| 8,000,000 | 7,997,817 | 1 | 1 | 1 |
| 9,199,930 | 9,197,561 | 1 | 1 | 1 |

Table 6. Simulation Results for Un Safe Cases using Artificial Neural Network.



| Total Number of Simulations | Number of Unsafe Cases | Precision | Recall | F1-Score |
| --- | --- | --- | --- | --- |
| 1,000,000 | 188 | 1.00 | 0.83 | 0.91 |
| 2,000,000 | 202 | 1.00 | 0.48 | 0.64 |
| 3,000,000 | 474 | 1.00 | 0.55 | 0.71 |
| 4,000,000 | 1564 | 0.96 | 0.82 | 0.88 |
| 5,000,000 | 2035 | 0.96 | 0.87 | 0.91 |
| 6,000,000 | 2065 | 0.96 | 0.74 | 0.83 |
| 7,000,000 | 2065 | 0.90 | 0.85 | 0.87 |
| 8,000,000 | 2183 | 0.99 | 0.76 | 0.86 |
| 9,199,930 | 2369 | 0.90 | 0.81 | 0.85 |

Based on the results above, it is clear that all three models perform really well in predicting safe events but does that mean that they are all robust and efficient enough in detecting and predicting dangerous concentrations of methane? The answer to this question is no. There is a major imbalance in the dataset, as shown in the figure above. If we consider the dataset in its totality, there are 2369 cases of unsafe cases over a total of 9,199,930 cases, and that amounts to only 0.026%. As a result, if one takes the accuracy of these models as a metric to measure their strength, it will lead to an erroneous conclusion as the accuracy tells us how well the model performs, and in this case, that will relate to how good the model is at picking up safe cases. The minority class of unsafe classes will therefore be overlooked in such an analysis, and that will not contribute to creating an algorithm that is good at detecting unsafe concentrations of methane. Therefore, other metrics need to be employed to correctly assess the robustness and efficiency of the above tested models in terms of their predictability capacity. The metric that has been considered is precision. The precision parameter contributed to answering the following question: Out of all the unsafe events detected, how many are really unsafe events? Basically, it ensures that only real cases of unsafe events are picked up and all false alarms are filtered out.

Table 2 clearly shows that for the simulation of the naive Bayes algorithms, low precision was achieved across the different sample sizes. This indicates that the model performed poorly in detecting real cases of unsafe events, and this generated a lot of false alarms. This is an example of an algorithm that cannot be applied in a real-life situation because it will wrongly flag standard cases as unsafe ones, causing unnecessary disruptions during underground mining operations. Table 4 shows an improvement in the predictive capacity of the model when a logistic regression algorithm is used. The precision presents a maximum value of 0.57 and a minimum value of 0.40. Despite this improvement, the logistic regression algorithm still performs poorly as those values indicate that around approximately half of the predictions made are actually made up of false positives. However, Table 6 shows a drastic improvement in the predictive capacity to detect dangerous concentrations of methane when an artificial neural network is deployed.The minimum value recorded is 0.90, and a maximum value of 1.0 was recorded in three different simulations over three different slices of the dataset. This indicates that in three different instances, the algorithm correctly identified all the different unsafe cases of methane without any false positives. In order to improve those predictions, it must be noted that since the dataset is very imbalanced in nature, it is therefore highly recommended that resampling methods like SMOTE be applied in order to improve the machine intelligence

algorithms in their learning capacity towards the minority class, precisely the unsafe class for this specific research.

### 4. Conclusions

This research presents an approach to comparing three machine learning models with the objective of building a classification model down the line that has high predictability for detecting dangerous or unsafe concentrations of methane. The research started with handling a dataset containing records of methane concentrations, environmental or climatic factors, as well as physical factors. Since there was a desire to build predictive models that are climatic or environmentally oriented for the prediction of coal mine methane, the assumption was made that the only inputs to the machine learning model that will be considered are temperature, airflow, pressure as well as humidity. The dataset was cleaned,and the required content was extracted to serve as input to the different machine learning models. The three models were tested on different sample sizes of data, and a classification report was issued after each simulation with the necessary statistical parameters to evaluate the robustness and reliability of these models. The parameters that were used were the precision, f1 score and recall. These parameters were selected as they can provide a robust answer to the question"How efficient are the models in picking up unsafe situations,keeping in mind that there is a major imbalance favoring safe classes over the unsafe ones?"The evidence displayed by Tables 2, 4 and 6 indicates that the artificial neural network(ANN) performed better compared to naive Bayes and logistic regression when it came to the prediction of unsafe cases. This research indicates that machine learning models built on neural networks algorithms perform better in their predictive capability in this type of situation. A further study into this research will include the use of more advanced deep learning models working in a hybrid approach with optimization algorithms like the Black Kite Algorithm(BKA).

Author Contributions: Initial concept, M.K.A.; formal analysis and investigation, R.M.; writing-original draft preparation,R.M.;writing-review and editing,R.M.and M.K.A.;supervision and guidance, M.K.A. All authors have read and agreed to the published version of the manuscript.

Funding: This research received no external funding.

Institutional Review Board Statement: Not applicable.

Informed Consent Statement: Not applicable.

Data Availability Statement: No additional data is available other than the dataset presented in the body of this work.

Conflicts of Interest: The authors declare no conflicts of interest.

### References

1.Peng,S. Longwall Mining; CRC Press: Boca Raton,FL,USA,2019.

2.Demirkan, D.C.; Duzgun, S.; Juganda, A.; Brune, J.; Bogin, G. Evaluation of time series artificial intelligence models for real-time/near-real-time methane prediction in coal mines. CIM J. 2022, 13, 97-106.[CrossRef]

3.United Nations: Economic Commission for Europe. Best Practice Guidance for Effective Methane Drainage and Use in Coal Mines;United Nations: New York,NY,USA,2010.

4.Gangrade, V.; Schatzel, S.; Harteis, S.; Addis, J. Investigating the impact of caving on longwall mine ventilation using scaled physical modeling. Min. Metall. Explor. 2019, 36, 729-740.[PubMed]

5. Kimiagar, S.; Najafi, V.; Witkowski, B.; Pietruszka, R.; Godlewski, M. High performance and low temperature coal mine gas sensor activated by UV-irradiation. Sci. Rep. 2018, 8, 16298.[CrossRef][PubMed]

6. Wu,X.;Cui,J.;Tong,R.;Li,Q.Research on Methane Measurement and Interference Factors in Coal Mines. Sensors 2022,22,5608.[CrossRef][PubMed]

7. Tutak,M.; Krenicky,T.;Pirnik,R.;Brodny,J.;Grebski,W.W.Predicting Methane Concentrations in Underground Coal Mining Using a Multi-Layer Perceptron Neural Network Based on Mine Gas Monitoring Data. Sustainability 2024, 16, 8388.[CrossRef]

8.Qu,H.;Shao,X.;Gao,H.;Chen,Q.;Guang,J.;Liu,C.A Prediction Model for Methane Concentration in the Buertai Coal Mine Based on Improved Black Kite Algorithm-Informer-Bidirectional Long Short-Term Memory. Processes 2025, 13, 205.[CrossRef]

9.Nie, Z.; Ma, H.; Zhang, Y. Research on Gaussian Plume Model of Gas Diffusion in Coal Mine Roadway Based on BP Neural Network Optimized by Genetic Algorithm. Proc. IOP Conf. Ser. Earth Environ. Sci. 2020, 526, 012158.[CrossRef]

10.Guo,R.;Xu,G.Research on coal mine gas concentration multi-sensor prediction model based on information fusion and GA-SVM.China Saf. Sci. J. 2013, 23, 34-38.

11. Luo,Z.;Zhai,H.;Tong,J.Incorporating multi-features and XGBoost algorithm for gas concentration prediction. China Min. Mag.2024,33,359-363,370.

12. Kozielski, M.; Sikora, M.; Wróbel, L. Data on methane concentration collected by underground coal mine sensors. Data Brief 2021,39,107457.[CrossRef][PubMed]

Disclaimer/Publisher's Note: The statements, opinions and data contained in all publications are solely those of the individual author(s) and contributor(s) and not of MDPI and/or the editor(s). MDPI and/or the editor(s) disclaim responsibility for any injury to people or property resulting from any ideas, methods, instructions or products referred to in the content.