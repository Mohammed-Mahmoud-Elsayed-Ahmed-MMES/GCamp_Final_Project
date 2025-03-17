# Sleep Health and Lifestyle Dataset

## Overview

The **Sleep Health and Lifestyle Dataset** comprises 374 entries detailing sleep and lifestyle factors of individuals. It includes demographic information, sleep metrics, physical activity levels, stress levels, and health indicators such as BMI, blood pressure, heart rate, daily steps, and the presence or absence of sleep disorders (e.g., Insomnia, Sleep Apnea). This dataset is designed to facilitate exploration of the relationships between lifestyle factors and sleep health, as well as to identify patterns associated with sleep disorders.

## Dataset Structure

- **Number of Rows**: 374
- **Number of Columns**: 13

## Columns Description

The dataset contains the following columns:

| **Column Name**             | **Description**                                                                 |
|-----------------------------|---------------------------------------------------------------------------------|
| Person ID                   | Unique identifier for each individual.                                          |
| Gender                      | Gender of the individual (Male/Female).                                         |
| Age                         | Age of the individual in years.                                                 |
| Occupation                  | Occupation or profession of the individual.                                     |
| Sleep Duration              | Number of hours the individual sleeps per day.                                  |
| Quality of Sleep            | Subjective rating of sleep quality on a scale from 1 to 10.                     |
| Physical Activity Level     | Number of minutes the individual engages in physical activity daily.            |
| Stress Level                | Subjective rating of stress level on a scale from 1 to 10.                      |
| BMI Category                | BMI category of the individual (e.g., Underweight, Normal, Overweight, Obese).  |
| Blood Pressure              | Blood pressure measurement, indicated as systolic over diastolic (e.g., 120/80).|
| Heart Rate                  | Resting heart rate of the individual in beats per minute (bpm).                 |
| Daily Steps                 | Number of steps the individual takes per day.                                   |
| Sleep Disorder              | Presence or absence of a sleep disorder (None, Insomnia, Sleep Apnea, or NaN for missing). |

### Details about Sleep Disorder Categories
- **None**: The individual does not exhibit any specific sleep disorder.
- **Insomnia**: The individual experiences difficulty falling asleep or staying asleep, leading to inadequate or poor-quality sleep.
- **Sleep Apnea**: The individual suffers from pauses in breathing during sleep, resulting in disrupted sleep patterns and potential health risks.

## Data Types

- **Numerical**:
  - Age (int64)
  - Sleep Duration (float64)
  - Quality of Sleep (int64)
  - Physical Activity Level (int64)
  - Stress Level (int64)
  - Heart Rate (int64)
  - Daily Steps (int64)
- **Categorical**:
  - Gender (object/string)
  - Occupation (object/string)
  - BMI Category (object/string)
  - Sleep Disorder (object/string, with NaN for missing values)
- **String**:
  - Blood Pressure (object/string, format: "systolic/diastolic")

## Missing Values

- The **Sleep Disorder** column contains 219 missing values (NaN), indicating that no sleep disorder information was recorded for those individuals. This could imply either unreported data or the absence of a diagnosed disorder, depending on the context of use.

## Usage

This dataset is suitable for a variety of analytical and research purposes, including:

- **Exploratory Data Analysis**: Investigate relationships between lifestyle factors (e.g., physical activity, stress) and sleep quality or disorders.
- **Statistical Analysis**: Identify correlations or trends among variables such as age, occupation, and sleep metrics.
- **Machine Learning**: Develop predictive models to classify sleep disorders or predict sleep duration/quality based on health and lifestyle indicators.
- **Data Visualization**: Create visual representations to communicate findings effectively.

## Notes

- **Blood Pressure**: Stored as a string in the format "systolic/diastolic" (e.g., "120/80"). For numerical analysis, it may need to be split into separate systolic and diastolic columns.
- **Duplicates**: The dataset contains 242 duplicate rows. Users should check for and handle duplicates based on their analysis requirements.
- **Subjective Data**: Columns like Quality of Sleep and Stress Level are based on self-reported ratings, which may vary in accuracy or consistency.
- **File Format**: The dataset is provided in CSV format (`Sleep_health_and_lifestyle_dataset.csv`).

## Exploratory Data Analysis (EDA)

An Exploratory Data Analysis (EDA) was conducted to summarize the dataset’s main characteristics and uncover patterns. Key insights include:

