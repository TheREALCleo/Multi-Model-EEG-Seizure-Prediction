# Seizure Prediction using Time Series EEG Signals

## Introduction to EEG Signals
Electroencephalography (EEG) is a non-invasive method used to record electrical activity in the brain. The signals are captured via electrodes placed on the scalp, measuring the voltage fluctuations caused by neural activity. EEG signals are widely used in the diagnosis and treatment of neurological conditions, including epilepsy. By decoding these signals, we can gain insights into brain activity and detect abnormalities that may lead to seizures.

## Dataset Information
The dataset used in this project is **chbmit_preprocessed_data.csv**.
The dataset can be accessed from the [Preprocessed CHB-MIT Scalp EEG Database](https://ieee-dataport.org/open-access/preprocessed-chb-mit-scalp-eeg-database).

## About Seizures
A seizure is an abnormal burst of electrical activity in the brain, which can lead to changes in behavior, movements, feelings, or consciousness. Seizures can vary in severity and duration, ranging from brief lapses in awareness to prolonged convulsions. For individuals with epilepsy, predicting seizures can make a world of difference by enabling timely interventions, such as administering medication or moving to a safe environment.

Epilepsy affects millions of people worldwide, and despite advancements in treatment, many patients continue to experience seizures. The unpredictability of seizures is one of the most challenging aspects of epilepsy, underscoring the importance of accurate and reliable prediction methods.

## Feature Extraction
Feature extraction is a critical step in processing EEG signals, enabling the transformation of raw data into meaningful representations for analysis. In this project, the following features are extracted from each EEG channel:

### Statistical Features
1. **Mean**: Represents the average amplitude of the EEG signal over a specific time window.
2. **Standard Deviation (SD)**: Measures the variability or dispersion of the signal amplitudes.
3. **Variance (var)**: Quantifies the spread of the signal amplitudes.
4. **Maximum (max)**: The highest amplitude value in the signal.
5. **Minimum (min)**: The lowest amplitude value in the signal.
6. **Peak-to-Peak (ptp)**: Difference between the maximum and minimum values.
7. **Skewness (skew)**: Measures the asymmetry of the signal distribution.
8. **Kurtosis (kurt)**: Indicates the "tailedness" of the signal distribution.
9. **Zero Crossings (zcross)**: Counts the number of times the signal crosses zero.
10. **Energy**: Represents the total power of the signal.
11. **Root Mean Square (RMS)**: A measure of the signal's magnitude.

### EEG Channels
Features are extracted for the following channels:
- FP1-F7, C3-P3, C4-P4, CZ-PZ, F3-C3, F4-C4, F7-T7, F8-T8, FP1-F3, FP2-F4, FP2-F8, FT10-T8, FT9-FT10, FZ-CZ, P3-O1, P4-O2, P7-O1, P7-T7, P8-O2, T7-FT9, T7-P7, T8-P8-0, T8-P8-1

For each channel, the above features are computed and used for analysis.

## Time Series Analysis
EEG signals are inherently time-series data, capturing temporal patterns of brain activity. The analysis of time series involves:

- **Segmentation**: Dividing the continuous EEG signals into smaller time windows.
- **Feature Computation**: Calculating statistical features (mean, SD, variance, etc.) for each segment.
- **Sequence Construction**: Representing the EEG data as a sequence of statistical features over time.

This approach helps in identifying patterns that could predict seizures.

## Models Used
To classify and predict seizures, multiple machine learning models are employed. Each model is trained on the extracted time-series features and offers unique strengths:

### 1. 1D-CNN (One-Dimensional Convolutional Neural Network)
- Captures spatial and temporal patterns in the EEG data.
- Uses convolutional layers to extract local features from the time-series data.
- Particularly effective for identifying complex and non-linear patterns in sequential data.

### 2. K-Nearest Neighbors (KNN)
- A simple yet powerful model that classifies data points based on their similarity to the nearest neighbors.
- Easy to interpret and performs well on smaller datasets.

### 3. LightGBM (LGBM)
- A gradient-boosting framework optimized for speed and efficiency.
- Excellent for handling large datasets and offers robust performance with minimal tuning.

### 4. Random Forest (RF)
- An ensemble method that aggregates predictions from multiple decision trees.
- Reduces overfitting and provides high accuracy by averaging the outputs of diverse trees.

### 5. Support Vector Machine (SVM)
- Finds the optimal hyperplane to separate data points into distinct classes.
- Performs well in high-dimensional spaces and is especially effective for binary classification problems.

### 6. Histogram-based Gradient Boosting (HGB)
- A variation of gradient boosting that bins continuous features into discrete intervals.
- Optimized for speed and memory usage, making it ideal for large datasets.

### 7. XGBoost
- A scalable and efficient gradient-boosting algorithm.
- Known for its exceptional performance in time-series prediction tasks and competitions.

By comparing these models, we aim to identify the most effective approach for seizure prediction. Each model brings unique strengths, ensuring a thorough exploration of the data and prediction possibilities.

## File Overview
- **EEG_TimeFeatureExtraction.ipynb**: Responsible for extracting statistical features from raw EEG signals, converting time-series data into meaningful feature sets.
- **Preprocessing.ipynb**: Handles data cleaning, normalization, and preparation of the dataset for model training.
- **Models.ipynb**: Implements various machine learning and deep learning models, including 1D-CNN, LightGBM, and Random Forest.
- **ModelTesting.ipynb**: Evaluates the performance of the trained models using metrics like accuracy, precision, recall, and F1-score.

## Conclusion
This project focuses on leveraging the power of EEG signals and advanced machine learning models to predict seizures. By transforming raw EEG data into meaningful features and employing a diverse set of algorithms, this system aims to provide accurate and timely predictions. The ultimate goal is to contribute to better management of epilepsy, offering individuals a safer and more predictable future.

---

Feel free to explore the repository for the code, datasets, and results of the models. Contributions and suggestions are welcome!