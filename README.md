# Glomeruli-Binary-Classifier
Welcome to the repository containing the code and resources for a machine learning model developed for the binary classification of sclerotic and non-sclerotic glomeruli.

## Table of Contents
- [Medical Context](#section-1)
- [Machine Learning Models](#section-2)
- [Published Digital Pathology ML Models](#section-3)
- [Approach](#section-4)
- [Evalutaion Metrics](#section-5)
- [Dataset](#section-6)
- [Environment Specifications](#section-7)
- [Setup](#section-8)
- [Data Preprocessing](#section-9)
- [Model Selection](#section-10)
- [Defining Model](#section-11)
- [Training Model](#section-12)
- [Fine Tuning](#section-13)
- [Testing and Performance](#section-14)
- [Results](#section-15)
- [Abbreviations](#section-16)
- [References](#section-17)

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
| Index | Paper                                                  | Method                               | Stain | μF1 Score        |
|-------|--------------------------------------------------------|--------------------------------------|-------|------------------|
| I     | [2](#ref-2)                                                   | ANN                                  | PAS   |  0.9310(±0.0153) |
| II    | [3](#ref-3)                                                    | CNN on SegNet                       | PAS   |  0.69             | 
| III   | [3](#ref-3)                                                   | CNN on DeepLab v3+                   | PAS   |  0.63             |    
| IV    | [4](#ref-4)                                                    | GoogLeNet-BN-Bayesian                | PAS  | 0.9366(±7.82)   |      
| V   | [5](#ref-5)                                                    | CNN model of InceptionV3             | PAS    |  0.9678           |    

## Approach
<a name="section-4"></a>
### Intial Model Selection 
#### CNN MODEL OF INCEPTION V3
- Offers simple configuration [1](#ref-1)
- Offers possibility to import pre-trained models for partial setup [1](#ref-1)
- Eradicates the need to identify features [1](#ref-1)
- Offers dimensional reduction which reduces the computation load
- Showed a better μF1 Score compared to other models in the published models above

### Model Development
<img width="919" alt="Screenshot 2024-02-04 at 3 40 18 AM" src="https://github.com/Srujith20/Glomeruli-Binary-Classifier/assets/66065988/a67f6dd6-3741-4aff-b6cb-28c4a5503c84">

## Evaluation Metrics
<a name="section-5"></a>
### Definitions
1. **Precision (Positive Predictive Value):**
   - **Formula:** Precision = TP / (TP + FP)
   - **Interpretation:** Precision is the ratio of correctly identified sclerotic glomeruli to the total predicted sclerotic glomeruli. It is relevant when the cost of false positives (misclassifying a non-sclerotic glomerulus as sclerotic) is high.

2. **Recall (Sensitivity, True Positive Rate):**
   - **Formula:** Recall = TP / (TP + FN)
   - **Interpretation:** Recall is the ratio of correctly identified sclerotic glomeruli to the total actual sclerotic glomeruli. It is important when missing sclerotic glomeruli (false negatives) is costly, and you want to maximize the identification of all positive instances.

3. **F1 Score:**
   - **Formula:** F1 Score = 2 * (Precision * Recall) / (Precision + Recall)
   - **Interpretation:** The F1 Score is the harmonic mean of precision and recall. It provides a balance between precision and recall and is useful when there is an uneven class distribution.
  
### Metric Selection
**Influencing Factors**
**False Positive Results**: Low precision leads to a higher number of false positives, where the model incorrectly identifies individuals as having a disease or condition when they do not. This can result in unnecessary anxiety and stress for patients, as well as unnecessary follow-up tests, treatments, or interventions. 

**False Negative Results**: Low recall results in a higher number of false negatives, where the model fails to identify individuals who actually have a disease or condition. This can lead to missed diagnoses, delayed treatment, and progression of the disease, potentially resulting in poorer patient outcomes and decreased quality of life.

- Hence, it is essential to maintain balance between the aforementioned factors. 

- F1 score satisfies the requirement and hence it was selected as the evalutaion metric.

## Dataset
<a name="section-6"></a>
| Image Type             | Count       |
|------------------------|-------------|
| Globally Sclerotic     | 1504        |
| Non-Globally Sclerotic | 4704        |

## Enviroment Specification
<a name="section-7"></a>
- Environment: Google Colab
- Hardware Accelerator: T4 GPU
- Data Storage: Google Drive

## Setup
<a name="section-8"></a>
### Train the Model

**Demo Video Link:** https://drive.google.com/file/d/1pQJrc9We7lSXpceHoV6mI6GINRkbpvx4/view?usp=sharing

1. Upload the Data folder to google drive
2. The data folder should have two folders for **globally_sclerotic** and **non_globally_sclerotic** images
3. Open **BinaryGlomeruliClassifier_.ipynb** and click on **Open in Colab** at the top of the page
4. Make sure Colab and drive are associated with the same account
5. Connect to a hosted runtime preferably GPU 
6. Run cell under **Setup**
7. Run cell under **Mounting Drive**
8. Give permissions to Colab to access drive
9. Change paths under **Creating Train, Validate and Test Folders** for:
    - **original_dataset_dir:** Point to folder containing **globally_sclerotic** and **non_globally_sclerotic** images
    - **original_sclerotic_data_dir:** Point to folder containing **globally_sclerotic** images
    - **original_non_sclerotic_data_dir:** Point to folder containing **non_globally_sclerotic** images
10. Click **Run all** under **Run Time**
11. The model will be saved to root of drive under the name **mobilenet_glomeruli_classifier**

### Test using the generated model

**Demo Video Link:** https://drive.google.com/file/d/1QbBXf1hAU8UKqL37foYrJdX55Z8PeKdu/view?usp=sharing

1. Upload test folder and trained model to google grive
2. Open evaluation.ipynb in this repository
3. Click on Google Colab icon in the evaluation.ipynb file at the top
4. Make sure Colab and Drive are associated with same account
5. Connect to hosted run time CPU or GPU
6. Run the code to mount the drive, give access
7. Run the python script
8. Copy and paste the images location from the drive using the folder icon in Colab
9. Copy and paste the model location similarly
10. Evaluation.csv file will be generated with name and predicted class in the same location as that of model


## Data Preprocessing
<a name="section-9"></a>
- Downloaded Data
- Split the entire data into train(70%), test(15%) and validate(15%) folders
- Each folder above contains both globally_scloretic and non_globally_scloretic folders as classes with images count depending on the aforementioned split on their original folders
- Configured the dataset for performance by utilising buffered prefetching for loading images from disc without causing I/O blocks
- Augmented data to introduce diveristy by applying realistic transformations to reduce overfitting
- Rescaled pixel values to suit the pretrained models

## Model Selection
<a name="section-10"></a>
- A sample folder consisting of 150 globally_scloretic_glomeruli and 150 non_globally_scloretic_glomeruli was sampled from original dataset for testing to select model. 
- Two pretrained CNN models were considered for transfer learning and fine tuning:
  1. MobileNetV2
  2. InceptionV3
- The following were the results of training and testing the model using sampled training and testing data before and after fine tuning:

| Model        | Precision | Accuracy | F1 Score |
|--------------|-----------|----------|----------|
| MobileNetV2  |   0.65    |   0.68   |   0.66   |
| InceptionV3  |   0.5     |   0.5    |   0.5    |

- Since the **MobileNetV2** perforemed better than **InceptionV3**, it has been chose as the model for the binary classification.

## Defining Model
<a name="section-11"></a>
- Input Image Shape = [160, 160, 3]
- Batch Size = 32
- Loaded MobileNetV2 ,since showed better results in the terms of the F1 score on sampled data

## Training Model
<a name="section-12"></a>
- Freezed the convolutional base
- Added gloabl average pooling to feature maps which resulted in single 1280-element vector per image in the batch
- Added dense layer which sets to 1, indicating that it will produce a single prediction value per image in the batch
- Compiled the model
- Ran the model to fit the dataset
- Evaluaed the training and validation accuracy/loss

## Fine Tuning
<a name="section-13"></a>
- Unfreezed the base model to force the weights to be tuned from generic feature maps to features associated specifically with the dataset
- Compiled and ran the model again

## Testing and performace
<a name="section-13"></a>

## Results
<a name="section-15"></a>

## Abbreviations
<a name="section-16"></a>
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
<a name="section-17"></a>
[1]<a name="ref-1"></a> Gallego J, Pedraza A, Lopez S, Steiner G, Gonzalez L, Laurinavicius A, Bueno G. Glomerulus Classification and Detection Based on Convolutional Neural Networks. Journal of Imaging. 2018; 4(1):20. doi.org/10.3390/jimaging4010020

[2]<a name="ref-2"></a>Cascarano GD, Debitonto FS, Lemma R, et al. A neural network for glomerulus classification based on histological images of kidney biopsy. BMC Med Inform Decis Mak. 2021;21(Suppl 1):300. Published 2021 Nov 1. doi:10.1186/s12911-021-01650-3

[3]<a name="ref-3"></a> Altini N, Cascarano GD, Brunetti A, Marino F, Rocchetti MT, Matino S, Venere U, Rossini M, Pesce F, Gesualdo L, et al. Semantic Segmentation Framework for Glomeruli Detection and Classification in Kidney Histological Sections. Electronics. 2020; 9(3):503. doi.org/10.3390/electronics9030503

[4]<a name="ref-4"></a> Yao X, Wang X, Karaca Y, Xie J, Wang S. Glomerulus classification via an improved GoogLeNet. IEEE Access. 2020;8:176916-176923. doi:10.1109/access.2020.3026567

[5]<a name="ref-5"></a> Varalakshmi P, Saroja S, Ketharaman S, Shimola S. Glomeruli Identification in Renal Biopsy using Deep Learning Approaches. 2022 International Conference on Innovative Computing, Intelligent Communication and Smart Electrical Systems (ICSES). July 2022. doi:10.1109/icses55317.2022.9914279