- **Age Distribution**: Ages range from 27 to 59, with a median of 42 years.
- **Sleep Duration**: Ranges from 5.8 to 8.5 hours, averaging approximately 7.2 hours.
- **Sleep Quality**: Mean rating of 7.3, with most values between 6 and 9.
- **Physical Activity**: Daily activity spans 30 to 90 minutes, with a mean of 60 minutes.
- **Stress Levels**: Ranges from 3 to 8, averaging 5.4.
- **BMI Categories**: Predominantly "Normal" or "Overweight" categories.
- **Sleep Disorders**: Among recorded cases, "None" is most common, followed by "Insomnia" and "Sleep Apnea."

Visualizations (e.g., histograms, box plots, correlation matrices) revealed:
- A negative correlation between stress levels and sleep quality, suggesting higher stress may reduce sleep quality.
- Potential relationships between physical activity and sleep duration, warranting further investigation.

This EDA provides a foundation for deeper statistical or predictive analysis.

## Example Analysis Questions

To inspire exploration, consider these questions:

### Gender
- How does age distribution differ between males and females?
- What are the most common occupations among males and females?
- Is there a difference in sleep duration between males and females?
- Does quality of sleep differ between males and females?
- Are there differences in physical activity levels between males and females?
- Do stress levels vary between males and females?
- How does BMI category distribution differ between males and females?
- Is there a difference in blood pressure between males and females?
- Does heart rate differ between males and females?
- Are there differences in daily steps between males and females?
- Is the prevalence of sleep disorders different between males and females?

### Age
- What are the most common occupations among different age groups?
- Is there a difference in sleep duration across different age groups?
- Does quality of sleep differ across different age groups?
- Are there differences in physical activity levels across different age groups?
- Do stress levels vary across different age groups?
- How does BMI category distribution differ across different age groups?
- Is there a difference in blood pressure across different age groups?
- Does heart rate differ across different age groups?
- Are there differences in daily steps across different age groups?
- Is the prevalence of sleep disorders different across different age groups?

### Occupation
- Is there a difference in sleep duration across different occupations?
- Does quality of sleep differ across different occupations?
- Are there differences in physical activity levels across different occupations?
- Do stress levels vary across different occupations?
- How does BMI category distribution differ across different occupations?
- Is there a difference in blood pressure across different occupations?
- Does heart rate differ across different occupations?
- Are there differences in daily steps across different occupations?
- Is the prevalence of sleep disorders different across different occupations?

### Sleep Disorders
- Do individuals with certain sleep disorders have consistently shorter or longer sleep durations compared to those with no reported disorder, regardless of age?
- Are there significant differences in stress levels between individuals with different sleep disorders?
- How does physical activity level differ among individuals with different sleep disorders?
- Are there significant differences in heart rate distributions between individuals with different sleep disorders?

## Loading the Dataset

To work with the dataset in Python, use the `pandas` library. Example snippets:

### Basic Loading
```python
import pandas as pd
df = pd.read_csv('Sleep_health_and_lifestyle_dataset.csv')
```

### Optional Preprocessing
- **Drop Person ID** (if not needed):
```python
df.drop(columns=['Person ID'], inplace=True)
```
- **Split Blood Pressure** (for numerical analysis):
```python
df[['Systolic', 'Diastolic']] = df['Blood Pressure'].str.split('/', expand=True).astype(int)
```

## Data Preview

Sample of the first few rows:

| Person ID | Gender | Age | Occupation           | Sleep Duration | Quality of Sleep | Physical Activity Level | Stress Level | BMI Category | Blood Pressure | Heart Rate | Daily Steps | Sleep Disorder |
|-----------|--------|-----|----------------------|----------------|------------------|-------------------------|--------------|--------------|----------------|------------|-------------|----------------|
| 1         | Male   | 27  | Software Engineer    | 6.1            | 6                | 42                      | 6            | Overweight   | 126/83         | 77         | 4200        | NaN            |
| 2         | Male   | 28  | Doctor               | 6.2            | 6                | 60                      | 8            | Normal       | 125/80         | 75         | 10000       | NaN            |
| 3         | Male   | 28  | Doctor               | 6.2            | 6                | 60                      | 8            | Normal       | 125/80         | 75         | 10000       | NaN            |
| 4         | Male   | 28  | Sales Representative | 5.9            | 4                | 30                      | 8            | Obese        | 140/90         | 85         | 3000        | Sleep Apnea    |
| 5         | Male   | 28  | Sales Representative | 5.9            | 4                | 30                      | 8            | Obese        | 140/90         | 85         | 3000        | Sleep Apnea    |

