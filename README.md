# Glomeruli-Binary-Classifier
Welcome to the repository containing the code and resources for a machine learning model developed for the binary classification of sclerotic and non-sclerotic glomeruli.

## Table of Contents
- [Medical Context](#section-1)
- [Machine Learning Models](#section-2)
- [Published Digital Pathology ML Models](#section-3)
- [Approach](#section-4)
- [Performance Metrics](#section-5)
- [Dataset](#section-6)
- [Installation](#section-7)
- [Results](#section-8)
- [Abbreviations](#section-9)
- [References](#section-10)

## Medical Context
<a name="section-1"></a>
### Sclerotic Glomeruli
Sclerotic glomeruli refer to a condition where the glomerulus, a tiny blood vessel in the kidney, undergoes sclerosis, which involves the hardening and scarring of the tissues. This condition is often associated with various renal diseases and can impact kidney function. Identification of sclerotic glomeruli through machine learning models can aid in understanding and diagnosing renal diseases.

### Non-sclerotic Glomeruli
Non-sclerotic glomeruli, on the other hand, represent glomeruli without the hardening and scarring characteristic of sclerosis. Understanding the differences between sclerotic and non-sclerotic glomeruli is crucial in the medical domain for accurate diagnosis and treatment planning.

## Machine Learning Models
<a name="section-2"></a>
| Feature                       | Logistic Regression      | Support Vector Machines  | Random Forest             | Convolutional Neural Networks (CNN) | Recurrent Neural Networks (RNN) |
|-------------------------------|--------------------------|--------------------------|---------------------------|--------------------------------------|----------------------------------|
| **Model Type**                | Linear Model             | Discriminative Model     | Ensemble Model            | Deep Learning Model                  | Deep Learning Model              |
| **Interpretability**           | High                     | Medium                   | Medium                    | Low                                  | Low                              |
| **Complexity**                | Low                      | Medium-High              | High                      | High                                 | High                             |
| **Feature Importance**        | Yes (Coefficients)       | Yes (Support Vectors)    | Yes (Tree Importance)    | Yes (Learned Filters)               | Limited                          |
| **Handling Non-Linearity**    | Limited                  | Yes                      | Yes                       | Yes                                  | Yes                              |
| **Regularization**            | Yes                      | Yes                      | Yes                       | Yes                                  | Yes                              |
| **Robustness to Noise**        | Moderate                 | High                     | High                      | High                                 | Moderate                         |
| **Dataset Size Sensitivity**   | Moderate                 | High                     | Moderate-High             | High                                 | High                             |
| **Hyperparameter Sensitivity** | Low                      | Moderate                 | Moderate                  | High                                 | High                             |
| **Suitability for Image Data** | No                       | No                       | No                        | Yes                                  | No                               |
| **Suitability for Time Series**| No                       | No                       | No                        | No                                   | Yes                              |
| **Handling Imbalanced Data**   | May require adjustments | Can handle with C parameter| Can handle with class weights | May require adjustments            | May require adjustments          |

## Published Digital Pathology ML Models
<a name="section-3"></a>
| Index | Paper                                                  | Method                               | Stain | μPrecision | μRecall | μF1 Score        | MCC           | Split  |
|-------|--------------------------------------------------------|--------------------------------------|-------|------------|---------|------------------|---------------|--------|
| I     | [2](#ref-2)                                                   | ANN                                  | PAS   | 0.9844(±0.0111) | 0.9310(±0.0153) | NA         | 0.95(±0.01)  | NA     |
| II    | [3](#ref-3)                                                    | CNN on SegNet                       | PAS   | NA         | NA      | 0.69             | NA            | NA     |
| III   | [3](#ref-3)                                                   | CNN on DeepLab v3+                   | PAS   | NA         | NA      | 0.63             | NA            | NA     |
| IV    | [4](#ref-4)                                                    | CNN-MLP                              | H&E and PAS | 0.995(±0.008) | 0.994(±0.009) | 0.996(±0.006) | NA           | 80/20  |
| V     | [4](#ref-4)                                                    | CNN-SVM                              | H&E and PAS | 0.996(±0.006) | 0.996(±0.007) | 0.996(±0.003) | NA           | 80/20  |
| VI    | [5](#ref-5)                                                    | GoogLeNet-BN-Bayesian                | NA    | NA         | NA      | 0.9366(±7.82)   | NA            | NA     |
| VII   | [6](#ref-6)                                                    | CNN model of InceptionV3             | NA    | 0.9830     | NA      | 0.9678           | NA            | NA     |

## Approach
<a name="section-4"></a>
### Model Selection
#### CNN MODEL OF INCEPTION V3
- Offers simple configuration [1](#ref-1)
- Offers possibility to import pre-trained models for partial setup [1](#ref-1)
- Eradicates the need to identify features [1](#ref-1)
- Offers dimensional reduction which reduces the computation load

### Model Development
<img width="919" alt="Screenshot 2024-02-04 at 3 40 18 AM" src="https://github.com/Srujith20/Glomeruli-Binary-Classifier/assets/66065988/a67f6dd6-3741-4aff-b6cb-28c4a5503c84">

## Performace Metrics
<a name="section-5"></a>
1. **Precision (Positive Predictive Value):**
   - **Formula:** Precision = TP / (TP + FP)
   - **Interpretation:** Precision is the ratio of correctly identified sclerotic glomeruli to the total predicted sclerotic glomeruli. It is relevant when the cost of false positives (misclassifying a non-sclerotic glomerulus as sclerotic) is high.

2. **Recall (Sensitivity, True Positive Rate):**
   - **Formula:** Recall = TP / (TP + FN)
   - **Interpretation:** Recall is the ratio of correctly identified sclerotic glomeruli to the total actual sclerotic glomeruli. It is important when missing sclerotic glomeruli (false negatives) is costly, and you want to maximize the identification of all positive instances.

3. **F1 Score:**
   - **Formula:** F1 Score = 2 * (Precision * Recall) / (Precision + Recall)
   - **Interpretation:** The F1 Score is the harmonic mean of precision and recall. It provides a balance between precision and recall and is useful when there is an uneven class distribution.

4. **Matthews Correlation Coefficient (MCC):**
   - **Formula:** MCC = (TP * TN - FP * FN) / sqrt((TP + FP) * (TP + FN) * (TN + FP) * (TN + FN))
   - **Interpretation:** MCC takes into account all four values in a confusion matrix and is particularly robust for imbalanced datasets. It ranges from -1 to +1, with 0 indicating no better than random chance.

### Metric Selected
**F1 Score**
- To maintain balance between precision and recall

## Dataset
<a name="section-6"></a>
| Image Type             | Count       |
|------------------------|-------------|
| Globally Sclerotic     | 1504        |
| Non-Globally Sclerotic | 4704        |

## Installation
<a name="section-7"></a>

## Results
<a name="section-8"></a>

## Abbreviations
<a name="section-9"></a>
- **ANN**: Artificial Neural Networks
- **CNN**: Convolutional Neural Networks
- **LSTM NN**: Long Short Term Memory Neural Network
- **PAS**: Periodic Acid Schiff
- **MCC**: Matthews Correlation Coefficient
- **BN**: Batch Normalization
- **MLP**: Multilayer Perceptron
- **μ**: Average
- **NA**: Not Available

## References
<a name="section-10"></a>
[1]<a name="ref-1"></a> Gallego J, Pedraza A, Lopez S, Steiner G, Gonzalez L, Laurinavicius A, Bueno G. Glomerulus Classification and Detection Based on Convolutional Neural Networks. Journal of Imaging. 2018; 4(1):20. doi.org/10.3390/jimaging4010020

[2]<a name="ref-2"></a>Cascarano GD, Debitonto FS, Lemma R, et al. A neural network for glomerulus classification based on histological images of kidney biopsy. BMC Med Inform Decis Mak. 2021;21(Suppl 1):300. Published 2021 Nov 1. doi:10.1186/s12911-021-01650-3

[3]<a name="ref-3"></a> Altini N, Cascarano GD, Brunetti A, Marino F, Rocchetti MT, Matino S, Venere U, Rossini M, Pesce F, Gesualdo L, et al. Semantic Segmentation Framework for Glomeruli Detection and Classification in Kidney Histological Sections. Electronics. 2020; 9(3):503. doi.org/10.3390/electronics9030503

[4]<a name="ref-4"></a> Chagas P, De Souza LC, Araújo I, et al. Classification of glomerular hypercellularity using convolutional features and support vector machine. Artificial Intelligence in Medicine. 2020;103:101808. doi:10.1016/j.artmed.2020.101808

[5]<a name="ref-5"></a> Yao X, Wang X, Karaca Y, Xie J, Wang S. Glomerulus classification via an improved GoogLeNet. IEEE Access. 2020;8:176916-176923. doi:10.1109/access.2020.3026567

[6]<a name="ref-6"></a> Varalakshmi P, Saroja S, Ketharaman S, Shimola S. Glomeruli Identification in Renal Biopsy using Deep Learning Approaches. 2022 International Conference on Innovative Computing, Intelligent Communication and Smart Electrical Systems (ICSES). July 2022. doi:10.1109/icses55317.2022.9914279
