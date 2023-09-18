# ICSXVPN-2016 Dataset Analysis and Classification

This project utilizes the publicly available ICSXVPN-2016 dataset, which can be found [here](<https://www.unb.ca/cic/datasets/vpn.html>). The dataset originally came in a .pcap format and was transformed into a readable .csv format using the CICFlowmeter tool, written in Java. The Flowmeter tool also performed feature engineering, extracting 84 features for each network data packet.

## Phase 1: Data Preparation

### 1.1 Data Transformation

- The ICSXVPN-2016 dataset was initially in .pcap format.
- The ICSX Flowmeter tool was used to convert it into .csv format, making it easily readable and accessible.

### 1.2 Labeling

- The dataset was labeled into two categories: VPN and Non-VPN data packets.
- This labeling process was carried out using the 'label_and_combine_csv' tool.

## Phase 2: Data Preprocessing

### 2.1 Data Analysis

In this phase, we perform comprehensive analysis to better understand the dataset.

- **Statistical Summary**: Obtain summary statistics to gain insights into the dataset's characteristics.
- **Raw Data Information**: Explore information about the raw data.
- **Missing Values**: Check for missing values within the dataset.
- **Data Distribution**: Examine the distribution of data points.
- **Class Distribution**: Analyze the distribution of classes (VPN and Non-VPN).
- **Data Duplication**: Identify and handle duplicated data.

### 2.2 Data Cleaning

- **Handling Missing Values**: Implement strategies to address missing values, ensuring data integrity.
- **Deletion of Duplicate Data**: Remove duplicated entries to avoid bias in the analysis.
- **Feature Selection**: Select relevant features for model training.

### 2.3 Feature Selection

To select the most relevant features for the classification task, the dataset is divided into six parts. Pearson correlation is calculated for feature selection in each part. Finally, two approaches are applied:

#### Approach 1: Features with Correlation > 0.2

- Features with a correlation value greater than 0.2 are selected.

#### Approach 2: Features with Correlation > 0.1

- Features with a correlation value greater than 0.1 are selected.

## Phase 3: Model Training and Evaluation

### 3.1 Model Training

Four machine learning models are trained using the selected features from both approaches:

- Decision Tree
- Naive Bayes
- AdaBoost
- Random Forest

For each model, two sets of features are used (correlation > 0.2 and correlation > 0.1).

### 3.2 Model Evaluation

The results, including confusion matrices, are stored in the "outputs" folder. All models are evaluated using the following metrics:

- **Precision**: Measures the accuracy of positive predictions.
- **Recall**: Calculates the proportion of true positives identified.
- **F1 Score**: Balances precision and recall for a single metric.

The evaluation results provide insights into the performance of the models in classifying VPN and Non-VPN data packets based on the selected features.

This README provides an overview of the project's phases and steps, highlighting the dataset preparation, data preprocessing, feature selection, model training, and evaluation. Detailed information and code can be found in the project's documentation and code files.