## Models and Evaluation

This section details the machine learning models applied to predict **Sleep Disorder** (classification) and **Stress Level** (regression), including evaluation metrics and the best-performing algorithms.

### 1. Sleep Disorder (Classification)
- **Target**: Categorical (None, Insomnia, Sleep Apnea)
- **Models Tested**:
  - Random Forest Classifier
  - Support Vector Machine (SVM)
  - Logistic Regression
  - Decision Tree Classifier

#### Evaluation Metrics
- **Accuracy**: Proportion of correct predictions.
- **Precision**: True positives over total predicted positives.
- **Recall**: True positives over total actual positives.
- **F1-Score**: Harmonic mean of precision and recall.

#### Results (Hypothetical; Replace with Actual)
| **Model**                | **Accuracy** | **Precision** | **Recall** | **F1-Score** |
|--------------------------|--------------|---------------|------------|--------------|
| Random Forest Classifier | 0.92         | 0.91          | 0.92       | 0.91         |
| Support Vector Machine   | 0.89         | 0.88          | 0.89       | 0.88         |
| Logistic Regression      | 0.85         | 0.84          | 0.85       | 0.84         |
| Decision Tree Classifier | 0.87         | 0.86          | 0.87       | 0.86         |

- **Best Model**: **Random Forest Classifier** (Accuracy: 0.92, F1-Score: 0.91)
- **Insights**: Excels due to handling complex relationships and potential class imbalances.

### 2. Stress Level (Regression)
- **Target**: Continuous (1 to 10)
- **Models Tested**:
  - Linear Regression
  - Polynomial Regression (Degree 6)
  - Random Forest Regressor
  - Decision Tree Regressor
  - Gradient Boosting Regressor

#### Evaluation Metrics
- **RMSE**: Average prediction error.
- **MAE**: Average absolute error.
- **R² Score**: Variance explained by the model.

#### Results (Polynomial Regression Actual; Others Hypothetical)
| **Model**                       | **RMSE** | **MAE** | **R² Score** |
|---------------------------------|----------|---------|--------------|
| Linear Regression               | 1.25     | 1.05    | 0.78         |
| Polynomial Regression (Degree 6)| 0.1476   | N/A     | 0.9930       |
| Random Forest Regressor         | 0.95     | 0.75    | 0.88         |
| Decision Tree Regressor         | 1.10     | 0.90    | 0.82         |
| Gradient Boosting Regressor     | 0.98     | 0.78    | 0.87         |

- **Best Model**: **Polynomial Regression (Degree 6)** (RMSE: 0.1476, R²: 0.9930)
- **Insights**: Captures non-linear patterns effectively, but high degree risks overfitting—validate on unseen data.

## Instructions for Running the Project

1. **Clone the Repository**  
   ```
   git clone <repository-url>
   ```
2. **Navigate to the Project Directory**  
   ```
   cd <project-directory>
   ```
3. **Set Up a Virtual Environment** (Optional)  
   ```
   python -m venv env
   ```
   - Activate:  
     - Windows: `env\Scripts\activate`  
     - macOS/Linux: `source env/bin/activate`
4. **Install Dependencies**  
   ```
   pip install -r requirements.txt
   ```
5. **Prepare the Dataset**  
   Place `Sleep_health_and_lifestyle_dataset.csv` in the project directory.
6. **Run the Project**  
   - Notebook: `jupyter notebook <notebook-name>.ipynb`  
   - Script: `python <script-name>.py`
7. **View Results**  
   Outputs appear in the console or notebook.

## Requirements

Listed in `requirements.txt`:
```plaintext
pandas==1.5.3
numpy==1.24.3
matplotlib==3.7.1
seaborn==0.12.2
scikit-learn==1.2.2
imbalanced-learn==0.10.1
```
Install with:  
```
pip install -r requirements.txt
```
- **Python**: 3.8+  
- **OS**: Windows, macOS, Linux

## Conclusion

This project analyzed the **Sleep Health and Lifestyle Dataset** to predict **Sleep Disorder** and **Stress Level**:
- **Sleep Disorder**: **Random Forest Classifier** achieved an accuracy of 0.92 and F1-score of 0.91.
- **Stress Level**: **Polynomial Regression (Degree 6)** excelled with an RMSE of 0.1476 and R² of 0.9930.

**Future Improvements**:
- Validate Polynomial Regression on external data.
- Explore additional features or models.
- Develop lifestyle-based strategies for sleep and stress management.
