# 🧠 Stroke Prediction Using Machine Learning
This project uses machine learning to predict the likelihood of a person having a stroke based on medical and lifestyle features. It demonstrates how data science can support early detection and prevention efforts in healthcare using accessible and structured data.


# 📌 Introduction
Stroke is a leading cause of death and disability worldwide. Early identification of high-risk individuals is critical to prevention. This project builds a machine learning classification model that predicts stroke risk based on patient data such as age, hypertension, heart disease, BMI, etc.

Leveraging supervised learning and model evaluation techniques, I aim to create a pipeline for clinical decision support systems or health screening.

# 🧾 Dataset
The dataset used is the 'Stroke Prediction Dataset' publicly available. It has 11 features, with a binary target variable (0 = 'no stroke', 1 = 'stroke')

# Methodology
### Data Cleaning and Preprocessing
Dropped rows containing null and/or inconsistent values.
Categorical features were encoded using one-hot encoding.

### Exploratory (Statistical) Data Analysis (EDA)
Conducted independent t-tests on some features to determine if they significantly affected the target variable.

### Model Selection and Training
The dataset was normalized, then split into train and test sets. A Logistic Regression model was then fit to the trainin set and used to make predictions on the test set data.
For the final prediction, a lower threshold probability was set and used to predict. This was to handle the overhwelming class imbalance present in the data.

### Some Background Considerations
The data set has a high degree of class imbalance in the target variable, hence using models like the RandomForest Classifier (which i tested first) produce results with very high accuracy but basically no positive recall and precision. In healthcare, as in this case, accuracy can be a misleading metric to use in assessing model performance. Due to the high class imbalance, the model could basically predict the majority class ('no stroke' in this case) and still get a high accuracy. This model would be basically useless though because what is needed is for it to predict the positive class ('stroke') so that clinical decisions could be taken to prevent it. Hence, precision and recall must be maximized for, even if it is at the expense of accuracy.
At the end, i chose the Logistic Regressor and manually reset the threshold probability to predict a positive class. This improved the positive precision and recall of the model at the expense of accuracy (which is really not of much importance here).

### Model Evaluation
Model was evaluated using a classification report including precision, recall, etc.

# How to Use
1. Clone the repository
2. Open the notebook in Google Colab. Upload the notebook to your Google Colab environment.
3. Instanll dependencies/missing libraries if required
4. Run the notebook sequentially. Take note that you can set the threshold probability to whatever value you want in the model selection and training section.
5. Customize the code to experiment with different model architectures, hyperparameters or datasets.

# Disclaimer
This project is for educational and research purposes only. It is not intended to be used for clinical diagnosis.

Contact me at chibuikemofobuike@gmail.com
