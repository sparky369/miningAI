##### Information Fusion 118 (2025) 102976
Available online 31 January 2025
1566-2535/© 2025 Published by Elsevier B.V.
Contents lists available at ScienceDirect
Information Fusion
journal homepage: www.elsevier.com/locate/inffus
Full length article
Explainable artificial intelligence and advanced feature selection methods
for predicting gas concentration in longwall mining
Haoqian Chang a, Xiangqian Wang a,∗, Alexandra I. Cristea b,∗, Xiangrui Meng a, Zuxiang Hu a,
Ziqi Pan b
a Anhui University of Science and Technology, School of Economics and Management, Huainan, 232001, Anhui, China
b Durham University, Department of Computer Science, Durham, DH1 3LE, UK
A R T I C L E I N F O
```
Keywords:
```
```
Explainable artificial intelligence (XAI)
```
Multivariate time series prediction
```
Shapley additive explanations (SHAP)
```
Longwall mining safety
Gas concentration modelling
A B S T R A C T
Accurate prediction of gas concentrations at longwall mining faces is critical for safety production, yet current
methods still face challenges in interpretability and reliability. This study aims to enhance prediction accuracy
and model interpretability by employing advanced feature selection techniques. We integrate Shapley Additive
```
Explanations (SHAP) into feature selection process to identify and quantify the contributions of multivariate
```
features to gas concentration variations. The effectiveness of SHAP-based feature selection is systematically
evaluated alongside Principal Component Analysis, Dynamic Time Warping, and unfiltered features, across four
baseline predictive models chosen based on their structural characteristics: Long Short-Term Memory, Gated
Recurrent Unit, Transformer and Graph Neural Network. Using public dataset from the Upper Silesian coal
basin in Poland, we demonstrate that models trained with SHAP-selected features outperform baseline models,
particularly in terms of accuracy and reliability for long-term predictions. By identifying the most relevant
features and clarifying their interactions, this study enhances predictive performance and provides deeper
insights into the dynamics governing gas concentrations, emphasising the value of advanced, interpretable
feature selection techniques in developing robust models for industrial applications in mining.
1. Introduction
Predicting gas concentrations at longwall mining faces is essential
for ensuring mining safety [1]. In the semi-enclosed tunnel environ-
ment, underground monitoring data often display intricate coupling
patterns [2] and spatiotemporal correlations [3]. While the interactions
between various factors influencing gas concentration are apparent,
accurately quantifying and representing these interactions remains a
challenge [4]. To ensure precision in prediction, it is critical to identify
the most relevant and influential features from the extensive array
of underground sensors [5], as these key features directly impact the
prediction targets, thereby providing a robust foundation for reliable
prediction in complex mining environments [6].
However, determining the most influential factors is challenging
[7], particularly due to the linear and nonlinear coupling relationships
between monitoring data [8], which makes it more complex to identify
the features that have the greatest impact on gas concentration predic-
tions [9]. For instance, temperature variations influence gas behaviour
by altering solubility, while changes in airflow affect the diffusion
rates of gases [10]. These coupled factors intricately influence gas
dynamics in underground environments, exacerbated by the dynamic
∗ Corresponding authors.
```
E-mail addresses: xiqwang@aust.edu.cn (X. Wang), alexandra.i.cristea@durham.ac.uk (A.I. Cristea).
```
nature of mining operations, underscores the need for advanced meth-
ods to improve gas concentration predictions and ensure safety [11].
Refining feature selection in longwall mining operations necessitates
the adoption of advanced methodologies to accurately quantify and pri-
oritise the most influential factors affecting gas concentration, thereby
enhancing prediction accuracy amidst complex coupling challenges.
Feature selection is crucial for refining gas concentration predictive
models, particularly in mining environments where complex, non-
linear relationships between variables are prevalent [12]. This process
involves identifying the most relevant variables from extensive datasets
to enhance model accuracy and interpretability [13,14]. Techniques
```
such as principal component analysis (PCA) [15], dynamic time warp-
```
```
ing (DTW) [16], and Pearson correlation are commonly employed to
```
reduce dimensionality and highlight influential features [17]. However,
these methods often focus on statistical correlations, potentially over-
looking nuanced interactions and leading to a loss of critical informa-
tion [18]. To address these shortcomings, advanced methods such as ex-
```
plainable artificial intelligence (XAI) offer a promising alternative [19].
```
XAI techniques are capable of uncovering and elucidating the complex
```
https://doi.org/10.1016/j.inffus.2025.102976
```
```
Received 4 November 2024; Received in revised form 12 December 2024; Accepted 21 January 2025
```
```
Information Fusion 118 (2025) 102976
```
2
H. Chang et al.
dependencies influencing gas concentration variations with greater
clarity. Notably, XAI has been successfully applied in environmental
domains, including gully erosion [20], land subsidence [21], wildfire
susceptibility prediction [22], and dust emission assessments [23]. Inte-
grating these interpretative methods into gas concentration prediction
frameworks could significantly enhance transparency, reliability, and
practical applicability within mining contexts.
The advent of explainable artificial intelligence [24] further en-
hances the feature selection process. Explainable AI techniques, such as
```
SHapley Additive exPlanations (SHAP) [25,26] and Local Interpretable
```
```
Model-agnostic Explanations (LIME) [27], provide insights into the
```
contribution of each feature to the model’s predictions. These methods
not only improve the transparency of deep learning models but also
facilitate a deeper understanding of the underlying data interactions.
By leveraging explainable AI, researchers and engineers can ensure that
the selected features align with domain knowledge and operational
realities, thereby enhancing the reliability and trustworthiness of the
predictive models.
To advance this research, a comprehensive feature selection study
is proposed, focused on predicting gas concentrations specifically at
the upper corner of the coal mining face. The study employ four dis-
tinct feature selection methodologies—Principal Component Analysis
```
(PCA) [15], Dynamic Time Warping (DTW) [16], SHapley Additive ex-
```
```
Planations (SHAP) [25], and an unfiltered entire dataset to identify the
```
most pertinent sensor data influencing gas concentration. The identified
features will be evaluated across four baseline multivariate time series
prediction models, selected based on their structural architectures to
assess the effectiveness of the feature selection method under different
```
model frameworks: Long Short-Term Memory (LSTM) [28], Gated Re-
```
```
current Unit (GRU) [29], Transformer [30], and Graph Neural Network
```
```
(GNN) [31]. Each model will be run three times with varying sliding
```
window sizes and different random seeds to minimise experimental
error and enhance result reliability.
This approach enables a rigorous comparison of the effectiveness of
each feature selection method in enhancing the accuracy of gas concen-
tration predictions. Furthermore, it provides insights into the underly-
ing patterns within longwall mining face data, yielding interpretable
results that can inform safety measures.
The principal contributions of this paper are as follows:
• To the best of our knowledge, this is the first study to apply the
SHAP explanation method to investigate the coupled relationships
of gas concentration features at the longwall mining face.
• Using real-world data from longwall mining face, we comprehen-
sively evaluate methods for selecting gas concentration charac-
teristics at the mining face and rigorously validate their effective-
ness.
• Our study offers insights into the dynamics of gas concentration
at longwall mining face, contributing to the development of ro-
bust gas management strategies and enhanced safety measures in
mining operations.
2. Related work
Effective feature selection enhances model performance and in-
terpretability by reducing dimensionality and focusing on the most
impactful variables [32]. Those techniques include Principal Compo-
```
nent Analysis (PCA) [15], Mutual Information, and Recursive Feature
```
```
Elimination (RFE) [33]. Advanced methods such as SHapley Additive
```
```
exPlanations (SHAP) [34,35] and Local Interpretable Model-agnostic
```
```
Explanations (LIME) are also employed. These techniques facilitate
```
understanding of complex interactions among variables and improve
predictive accuracy in various applications.
Feature selection methods, while widely applied across various in-
dustrial sectors [36,37], remain relatively traditional within the mining
industry and have not yet reached the same level of diversity or
Table 1
Characteristics and measurement units of sensors.
Sensor characteristics
```
MM Methane (Gas concentration) (%CH4)
```
```
AN Anemometer (m/s)
```
```
TP Temperature (◦ C)
```
```
RH Humidity (%RH)
```
```
BA Barometer (hPa)
```
```
CM High concentration methane meter (%CH4)
```
```
AM/DM Mining equipment (A)
```
advancement. Liu et al. [38] introduced a hybrid feature selection
model for coal and gas outbursts, utilising random forest to identify the
most relevant features. Zhou et al. [39] used four basic feature selection
methods to identify optimal features and built predictive models with
classical machine learning algorithms. Miao et al. [40] developed a
coal mine rock burst risk prediction model using standard machine
learning and feature selection algorithms to identify key indicators.
Chen and Dong [41] implemented a sequential approach for water in-
flow prediction in coal mines, combining conventional feature selection
and optimisation techniques. De et al. [42] employed a multi-objective
feature selection model to remove redundant and irrelevant features,
enhancing fault diagnosis performance.
While these methods have improved safety and operational effi-
ciency, the mining industry still lags in adopting sophisticated, explain-
```
able AI (XAI) techniques. Integrating advanced XAI methods for feature
```
selection is essential to enhance model interpretability and trust.
3. Background
In this section, we present some background about longwall mining
face, highlight the challenges through an initial dataset analysis, and
define the research problem under investigation.
3.1. Dataset
The publicly available dataset used in this study was obtained from
the Upper Silesian coal basin in Poland [43]. Real-time data were
collected from the underground environment of the longwall mining
```
face, encompasses key environmental parameters such as Methane (Gas
```
```
concentration), Anemometer, Temperature, Humidity, Barometer etc.,
```
as detailed in Table 1, resulting in a high-frequency multidimensional
time series. The dataset includes temporal sensory readings from two
distinct sensor arrays, captured from March 2 to June 16, 2014. This
repository comprises 9, 199, 930 data instances, each detailed with a
timestamp and measurements from 28 sensors. Fig. 1 shows the mining
face layout from which the dataset was derived, where fresh airflow is
introduced from the intake airway, sweeping across the mining face and
expelling exhaust through the return airway. This trend is visualised
in Fig. 2, where observing the gas concentration variations over a 24-
```
h period (1440 min), it is a clear temporal dependency, and the data
```
exhibit an apparent co-movement pattern across the time series. Similar
temporal trends are also evident in the wind speed and temperature
variables. However, although the gas concentration migrates along
the airflow within the working face, a straightforward application of
correlation fails to capture this relationship.
Sensor point MM264 measures the gas concentration at the upper
corner of the mining face, located at the intersection of the return
airway and the roof. This region is a critical accumulation zone where
methane from the goaf and emissions generated during mining opera-
tions converge due to ventilation-induced airflow, resulting in elevated
localised concentrations. Given its significance in monitoring gas dy-
namics, this point is selected as the multivariate prediction target,
while data from other sensors are classified as either endogenous or
exogenous inputs. Endogenous data include sensor readings directly
associated with MM264, such as those from MM263 and MM256, which
```
Information Fusion 118 (2025) 102976
```
3
H. Chang et al.
Fig. 1. Structure of the longwall mining face and Naïve Pearson correlation analysis of gas concentration.
Fig. 2. Time series and statistical histogram of data from longwall mining face.
are located downstream along the gas flow path. During this process,
gas concentration gradually propagates from upstream positions, such
as MM261, to downstream sensors like MM256, creating a chain of
dynamic gas concentration distribution. In contrast, exogenous data
utilise additional information from peripheral areas of the mining face,
```
including the physical properties of the coal seam (e.g., gas content,
```
```
gas permeability) and environmental factors (e.g., face temperature,
```
```
humidity, and atmospheric pressure). Exogenous data provide critical
```
external context for understanding the spatio-temporal variations in gas
concentration patterns.
Direct correlation analysis reveals minimal linear association be-
```
tween nearby sensors (e.g., MM263 and MM264), as shown in Fig. 3.
```
The generally low correlation values across the dataset underscore the
complexity and nonlinearity of factors influencing gas concentration
```
Information Fusion 118 (2025) 102976
```
4
H. Chang et al.
Fig. 3. Pearson correlation heatmap of all sensor data in the longwall mining face.
Fig. 4. Pearson correlation of MM264 with various features across different window
sizes in the longwall mining face.
within the longwall mining face. Nonetheless, these findings offer
valuable prior insights. For instance, an analysis of average correla-
```
tion across different time windows (as shown in Fig. 4) illustrates
```
the influence of window size on sensor correlation. As the window
size increases, all sensor pairs display greater trend consistency at
larger window sizes even when the overall correlation remains low.
This observation suggests that by selecting an appropriate time win-
dow, it is possible to more effectively capture underlying patterns in
gas concentration fluctuations and identify latent associations between
sensors.
For all sensor configuration, as detailed in Table 2, includes the
minimum, maximum, mean, standard deviation, median, and data
length for each sensor, providing a comprehensive overview of their
distributions and variability. A variety of sensor types work together
to deliver holistic environmental monitoring, capturing factors that
Table 2
Statistical characteristics of sensor data.
Sensor Min Max Mean Std. Dev. Median Lengths
MM252 −0.1 30 0.038 0.121 0 9,199,930MM261 0 30 0.049 0.125 0 9,199,930
MM262 −0.2 30 0.051 0.136 0 9,199,930MM263 −2 30 0.248 0.197 0.2 9,199,930
MM264 −2 40 0.327 0.206 0.3 9,199,930MM256 0 30 0.43 0.204 0.4 9,199,930
MM211 −2 30 0.7 0.151 0.7 9,199,930
AN311 −266 5 3.484 0.611 3.6 9,199,930AN422 0 2.4 1.655 0.128 1.6 9,199,930
AN423 −2.4 5.3 1.498 0.33 1.4 9,199,930TP1721 0 27.9 25.477 0.932 25.4 9,199,930
TP1711 0 31.2 28.894 0.757 28.8 9,199,930RH1722 0 71 49.283 6.143 48 9,199,930
RH1712 0 86 68.687 7.268 69 9,199,930BA1723 0 1131.7 1106.161 7.625 1105.9 9,199,930
BA1713 0 1130.9 1105.597 7.617 1105.3 9,199,930
CM861 −0.2 67.7 32.92 21.395 43.7 9,199,930CR863 −8 258 75.081 55.161 78 9,199,930
P_864 0 435.4 86.967 29.158 94.2 9,199,930TC862 0 40.5 29.898 9.898 32.9 9,199,930
WM868 0 6.39 1.803 1.32 2.2 9,199,930
AMP1_IR −255 988 5.854 24.413 0 9,199,930AMP2_IR −255 1009 5.741 24.25 0 9,199,930
DMP3_IR −255 216 4.201 17.342 0 9,199,930DMP4_IR −255 198 3.97 17.313 0 9,199,930
AMP5_IR −255 121 0.414 10.966 0 9,199,930V 0 100 1.347 5.997 0 9,199,930
impact the longwall environment. This multi-sensor data enables con-
tinuous assessment and adjustment, supporting accurate upper corner
monitoring and promoting safe production.
3.2. Problem definition
The objective of multivariate gas concentration prediction is to
estimate future trends in gas concentration across the longwall mining
face. This is achieved using multidimensional time-series data collected
from multiple sensors, encompassing various influencing factors. Let
```
𝐗 = {𝐱𝑡}𝑇𝑡=1 represent the multivariate time series data collected by a
```
network of sensors, where each 𝐱𝑡 ∈ R𝑑 is a 𝑑-dimensional observation
```
vector at time 𝑡. Specifically, 𝐱𝑡 = [𝑥(1)𝑡 , 𝑥(2)𝑡 , … , 𝑥(𝑑)𝑡 ]⊤, with 𝑥(𝑖)𝑡 indicat-
```
ing the reading from the 𝑖th sensor at time 𝑡, such as gas concentration,
```
wind speed, or temperature. The target variable, denoted as 𝐘 = {𝑦𝑡}𝑇𝑡=1,
```
represents the observed gas concentration at each time 𝑡.
Based on the above definitions, the multivariate gas concentration
prediction problem can be formulated as a time-series regression task,
```
aiming to learn a non-linear mapping function 𝑓 (⋅) such that:
```
```
̂𝑦 𝑡+𝜏 = 𝑓 (𝐱𝑡, 𝐱𝑡−1, … , 𝐱𝑡−𝑛+1; 𝜃) (1)
```
where 𝜃 represents the model parameters, 𝑛 is the input time series
window length, 𝜏 is the prediction horizon, and̂ 𝑦 𝑡+𝜏 is the model’s
predicted gas concentration at future time 𝑡 + 𝜏.
To capture the dynamic characteristics of gas concentration, we
employ a fixed-length time window of size 𝑛, utilising observations
from the past 𝑛 time steps to forecast the gas concentration at future
time 𝑡 + 𝜏. Specifically, the input data matrix 𝐗𝑡 ∈ R𝑛×𝑑 is defined as:
```
𝐗𝑡 = [𝐱𝑡−𝑛+1, 𝐱𝑡−𝑛+2, … , 𝐱𝑡]⊤ (2)
```
The model’s objective is to minimise the loss function  between
the predicted valueŝ 𝑦 𝑡+𝜏 and the true values 𝑦𝑡+𝜏 , typically using the
```
mean squared error (MSE):
```
```
(𝜃) = 1𝑁
```
𝑁∑
𝑖=1
```
(
```
𝑦𝑡𝑖+𝜏 −̂𝑦 𝑡𝑖+𝜏
```
)2
```
```
(3)
```
where 𝑁 is the number of training samples.
```
Information Fusion 118 (2025) 102976
```
5
H. Chang et al.
Fig. 5. Framework for multivariate gas concentration prediction in longwall mining face using feature selection techniques.
```
Based on existing studies (e.g., [30,44]), the time window length 𝑛
```
is commonly set to 24, 48, 96 and 168 time steps to capture periodic
fluctuations and trends in the data. In this study, the time window
length 𝑛 is set to [24, 48, 96, 168], and the prediction horizon 𝜏 is
```
set to 12. The prediction can thus be expressed as 𝑓 (⋅), enabling it to
```
utilise multivariate observations from the past 𝑛 time steps to accurately
forecast the gas concentration 𝜏 time steps ahead:
```
̂𝑦 𝑡+𝜏 = 𝑓 (𝐗𝑡; 𝜃) (4)
```
```
By minimising the loss function (𝜃), we optimise the model param-
```
eters 𝜃 to improve prediction accuracy.
4. Methodology
This section provides a detailed description of the framework for
multivariate gas concentration prediction in the longwall mining face
using feature selection techniques. Followed by a discussion of the
various feature selection methods employed, and the baseline models
used for multivariate time series prediction.
4.1. Multivariate time series feature selection methods
Given the extensive dataset obtained from the Upper Silesian coal
basin, comprising over nine million data instances collected from 28
sensors, identifying the most relevant features is paramount for effec-
tive model training and prediction. We plan to employ four differ-
ent methods for feature selection and compare their efficacy: SHAP
```
(SHapley Additive exPlanations), PCA (Principal Component Analysis)
```
```
with 95% confidence, DTW (Dynamic Time Warping), and a baseline
```
approach which is no feature selection. SHAP offer a robust and inter-
pretable way to determine the importance of each feature, providing
clear insights into their contributions to the prediction accuracy. PCA
with 95% confidence effectively reduces dimensionality by capturing
the majority of the data’s variance, simplifying the dataset while retain-
ing the most significant information. DTW measures temporal similarity
between time series, making it ideal for aligning features with similar
temporal patterns to the target variable, even if they are shifted in time.
And by using all features serves as a control to evaluate the raw data’s
predictive power and the overall impact of feature selection methods.
This study compares and evaluates the effectiveness of SHAP, PCA,
DTW, and a baseline approach in selecting the most relevant features,
as illustrated in Fig. 5, covering data collection, feature selection, and
multivariate time series prediction. This comparison seeks to identify
the optimal method for enhancing the accuracy and interpretability of
gas concentration predictions in longwall mining operations.
4.1.1. SHAP
```
SHAP (Shapley Additive exPlanations) [25], which harnesses the
```
Shapley values from cooperative game theory [45], provides a solid
theoretical foundation for assigning contributions to individual features
within predictive models. The explanation model can be simplified as
```
Eq. (5).
```
```
𝑔(𝑥′) = 𝜙0 +
```
𝑀∑
𝑖=1
```
𝜙𝑖𝑥′𝑖 (5)
```
```
where 𝑥′ ∈ {0, 1}𝑀 , 𝜙𝑖 ∈ R and 𝑀 symbolises the quantity of simplified
```
input features, as also proposed in LIME [27]. Portraying an explana-
tory model 𝑔 as a linear function wherein binary variables signify the
inclusion or exclusion of input features from the original model 𝑓 . In
LIME, the contribution of each feature 𝜙𝑖 is represented through a linear
summation of the model’s predictions, presuming the independence of
features. Contrastingly, SHAP, which is an instantiation of an additive
feature attribution method, employs Shapley values to apportion the
contribution of each feature to the model’s prediction, which can be
```
defined as in Eq. (6)
```
𝜙𝑖 = ∑
```
𝑆 ⊆𝐹 ⧵{𝑖}
```
```
|𝑆|!(|𝐹 | − |𝑆| − 1)!
```
|𝐹 |!
[𝑓
```
𝑆∪{𝑖}(𝑥𝑆∪{𝑖}) − 𝑓𝑆 (𝑥𝑆 )
```
```
] (6)
```
where 𝐹 represents the ensemble of features, 𝑆 denotes a subset of 𝐹
excluding feature 𝑖, and 𝜙𝑖 indicates the predictive outcome of model 𝑓
```
employing solely the feature set 𝑆. The function 𝑓𝑆∪{𝑖}(𝑥𝑆∪{𝑖}) − 𝑓𝑆 (𝑥𝑆 )
```
```
Information Fusion 118 (2025) 102976
```
6
H. Chang et al.
Fig. 6. Euclidean distance and dynamic time warping.
```
gives the prediction with feature 𝑖, while 𝑓𝑆 (𝑥𝑆 ) gives the prediction
```
without it. Each feature’s influence is deduced by assessing the model’s
prediction in both scenarios: the inclusion and exclusion of the feature,
averaged over all conceivable subsets. Consequently, SHAP transcends
the basic linear model, emerging as an intricate explanatory frame-
work that accounts for the interdependencies and interactions amongst
features.
Compared with LIME, SHAP’s approach is founded on theoretical
underpinnings of cooperative game theory, ensuring equitable and
consistent distribution of attributions amongst features. Distinct from
LIME’s penchant for localised approximations – prone to yielding in-
terpretations that are accurate within a narrow context, but may falter
on a universal scale – SHAP considers the full spectrum of the dataset
```
in evaluating feature significance. And unlike PI (Permutation Impor-
```
```
tance) [46], SHAP calculates the imputation of predictions rather than
```
model performance, which makes it easy to interpret. The aggregate
of SHAP values for all features precisely equates to the deviation of
the model’s prediction from a predetermined baseline. This principle
resonates with the logical presumption that the sum of contributions
from all features should correspond with the variation in output. Such
a quality is especially beneficial for elucidating a clear and coherent
delineation of feature contributions, bolstering the intelligibility and
transparency of the model’s interpretative process. This is the main
reason why the SHAP method was chosen for this research.
```
4.1.2. PCA (principal component analysis) with 95% confidence
```
```
Principal component analysis (PCA) [15], a well-established di-
```
mensionality reduction technique, addresses the challenge of high-
dimensional data by transforming the original features into a new set
of mutually orthogonal principal components through linear transfor-
mation. These components are ranked by the variance they explain,
with the first few typically capturing the majority of the data’s informa-
tional content. In this study, we selected the principal components that
explain 95% of the variance to reduce data dimensionality. Although
PCA is an unsupervised feature selection method that does not rely on
the target variable and can simplify the data by reducing the number
of features, it is employed here primarily for comparison with other
methods. While PCA can lower computational complexity and retain
essential data information, its utility in this context is as a benchmark
against more targeted approaches.
```
4.1.3. DTW (Dynamic Time Warping)
```
```
Dynamic Time Warping (DTW) [16] offers a solution to this lim-
```
itation by allowing for adjustments along the time axis, aligning two
sequences to effectively identify similar patterns, especially when there
are temporal offsets or delays. For assessing the similarity between two
Fig. 7. LSTM units.
Fig. 8. GRU units.
temporal sequences, regardless of their alignment or length differences.
In the coal mining context, accurately tracking gas movement from one
sensor to another is complicated by wind-induced timing variances.
Fig. 6 illustrates a comparison between DTW and Euclidean distances.
DTW achieves this by flexibly aligning the sequences, addressing
challenges associated with temporal offsets and scaling. For two sen-
```
sors, 𝑆 𝑒𝑛𝑠𝑜𝑟1 = {𝑥1, 𝑥2, … , 𝑥𝑛} and 𝑆 𝑒𝑛𝑠𝑜𝑟2 = {𝑦1, 𝑦2, … , 𝑦𝑚}, the DTW
```
distance, denoted as 𝐷[𝑛][𝑚].
4.2. Multivariate time series prediction models
In this study we selected four time series prediction models, which
```
are Long short-term memory (LSTM) as baseline model [28] by intro-
```
ducing a gating mechanism, it successfully addresses the common issues
of gradient vanishing and exploding in long time series data, making
it widely used in time series prediction. LSTM units control the flow
of information through input gates, forget gates, and output gates as
shown in Fig. 7, which allowing the LSTM to retain dependencies over
long time spans. This gating mechanism enables LSTMs to selectively
retain or forget information, adapting to different time series patterns.
```
Gated recurrent units (GRU) [29] as shown in Fig. 8 is a simplified
```
variant of LSTM, designed to reduce model complexity while maintain-
ing the ability to handle long-term dependencies. GRU merges the input
gate and forget gate into a single update gate, simplifying the com-
putation process. Additionally, GRU uses reset gates and update gates
to control the updating and resetting of information flow, balancing
computational efficiency and performance.
The Transformer mechanism as shown in Fig. 9, by introducing a
self-attention mechanism, significantly enhances the capability of time
series prediction, particularly in capturing long-term dependencies.
Compared to traditional RNN models, Transformers [30] are better
at capturing global dependencies in long time series and offer higher
parallel efficiency during training. This makes Transformers especially
```
Information Fusion 118 (2025) 102976
```
7
H. Chang et al.
Fig. 9. Attention mechanism.
Fig. 10. Graph neural networks prediction.
suitable for applications that require handling high-dimensional, mul-
tivariate time series data, such as comprehensive environmental data
analysis in coal mine safety monitoring.
Despite the commendable performance of models such as LSTM,
GRU and Transformers in handling time-series data, commonly applied
in industrial settings such as real-time gas concentration monitoring
in longwall mining faces [47], these approaches inherently struggle
with capturing the non-Euclidean spatial dependencies underlying com-
plex gas diffusion patterns. As a result, interpreting interdependencies
among various monitoring points remains challenging, limiting the
overall accuracy of spatiotemporal predictions.
```
In contrast, Graph Neural Networks (GNNs) [31] explicitly model
```
spatial relationships by representing monitoring points as graph nodes
and their interactions as edges [48,49]. As shown in Fig. 10, variables
such as gas concentration, temperature, and airflow velocity within
the historical interval [𝑡 − 𝑆 , 𝑡] form the input nodes, with spatial or
physical connections defined as edges. This structure leverages both
spatial and temporal dimensions, facilitating forecasts from 𝑡 + 1 to
𝑡 + ℎ that more accurately represent diffusion pathways and delayed
propagation effects across multiple monitoring locations.
4.3. Evaluation criterion
```
We use mean absolute error (MAE), mean squared error (MSE),
```
```
root mean squared error (RMSE), and mean absolute percentage error
```
```
(MAPE) as performance metrics to evaluate the models, defined in
```
```
Eqs. (7), (8), (9), and (10) respectively.
```
𝑀 𝐴𝐸 = 1𝑁
𝑁∑
𝑖=1
```
|𝑦𝑖 −̂𝑦 𝑖| (7)
```
𝑀 𝑆 𝐸 = 1𝑁
𝑁∑
𝑖=1
```
(𝑦𝑖 −̂𝑦 𝑖)2 (8)
```
𝑅𝑀 𝑆 𝐸 =
√√
√√ 1
𝑁
𝑁∑
𝑖=1
```
(𝑦𝑖 −̂𝑦 𝑖)2 (9)
```
𝑀 𝐴𝑃 𝐸 = 1𝑁
𝑁∑
𝑖=1
||
||
𝑦𝑖 −̂𝑦 𝑖
𝑦𝑖
||
```
|| × 100% (10)
```
5. Experiments and results
5.1. Feature selection results
The final results of the feature selection methods as shown in Fig. 11
```
including Principal Component Analysis (PCA), SHAP, and Dynamic
```
```
Time Warping (DTW)—distinguished by different colours. The figure
```
illustrates the layout of sensors in a coal mining face and the application
of the feature selection methods to each sensor, excluding the pipeline
extraction of gas P864. The primary target is the MM264 sensor at
the upper corner, highlighted with a purple arrow to indicate it as
the targets for feature selection. Sensors marked with blue borders rep-
```
resent features selected using the SHAP method; red borders indicate
```
```
those selected using DTW; and yellow borders denote features selected
```
using PCA95. Some sensors, such as MM256, MM263, and MM211, are
consistently selected by multiple methods, highlighting their signifi-
cance in the feature selection process. The baseline approach utilises
all 28 sensors for model training and prediction. In contrast, PCA, used
as an unsupervised method, selected fifteen features. The supervised
SHAP method identified the nine most relevant features, and DTW also
selected nine features for comparison. The diagram also shows the wind
direction and the layout of the mine passages.
A summary plot of SHAP values illustrates the importance of each
feature in the gas concentration prediction model and the direction
of their impact, as shown in Fig. 12. Where the vertical axis lists
features that significantly affect prediction performance, including
MM263, BA1723, and MM211. Positive or negative SHAP values in-
dicate whether each feature has a positive or negative influence on the
model output, while the colour reflects the magnitude of the feature
values. This representation reveals the importance of key features, facil-
itating the identification and analysis of the main driving factors behind
gas concentration changes in longwall mining environments, thereby
providing a reference for feature selection and model optimisation.
To demonstrate how the impact of each feature on the model output
varies across different instances, a SHAP value heatmap is utilised in
Fig. 13. The horizontal axis represents different instances, while the
```
vertical axis lists a set of key features. Colours ranging from blue (neg-
```
```
ative impact) to red (positive impact) depict the dynamic contribution
```
of each feature to the prediction output. The model output trend at the
top provides context for the feature impacts, making it easier to observe
the relationship between feature variations and output changes. This
indicates that the influence of key features dynamically changes under
different operating conditions, revealing complex relationships within
the predictive model and aiding in understanding the actual role of
features in gas concentration prediction.
Furthermore, the ranking of average absolute SHAP values of key
features under different time windows quantifies the influence of each
feature on gas concentration prediction. As in Fig. 14, the horizontal
axis represents the average SHAP value of the features, where larger
values indicate a more important impact on the model output. Features
MM211 and MM263 exhibit the highest average SHAP values, indicat-
ing they play a major role in the prediction. Additionally, features like
BA1723 and MM211 have a high impact under different time windows,
reflecting the dynamic influence of time window selection on feature
importance.
In Fig. 15, an analysis of the average SHAP values of features
MM211 and MM263 under different time windows further evaluates
the impact of the time window on feature importance. The distribution
of average SHAP values for the MM211 feature at different window
```
Information Fusion 118 (2025) 102976
```
8
H. Chang et al.
Fig. 11. Comparison of features selected for gas concentration prediction.
Fig. 12. SHAP summary plot of feature importance and distribution.
Fig. 13. SHAP values for feature impact analysis on model output.
```
sizes (24, 48, 96, and 168) shows that its influence on the prediction is
```
significantly higher at a window size of 48 compared to other settings.
Fig. 14. Mean absolute SHAP value ranking of key features across different window
sizes.
Similarly, the average SHAP value distribution for the MM263 feature
indicates that its influence is most prominent at a window size of 24,
gradually diminishing as the window size increases.
5.2. Experimental details
In this study, we evaluated four deep learning architectures for
multivariate gas concentration prediction: Long Short-Term Memory
```
(LSTM) networks, Gated Recurrent Units (GRU), Transformers, and
```
```
Graph Neural Networks (GNN), for a more detailed architecture see
```
Table 3. The dataset was partitioned with an 80:20 ratio, reserving 80%
for training and 20% for testing. Each model was trained and tested on
identical datasets with input sequence lengths of [24, 48, 96, 168] time
steps and a prediction horizon of 12 time steps.
Experimental was conducted on AMD EPYC 7542 32-Core Processor
with NVIDIA GeForce RTX 3090 GPUs, running on Ubuntu 22.04.1 LTS
Jellyfish. The software setup included Python 3.7 and PyTorch with
CUDA 11.2.
```
Information Fusion 118 (2025) 102976
```
9
H. Chang et al.
Fig. 15. Mean SHAP value analysis of feature importance across different time
windows for MM211 and MM263.
All models were trained using consistent hyperparameters and
training configurations to ensure a fair comparison. Common settings
included Adam optimiser with an initial learning rate of 1 × 10−4,
which decayed by a factor of 0.5 after each epoch to facilitate conver-
gence [44]. Training was conducted for up to 100 epochs with early
stopping based on validation loss to prevent overfitting. A batch size of
64 was used across all experiments and a teacher forcing ratio of 0.5
was applied during training.
5.3. Gas concentration prediction performance
We evaluated multiple models across various sliding time windows,
employing sequence lengths of 24, 48, 96, and 168. This approach
captures temporal dependencies at multiple scales. The dataset was
split into an 80%:20% ratio for training and testing, respectively, and
```
we compared four baseline models—Long Short-Term Memory (LSTM),
```
```
Gated Recurrent Unit (GRU), Transformer, and Graph Neural Net-
```
```
work (GNN)—alongside their feature selection-enhanced counterparts:
```
SHAP, PCA95, and DTW-improved versions. The results are presented
in Tables 4 and 5. We report MSE, MAE, RMSE, and MAPE to provide a
comprehensive assessment of predictive accuracy and error character-
istics. MSE and RMSE are more sensitive to larger errors, MAE captures
the average absolute error, and MAPE reflects the relative percentage
error with respect to actual values.
Among the evaluated models, the SHAP GNN consistently demon-
strates low prediction errors across all sequence lengths. For example,
with a sequence length of 24, the SHAP GNN attains an MSE of
0.0406 and MAE of 0.1318, coupled with an RMSE of 0.2015 and
MAPE of 0.4834. These values indicate that the SHAP GNN not only
maintains high accuracy but also effectively handles instances where
larger prediction errors might occur. Its stability is evident even at a
sequence length of 168, where MSE remains at 0.0410 and MAE at
0.1301, suggesting that the model adapts well to longer input sequences
without significant performance deterioration.
Comparatively, the original GNN model also shows good perfor-
mance but with slightly higher error metrics than the SHAP GNN. For
example, with a sequence length of 96, the original GNN has an MSE
of 0.0427, whereas the SHAP GNN’s MSE is 0.0402. This difference
may be attributed to the effectiveness of the SHAP feature selection
method in extracting important features, thereby reducing the MSE and
RMSE, which enhances predictive accuracy, especially for larger errors.
Baseline models such as LSTM and GRU exhibit relatively high error
metrics without feature selection. For instance, the original LSTM with
a sequence length of 48 has an MSE of 0.1292, MAE of 0.1896, RMSE
of 0.3595, and MAPE of 0.6346, indicating larger average prediction
errors and less accuracy in predicting instances with larger errors.
Incorporating SHAP feature selection reduces the error metrics of the
```
LSTM model; at the same sequence length, the SHAP LSTM reduces the
```
MSE to 0.0721, MAE to 0.1085, RMSE to 0.2685, and MAPE to 0.4925,
demonstrating that the feature selection method effectively reduces the
average absolute prediction error and relative error.
The original GNN model also yields robust results, though its error
metrics are slightly higher than those of the SHAP GNN. For instance,
at a sequence length of 96, the original GNN has an MSE of 0.0427,
whereas the SHAP GNN reduces it to 0.0402. This improvement high-
lights the effectiveness of SHAP-based feature selection, which appears
to preserve and emphasise critical features more effectively than meth-
ods like PCA95. In contrast, baseline models such as LSTM and GRU
without feature selection generally report higher error metrics. For
example, an LSTM at a sequence length of 48 exhibits an MSE of 0.1292
and MAE of 0.1896, values that are notably reduced when SHAP feature
```
selection is applied (MSE = 0.0721, MAE = 0.1085). The incorporation
```
of SHAP thus aids these models in better identifying and focusing on
key input features, subsequently lowering both absolute and relative
prediction errors.
The effect of feature selection methods varies by model. While
SHAP consistently lowers the errors across different model architec-
tures – most notably with GNN – PCA95 sometimes increases error
metrics, likely due to the loss of critical feature information through
dimensionality reduction. For example, the PCA95 LSTM at a sequence
length of 24 records an MSE of 0.0924, exceeding the original LSTM’s
MSE of 0.0825. Similarly, the Transformer model performs well at
shorter sequence lengths but does not show a clear advantage at longer
intervals, even after applying SHAP. For example, though the SHAP
Transformer improves upon the original Transformer at a sequence
```
length of 48 (MSE from 0.0863 down to 0.0701), its performance does
```
not continue to improve at longer sequence lengths, indicating that the
Transformer’s capacity for modelling extended input sequences may not
fully align with these feature selection strategies.
In summary, the SHAP GNN model demonstrates superior overall
performance, consistently delivering low MSE, MAE, RMSE, and MAPE
values across diverse sequence lengths. This finding underscores the
potential of SHAP to highlight critical variables more effectively than
PCA or DTW. Although other models also benefit from SHAP-based
feature selection to varying degrees, the gains are most pronounced
for the GNN, suggesting that integrating topological structures with
judiciously selected features is especially beneficial for accurate and
stable gas concentration predictions.
5.4. Final predictions
The final predictions are displayed in Fig. 16, based on the results
```
summarised in Tables 4 and 5. In particular, Fig. 16(a)–(d) present the
```
predicted time-series curves of gas concentration across four different
```
models. Fig. 16(e)–(h) illustrate scatter plots of prediction accuracy,
```
with the 45-degree diagonal line representing ideal agreement between
```
predicted and target values; the closer the points are to this line, the
```
```
higher the model’s prediction accuracy. Fig. 16(i)–(l) further provide
```
a magnified view of specific regions from the second layer of scatter
plots, highlighting the effects of different feature selection methods on
local prediction accuracy in gas concentration prediction.
The performance of different models – including LSTM, GRU, Trans-
former, and GNN – exhibits notable variations in gas concentration
prediction. As illustrated in Fig. 16. It can be observed that LSTM
and GRU exhibit larger prediction errors in certain intervals, while the
```
Transformer and GNN models (particularly the SHAP-based variants)
```
produce predictions that are closer to the target values, as shown in
```
Fig. 16(c) and (d). In handling outliers, the SHAP-based Transformer
```
```
Information Fusion 118 (2025) 102976
```
10
H. Chang et al.
Table 3
Summary of model hyperparameters.
Method Hyperparameters Value
LSTM
Hidden dimension 512
Number of layers 3 layers
Activation function Tanh and Sigmoid
Sequence length [24, 48, 96, 168]
Batch size 64
```
Optimiser Adam; Initial learning rate of 1𝑒−4 , decaying two times smaller every epoch
```
Dropout rate 0.05
Number of runs 3 times with random seed
Epochs 100
Early stopping Yes
GRU
Hidden dimension 512
Number of layers 3 layers
Activation function Tanh and Sigmoid
Sequence length [24, 48, 96, 168]
Batch size 64
```
Optimiser Adam; Initial learning rate of 1𝑒−4 , decaying two times smaller every epoch
```
Dropout rate 0.05
Number of runs 3 times with random seed
Epochs 100
Early stopping Yes
Transformer
Hidden dimension 512
Number of layers 4 Encoder/Decoder layers
Activation function ReLU
Sequence length [24, 48, 96, 168]
Batch size 64
```
Optimiser Adam; Initial learning rate of 1𝑒−4 , decaying two times smaller every epoch
```
Dropout rate 0.05
Number of runs 3 times with random seed
Epochs 100
Other parameters Attention heads = 8
Early stopping Yes
GNN
Hidden dimension 512
Number of layers Determined by block size = 3
Activation function ReLU
Sequence length [24, 48, 96, 168]
Batch size 64
```
Optimiser Adam; Initial learning rate of 1𝑒−4 , decaying two times smaller every epoch
```
Dropout rate 0.05
Number of runs 3 times with random seed
Epochs 100
Early stopping Yes
Table 4
```
Baseline and feature selection enhancements for multivariate long-sequence time-series prediction results (MSE and MAE).
```
Methods 24 48 96 168
MSE MAE MSE MAE MSE MAE MSE MAE
LSTM [28] 0.0825 0.1544 0.1292 0.1896 0.0940 0.1697 0.1023 0.1729
GRU [29] 0.0821 0.0945 0.1048 0.1843 0.0893 0.1571 0.0869 0.1462
Transformer [30] 0.0774 0.1245 0.0863 0.1118 0.0815 0.1161 0.0872 0.1158
GNN [31] 0.0429 0.1404 0.0428 0.1403 0.0427 0.1398 0.0443 0.1392
SHAP LSTM 0.0720 0.1124 0.0721 0.1085 0.0737 0.1067 0.0671 0.1057
SHAP GRU 0.0746 0.1024 0.0750 0.1006 0.0773 0.1053 0.0745 0.1009
SHAP Transformer 0.0751 0.1003 0.0701 0.1000 0.0884 0.1112 0.0826 0.1048
SHAP GNN 0.0406 0.1318 0.0418 0.1332 0.0402 0.1262 0.0410 0.1301
PCA95 LSTM 0.0924 0.1507 0.1024 0.1804 0.0960 0.1574 0.1023 0.1692
PCA95 GRU 0.0912 0.1497 0.1020 0.1737 0.1001 0.1666 0.0976 0.1596
PCA95 Transformer 0.0803 0.1208 0.0869 0.1210 0.0870 0.1223 0.0868 0.1138
PCA95 GNN 0.04285 0.1402 0.0428 0.1403 0.0470 0.1459 0.0426 0.1392
DTW LSTM 0.0774 0.1113 0.0788 0.1178 0.0772 0.1143 0.0802 0.1148
DTW GRU 0.0832 0.1134 0.0818 0.1084 0.0796 0.1070 0.0828 0.1061
DTW Transformer 0.0917 0.1170 0.0894 0.1137 0.0865 0.1008 0.0776 0.1013
DTW GNN 0.0428 0.1393 0.0430 0.1405 0.0430 0.1398 0.0427 0.1403
```
and GNN models (in blue) outperform models using PCA and DTW.
```
```
In Fig. 16(e)–(h), the comparison between the models’ predicted val-
```
ues and the actual values is illustrated through scatter plots, where GNN
```
model (Fig. 16(h)) is generally denser and closer to the 45-degree line,
```
especially with the assistance of the SHAP feature selection method,
which further enhances prediction accuracy. Moreover, in magnified
```
local regions Fig. 16(i)–(l), the impact of SHAP feature selection on
```
enhancing model accuracy becomes more pronounced, rendering the
model more sensitive in selecting critical features. The effects of differ-
ent feature selection methods on fine-grained predictions are further
demonstrated. Notably, the prediction results using the SHAP feature
```
selection method (marked with blue points) are denser and closer to
```
the diagonal line, indicating the efficacy of SHAP in refining feature
selection. This leads to higher prediction accuracy in local regions and
```
Information Fusion 118 (2025) 102976
```
11
H. Chang et al.
Table 5
```
Baseline and feature selection enhancements for multivariate long-sequence time-series prediction results (RMSE and MAPE).
```
Methods 24 48 96 168
RMSE MAPE RMSE MAPE RMSE MAPE RMSE MAPE
LSTM [28] 0.2873 0.6054 0.3595 0.6346 0.3067 0.5620 0.3199 0.6374
GRU [29] 0.2713 0.6031 0.3238 0.8112 0.2988 0.7405 0.2948 0.6822
Transformer [30] 0.2783 0.5243 0.2939 0.5018 0.2855 0.5209 0.2954 0.5525
GNN [31] 0.2070 0.5032 0.2069 0.4963 0.2066 0.4831 0.2105 0.5122
SHAP LSTM 0.2683 0.4979 0.2685 0.4925 0.2716 0.4945 0.2591 0.4949
SHAP GRU 0.2732 0.4961 0.2739 0.5033 0.2781 0.5045 0.2729 0.4918
SHAP Transformer 0.2740 0.4956 0.2649 0.4890 0.2973 0.5295 0.2874 0.5019
SHAP GNN 0.2015 0.4834 0.2045 0.4719 0.2004 0.4632 0.2024 0.4873
PCA95 LSTM 0.3040 0.5709 0.3200 0.6174 0.3099 0.5402 0.3198 0.5889
PCA95 GRU 0.3019 0.7403 0.3195 0.8383 0.3164 0.8430 0.3124 0.6867
PCA95 Transformer 0.2834 0.4899 0.2948 0.5417 0.2949 0.5064 0.2946 0.5068
PCA95 GNN 0.2090 0.5178 0.2070 0.5026 0.2165 0.5068 0.2064 0.5126
DTW LSTM 0.2783 0.4931 0.2808 0.4971 0.2779 0.4944 0.2832 0.5152
DTW GRU 0.2885 0.5077 0.2860 0.5001 0.2821 0.4898 0.2878 0.4883
DTW Transformer 0.3029 0.5037 0.2991 0.5291 0.2941 0.5094 0.2786 0.4933
DTW GNN 0.2069 0.4989 0.2074 0.5015 0.2073 0.4921 0.2067 0.4986
Fig. 16. Performance comparison of feature selection methods across different prediction models.
reduces the deviation of outlier points. This outcome is particularly
```
evident in the GNN model (Fig. 16(l)); in regions where all four feature
```
selection methods perform well, the SHAP method predicts even more
accurately, causing the blue scatter points to almost adhere to the
diagonal line, demonstrating strong predictive consistency.
The experimental results show that SHAP-based feature selection
outperforms traditional methods like PCA and DTW in multivariate
time series prediction. SHAP more effectively captures complex pat-
terns, improves accuracy, and enhances model stability by reducing
residuals and managing outliers.
```
Fig. 17 illustrates the computational time per epoch (in seconds)
```
for various predictive models – LSTM, GRU, Transformer, and GNN
– and their enhanced versions using SHAP, PCA95, and DTW feature
selection methods. Models are evaluated across prediction horizons of
24, 48, and 168 time steps, represented by red, green, and blue bars, re-
spectively. The top graph compares the original feature set with SHAP-
selected features, showing that SHAP-enhanced models, particularly the
Transformer and GNN, generally reduce computational time per epoch.
The bottom graph contrasts PCA95 and DTW feature selection methods,
indicating that PCA95-enhanced models exhibit consistent computa-
tional times across different horizons, while DTW-selected features may
increase computational time in GRU and Transformer models due to
added complexity.
6. Conclusion
This study underscores the crucial role of advanced feature selection
in predicting gas concentrations at longwall mining faces. By applying
and comparing four feature selection techniques—SHAP, PCA, DTW,
and an unfiltered baseline across multiple prediction models, SHAP
emerged as the most effective method for enhancing both model ac-
curacy and interpretability. The SHAP-based approach delivered more
precise predictions while offering critical insights into the interdepen-
dencies among key variables, thereby deepening the understanding of
```
Information Fusion 118 (2025) 102976
```
12
H. Chang et al.
Fig. 17. Time consumption.
gas concentration dynamics. These results highlight the importance
of sophisticated feature selection in developing robust models, espe-
cially within complex, high-dimensional datasets typical of industrial
environments. However, the study’s generalisability is limited, as the
dataset may not fully reflect the variability across diverse mining
environments, and the SHAP-based interpretability may not sufficiently
explain anomalies in model outputs, which are critical for early warn-
ing. Our future work will focus on validating these methods across
diverse datasets and developing advanced interpretability techniques to
better capture and explain outliers. Aims to support more robust early-
warning systems, refine feature selection processes, and strengthen
model reliability in practical applications.
CRediT authorship contribution statement
Haoqian Chang: Writing – original draft, Software, Methodol-
ogy. Xiangqian Wang: Resources, Funding acquisition, Data curation.
Alexandra I. Cristea: Writing – review & editing, Supervision. Xian-
grui Meng: Supervision, Funding acquisition. Zuxiang Hu: Writing –
review & editing. Ziqi Pan: Data curation.
Funding
This work was financially supported by the National Natural Science
```
Foundation of China (Grant nos. 52374074, 51874003, 51474007).
```
Declaration of competing interest
The authors declare that they have no known competing finan-
cial interests or personal relationships that could have appeared to
influence the work reported in this paper.
Data availability
Data will be made available on request.
References
[1] C. Fan, L. Xu, D. Elsworth, M. Luo, T. Liu, S. Li, L. Zhou, W. Su, Spatial–
temporal evolution and countermeasures for coal and gas outbursts represented
```
as a dynamic system, Rock Mech. Rock Eng. 56 (9) (2023) 6855–6877.
```
[2] J. Diaz, Z. Agioutantis, D.T. Hristopulos, S. Schafrik, K. Luxbacher, Time series
```
modeling of methane gas in underground mines, Min. Met. Explor. 39 (5) (2022)
```
1961–1982.
[3] D. Palka, P. Blistan, H. Badura, Forecast of the maximum methane concentration
in the longwall outlet and in the ventilation roadway. Case study, Manag. Syst.
```
Prod. Eng. 31 (4) (2023) 398–403.
```
[4] L. Barnewold, B.G. Lottermoser, Identification of digital technologies and digital-
```
isation trends in the mining industry, Int. J. Mining Sci. Technol. 30 (6) (2020)
```
747–757.
[5] X. Liu, P. Qi, P. Siarry, D. Hua, Z. Ma, X. Guo, O. Kochan, Z. Li, Mining security
assessment in an underground environment using a novel face recognition
```
method with improved multiscale neural network, Alex. Eng. J. 80 (2023)
```
217–228.
[6] R. Liang, C. Huang, C. Zhang, B. Li, S. Saydam, I. Canbulat, The fusion of data
visualisation and data analytics in the process of mining digitalisation, IEEE
```
Access (2023).
```
[7] H. Dougherty, E. Watkins, R. Kimutis, A network model analysis of an uncon-
ventional gas well breach above an underground coal mine, Min. Met. Explor.
```
40 (6) (2023) 2161–2166.
```
[8] D. Zhao, G. Su, G. Cheng, P. Wang, W. Chen, Y. Yang, Research on real-time
perception method of key targets in the comprehensive excavation working face
```
of coal mine, Meas. Sci. Technol. 35 (1) (2023) 015410.
```
[9] H. Wen, L. Yan, Y. Jin, Z. Wang, J. Guo, J. Deng, Coalbed methane concentration
prediction and early-warning in fully mechanized mining face based on deep
```
learning, Energy 264 (2023) 126208.
```
[10] W. Nie, Y. Cai, L. Wang, Q. Liu, C. Jiang, Y. Hua, C. Cheng, H. Zhang, Coupled
diffusion law of windflow-gas-dust in tunnel energy extraction processes and the
```
location of optimal pollution control exhaust duct, Energy (2024) 132145.
```
[11] A. Chaturvedi, Time series for data sciences: Analysis and forecasting, 2023.
[12] G. Zhang, E. Wang, Risk identification for coal and gas outburst in underground
```
coal mines: A critical review and future directions, Gas Sci. Eng. (2023) 205106.
```
[13] V. Hassija, V. Chamola, A. Mahapatra, A. Singal, D. Goel, K. Huang, S.
Scardapane, I. Spinelli, M. Mahmud, A. Hussain, Interpreting black-box models: a
```
review on explainable artificial intelligence, Cogn. Comput. 16 (1) (2024) 45–74.
```
[14] P.P. Angelov, E.A. Soares, R. Jiang, N.I. Arnold, P.M. Atkinson, Explainable
artificial intelligence: an analytical review, Wiley Interdiscip. Rev.: Data Min.
```
Knowl. Discov. 11 (5) (2021) e1424.
```
```
[15] A. Maćkiewicz, W. Ratajczak, Principal components analysis (PCA), Comput.
```
```
Geosci. 19 (3) (1993) 303–342.
```
```
[16] M. Müller, Dynamic time warping, Inf. Retr. Music. Motion (2007) 69–84.
```
[17] R.P. Masini, M.C. Medeiros, E.F. Mendes, Machine learning advances for time
```
series forecasting, J. Econ. Surv. 37 (1) (2023) 76–111.
```
[18] Z. Zamanzadeh Darban, G.I. Webb, S. Pan, C. Aggarwal, M. Salehi, Deep learning
```
for time series anomaly detection: A survey, ACM Comput. Surv. 57 (1) (2024)
```
1–42.
[19] I. Ahmed, G. Jeon, F. Piccialli, From artificial intelligence to explainable artificial
intelligence in industry 4.0: a survey on what, how, and where, IEEE Trans. Ind.
```
Inform. 18 (8) (2022) 5031–5042.
```
[20] H. Gholami, A. Mohammadifar, S. Golzari, Y. Song, B. Pradhan, Interpretability
of simple RNN and GRU deep learning models used to map land susceptibility
```
to gully erosion, Sci. Total Environ. 904 (2023) 166960.
```
[21] H. Gholami, A. Mohammadifar, Y. Song, Y. Li, P. Rahmani, D.G. Kaskaoutis, P.
Panagos, P. Borrelli, An assessment of global land susceptibility to wind erosion
based on deep-active learning modelling and interpretation techniques, Sci. Rep.
```
14 (1) (2024) 18951.
```
```
[22] A. Abdollahi, B. Pradhan, Explainable artificial intelligence (XAI) for interpreting
```
the contributing factors feed into the wildfire susceptibility prediction model, Sci.
```
Total Environ. 879 (2023) 163004.
```
[23] H. Gholami, A. Mohammadifar, R.D. Behrooz, D.G. Kaskaoutis, Y. Li, Y. Song,
Intrinsic and extrinsic techniques for quantification uncertainty of an inter-
pretable GRU deep learning model used to predict atmospheric total suspended
```
particulates (TSP) in Zabol, Iran during the dusty period of 120-days wind,
```
```
Environ. Pollut. 342 (2024) 123082.
```
[24] D. Minh, H.X. Wang, Y.F. Li, T.N. Nguyen, Explainable artificial intelligence: a
```
comprehensive review, Artif. Intell. Rev. (2022) 1–66.
```
[25] S.M. Lundberg, S.-I. Lee, A unified approach to interpreting model predictions,
```
in: I. Guyon, U.V. Luxburg, S. Bengio, H. Wallach, R. Fergus, S. Vishwanathan,
```
R. Garnett (Eds.), Advances in Neural Information Processing Systems 30, Curran
Associates, Inc., 2017, pp. 4765–4774, URL: http://papers.nips.cc/paper/7062-
a-unified-approach-to-interpreting-model-predictions.pdf.
[26] A.B. Parsa, A. Movahedi, H. Taghipour, S. Derrible, A.K. Mohammadian, Toward
safer highways, application of XGBoost and SHAP for real-time accident detection
```
and feature analysis, Accid. Anal. Prev. 136 (2020) 105405.
```
```
Information Fusion 118 (2025) 102976
```
13
H. Chang et al.
[27] M.T. Ribeiro, S. Singh, C. Guestrin, ‘‘Why should i trust you?’’ Explaining
the predictions of any classifier, in: Proceedings of the 22nd ACM SIGKDD
International Conference on Knowledge Discovery and Data Mining, 2016, pp.
1135–1144.
```
[28] S. Hochreiter, J. Schmidhuber, Long short-term memory, Neural Comput. 9 (8)
```
```
(1997) 1735–1780.
```
[29] K. Cho, B. Van Merriënboer, C. Gulcehre, D. Bahdanau, F. Bougares, H. Schwenk,
Y. Bengio, Learning phrase representations using RNN encoder-decoder for
statistical machine translation, 2014, arXiv preprint arXiv:1406.1078.
[30] A. Vaswani, N. Shazeer, N. Parmar, J. Uszkoreit, L. Jones, A.N. Gomez, Ł. Kaiser,
I. Polosukhin, Attention is all you need, Adv. Neural Inf. Process. Syst. 30 (2017).
[31] F. Scarselli, M. Gori, A.C. Tsoi, M. Hagenbuchner, G. Monfardini, The graph
```
neural network model, IEEE Trans. Neural Netw. 20 (1) (2008) 61–80.
```
[32] A.B. Arrieta, N. Díaz-Rodríguez, J. Del Ser, A. Bennetot, S. Tabik, A. Barbado,
S. García, S. Gil-López, D. Molina, R. Benjamins, et al., Explainable artificial
```
intelligence (XAI): Concepts, taxonomies, opportunities and challenges toward
```
```
responsible AI, Inf. Fusion 58 (2020) 82–115.
```
[33] H. Yoon, K. Yang, C. Shahabi, Feature subset selection and feature ranking for
```
multivariate time series, IEEE Trans. Knowl. Data Eng. 17 (9) (2005) 1186–1198.
```
[34] A. Aldrees, M. Khan, A.T.B. Taha, M. Ali, Evaluation of water quality in-
```
dexes with novel machine learning and SHapley Additive ExPlanation (SHAP)
```
```
approaches, J. Water Process. Eng. 58 (2024) 104789.
```
[35] Y. Song, Q. Wang, X. Zhang, L. Dong, S. Bai, D. Zeng, Z. Zhang, H. Zhang, Y.
Xi, Interpretable machine learning for maximum corrosion depth and influence
```
factor analysis, Npj Mater. Degrad. 7 (1) (2023) 9.
```
[36] D. Chushig-Muzo, H. Calero-Díaz, F.J. Lara-Abelenda, V. Gómez-Martínez, C.
Granja, C. Soguero-Ruiz, Interpretable data-driven approach based on feature
selection methods and GAN-based models for cardiovascular risk prediction in
```
diabetic patients, IEEE Access (2024).
```
[37] G. Hooker, L. Mentch, S. Zhou, Unrestricted permutation forces extrapolation:
variable importance requires at least one more model, or there is no free variable
```
importance, Stat. Comput. 31 (2021) 1–16.
```
[38] X. Liu, G. Zhang, Z. Zhang, A novel hybrid feature selection and modified KNN
```
prediction model for coal and gas outbursts, J. Intell. Fuzzy Systems 39 (5)
```
```
(2020) 7671–7691.
```
[39] J. Zhou, H. Lin, H. Jin, S. Li, Z. Yan, S. Huang, Cooperative prediction method of
gas emission from mining face based on feature selection and machine learning,
```
Int. J. Coal Sci. Technol. 9 (1) (2022) 51.
```
[40] D. Miao, K. Yao, W. Wang, L. Liu, X. Sui, Risk prediction of coal mine rock
burst based on machine learning and feature selection algorithm, in: Georisk:
Assessment and Management of Risk for Engineered Systems and Geohazards,
Taylor & Francis, 2024, pp. 1–14.
[41] S. Chen, S. Dong, A sequential structure for water inflow forecasting in coal
mines integrating feature selection and multi-objective optimization, IEEE Access
```
8 (2020) 183619–183632.
```
[42] H. De, L. Jian, L. Yong, L. Xiangyang, D. Lijun, L. Yonghong, H. Pingping,
H. Changshou, Experimental research on combination selection of observation
feature of resistance variation fault in mine ventilation, J. China Coal Soc. 46
```
(12) (2021) 3922–3933.
```
[43] D. Ślęzak, M. Grzegorowski, A. Janusz, M. Kozielski, S.H. Nguyen, M. Sikora,
S. Stawicki, Ł. Wróbel, A framework for learning and embedding multi-sensor
forecasting models into a decision support system: A case study of methane
```
concentration in coal mines, Inform. Sci. 451 (2018) 112–133.
```
[44] H. Zhou, S. Zhang, J. Peng, S. Zhang, J. Li, H. Xiong, W. Zhang, Informer: Beyond
efficient transformer for long sequence time-series forecasting, in: Proceedings of
the AAAI Conference on Artificial Intelligence, 2021, pp. 11106–11115.
[45] L.S. Shapley, et al., A value for n-person games, 1953.
```
[46] L. Breiman, Random forests, Mach. Learn. 45 (2001) 5–32.
```
[47] T. Liu, H. Meidani, End-to-end heterogeneous graph neural networks for traffic
```
assignment, Transp. Res. C 165 (2024) 104695.
```
[48] L. Cheng, L. Li, S. Li, S. Ran, Z. Zhang, Y. Zhang, Prediction of gas concentra-
tion evolution with evolutionary attention-based temporal graph convolutional
```
network, Expert Syst. Appl. 200 (2022) 116944.
```
[49] N. Xu, C. Kosma, M. Vazirgiannis, TimeGNN: Temporal dynamic graph learning
for time series forecasting, in: Complex Networks, 2023.