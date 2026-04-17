# Breast Cancer Detection - Machine Learning Project

A machine learning project for breast cancer diagnosis using the Wisconsin Breast Cancer Diagnostic dataset.

## Problem Statement

Breast cancer is one of the most common cancers among women worldwide. Early detection and accurate diagnosis are crucial for effective treatment and improved patient outcomes. This project aims to develop a machine learning classifier that can accurately distinguish between benign and malignant breast tumors based on cellular features extracted from digitized images of fine needle aspirates.

The dataset contains 569 samples with 30 features computed from cell nuclei characteristics, including:
- **Radius** (mean of distances from center to points on the perimeter)
- **Texture** (standard deviation of gray-scale values)
- **Perimeter**
- **Area**
- **Smoothness** (local variation in radius lengths)
- **Compactness** (perimeter² / area - 1.0)
- **Concavity** (severity of concave portions of the contour)
- **Concave points** (number of concave portions of the contour)
- **Symmetry**
- **Fractal dimension** ("coastline approximation")

Each feature is measured as mean, standard error, and worst (largest of the three) values, resulting in 30 total features.

## Workflow

### 1. Data Collection
The dataset is fetched directly from the UCI Machine Learning Repository using the `ucimlrepo` package (Dataset ID: 17).

### 2. Data Preprocessing
- **Feature Selection**: Removed highly correlated features to reduce multicollinearity (perimeter and area features, which are strongly correlated with radius)
- **Data Splitting**: 80/20 train-test split with stratification

### 3. Exploratory Data Analysis (EDA)
The notebook includes comprehensive data visualization:
- Pair plots of principal features
- Correlation heatmap
- Box plots for feature distribution analysis
- Histograms for feature distribution

### 4. Model Training
- **Algorithm**: Random Forest Classifier
- **Hyperparameter Tuning**: Grid Search with 5-fold cross-validation
- **Parameters optimized**:
  - `n_estimators`: [50, 100, 150, 200]
  - `criterion`: ['gini', 'entropy', 'log_loss']
  - `max_features`: ['sqrt', 'log2', None]

### 5. Model Evaluation
Multiple evaluation metrics and visualizations:
- Confusion Matrix
- Precision, Recall, F1-Score, Accuracy
- Feature Importance Analysis
- ROC Curve with AUC scores

## Evaluation Method

The model performance is evaluated using the following metrics:

### Primary Metrics
- **Accuracy**: Overall correctness of predictions (achieved: ~96%)
- **Precision**: Ratio of correctly predicted positive observations to total predicted positives
- **Recall (Sensitivity)**: Ratio of correctly predicted positive observations to all actual positives
- **F1-Score**: Weighted average of Precision and Recall

### Validation Strategy
- **5-Fold Cross-Validation**: Used during hyperparameter tuning to ensure model generalization
- **Hold-out Test Set**: 20% of data reserved for final evaluation

### Additional Analysis
- **Confusion Matrix**: Visualizes true positives, true negatives, false positives, and false negatives
- **ROC Curve**: Shows the trade-off between sensitivity and specificity across different thresholds
- **Feature Importance**: Identifies which cellular characteristics are most predictive of malignancy

## Installation

```bash
pip install -r requirements.txt
```

## Usage

Open and run the Jupyter notebook:

```bash
jupyter notebook breastCancerDetection.ipynb
```

## Dataset Source

Wisconsin Breast Cancer Diagnostic Dataset  
UCI Machine Learning Repository  
Dataset ID: 17  
[Link](https://archive.ics.uci.edu/ml/datasets/breast+cancer+wisconsin+diagnostic)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**StefoXCaffeine**
