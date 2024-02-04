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
- [Contact](#section-11)


## Medical Context
<a name="section-1"></a>
### Sclerotic Glomeruli
Sclerotic glomeruli refer to a condition where the glomerulus, a tiny blood vessel in the kidney, undergoes sclerosis, which involves the hardening and scarring of the tissues. This condition is often associated with various renal diseases and can impact kidney function. Identification of sclerotic glomeruli through machine learning models can aid in understanding and diagnosing renal diseases.

### Non-sclerotic Glomeruli
Non-sclerotic glomeruli, on the other hand, represent glomeruli without the hardening and scarring characteristic of sclerosis. Understanding the differences between sclerotic and non-sclerotic glomeruli is crucial in the medical domain for accurate diagnosis and treatment planning.

### Sclerotic Glomeruli Types
#### Globally Sclerotic Glomeruli
Globally sclerotic glomeruli are characterized by complete and diffuse hardening and scarring of the entire glomerulus. This type of sclerosis often indicates advanced renal damage, requiring careful management and intervention in clinical settings.

#### Non-Globally Sclerotic Glomeruli
In contrast, non-globally sclerotic glomeruli exhibit partial or localized hardening and scarring within the glomerulus. Understanding the specific patterns and distribution of sclerosis in non-globally sclerotic glomeruli is essential for a more nuanced diagnosis and targeted treatment approaches.

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
| Index | Paper                                                  | Method                               | Average Accuracy | Average F1 Score | MCC  | Split  |
|-------|--------------------------------------------------------|--------------------------------------|-------------------|-------------------|------|--------|
| 1     | Glomerulus Classification via an Improved GoogLeNet     | GoogLeNet-BN-Bayesian                | 95.04             | 93.66             | NA   | NA     |
| 2     | Glomeruli Identification in Renal Biopsy using Deep Learning Approaches | CNN model of InceptionV3      | 96                | 96.78             | NA   | NA     |
| 3     | A neural network for glomerulus classification based on histological images of kidney biopsy | ANN | 99.14 | NA   | 96.59 | NA     |
| 4     | Glomerulus Classification and Detection Based on Convolutional Neural Networks | CNN on pre-trained AlexNet | 99.9 | 99.9 | NA   | NA     |
| 5     | Semantic Segmentation Framework for Glomeruli Detection and Classification in Kidney Histological Sections | CNN on SegNet and DeepLab v3+ | NA | NA | NA   | NA     |
| 6     | Classification of glomerular hypercellularity using convolutional features and support vector machine | CNN-MLP | 99.5 | 99.6 | NA   | 80/20  |
| 7     | Classification of glomerular hypercellularity using convolutional features and support vector machine | CNN-SVM | 99.6 | 99.6 | NA   | 80/20  |

## Approach
<a name="section-4"></a>
### Model Selection
#### Convolution Neural Network(CNN)
- Offers simple configuration [1]
- Offers possibility to import pre-trained models for partial setup [1]
- Eradicates the need to identify features [1]
- Offers dimensional reduction which reduces the computation load

### Model Development
![Beige Colorful Minimal Flowchart Infographic Graph](https://github.com/Srujith20/Glomeruli-Binary-Classifier/assets/66065988/37334fe4-68bf-4ac2-b483-07cc10e829ac)

## Performace Metrics
<a name="section-5"></a>

## Dataset
<a name="section-6"></a>

## Installation
<a name="section-7"></a>

## Results
<a name="section-8"></a>

## Abbreviations
<a name="section-9"></a>
ANN     &nbsp; Artificial neural networks  
CNN     &nbsp; Convolutional Neural Networks  
LSTM NN &nbsp; Long Short Term Memory Neural Network  
PAS     &nbsp; Periodic Acid Schiff  
MCC     &nbsp; Matthews Correlation Coefficient  
NA      &nbsp; Not Available 

## Reference
<a name="section-10"></a>
[1] Gallego J, Pedraza A, Lopez S, Steiner G, Gonzalez L, Laurinavicius A, Bueno G. Glomerulus Classification and Detection Based on Convolutional Neural Networks. Journal of Imaging. 2018; 4(1):20. https://doi.org/10.3390/jimaging4010020

[2] Cascarano GD, Debitonto FS, Lemma R, et al. A neural network for glomerulus classification based on histological images of kidney biopsy. BMC Med Inform Decis Mak. 2021;21(Suppl 1):300. Published 2021 Nov 1. https://doi:10.1186/s12911-021-01650-3

[3] Yamaguchi R, Kawazoe Y, Shimamoto K, et al. Glomerular Classification Using Convolutional Neural Networks Based on Defined Annotation Criteria and Concordance Evaluation Among Clinicians. Kidney Int Rep. 2020;6(3):716-726. Published 2020 Dec 13. https://doi:10.1016/j.ekir.2020.11.037

[4] Altini N, Cascarano GD, Brunetti A, Marino F, Rocchetti MT, Matino S, Venere U, Rossini M, Pesce F, Gesualdo L, et al. Semantic Segmentation Framework for Glomeruli Detection and Classification in Kidney Histological Sections. Electronics. 2020; 9(3):503. https://doi.org/10.3390/electronics9030503

[5] Uchino E, Suzuki K, Sato N, et al. Classification of glomerular pathological findings using deep learning and nephrologist–AI collective intelligence approach. medRxiv (Cold Spring Harbor Laboratory). January 2020. https://doi:10.1101/2019.12.30.19016162

[6] Chagas P, De Souza LC, Araújo I, et al. Classification of glomerular hypercellularity using convolutional features and support vector machine. Artificial Intelligence in Medicine. 2020;103:101808. https://doi:10.1016/j.artmed.2020.101808

[7] Yao X, Wang X, Karaca Y, Xie J, Wang S. Glomerulus classification via an improved GoogLeNet. IEEE Access. 2020;8:176916-176923. https://doi:10.1109/access.2020.3026567

[8] Yang CK, Lee CY, Wang HS, et al. Glomerular disease classification and lesion identification by machine learning. Biomed J. 2022;45(4):675-685. https://doi:10.1016/j.bj.2021.08.011

[9] Uchino E, Suzuki K, Sato N, et al. Classification of glomerular pathological findings using deep learning and nephrologist–AI collective intelligence approach. International Journal of Medical Informatics. 2020;141:104231. https://doi:10.1016/j.ijmedinf.2020.104231

[10] Chagas P, De Souza LC, Araújo I, et al. Classification of glomerular hypercellularity using convolutional features and support vector machine. Artificial Intelligence in Medicine. 2020;103:101808. https://doi:10.1016/j.artmed.2020.101808

## Contact
<a name="section-11"></a>
- **Email:** narra.sr@ufl.edu




