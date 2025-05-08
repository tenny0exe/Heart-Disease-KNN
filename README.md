# Heart Disease Prediction using Logistic Regression
This notebook demonstrates a logistic regression model to predict heart disease based on various health indicators. Let me break down the key components and analysis:

Data Overview
The dataset contains 1,025 records with 14 features related to heart health:

Demographics: age, sex

Medical indicators:

cp (chest pain type)

trestbps (resting blood pressure)

chol (serum cholesterol)

fbs (fasting blood sugar)

restecg (resting electrocardiographic results)

thalach (maximum heart rate achieved)

exang (exercise induced angina)

oldpeak (ST depression induced by exercise relative to rest)

slope (slope of peak exercise ST segment)

ca (number of major vessels colored by fluoroscopy)

thal (thalium stress test result)

Target: presence of heart disease (0 = no, 1 = yes)

Data Preprocessing
Initial Cleaning:

Removed 723 duplicate rows (keeping only unique records)

Dropped rows where 'ca' = 4 (invalid value)

Recoded 'ca' values (0→3, 1→2, 2→1, 3→0)

Feature Engineering:

Created normalized versions of several features:

normalized_age (from 'ca' values)

normalized_chol (binned cholesterol levels)

normalized_trestbps (binned blood pressure)

normalized_thalach (standard scaled)

normalized_oldpeak (standard scaled)

Train-Test Split:

80% training data (238 samples)

20% test data (60 samples)

Model Implementation
The notebook implements logistic regression in two ways:

1. Manual Implementation
Key components:

Sigmoid function: Converts linear outputs to probabilities

Cost function: Binary cross-entropy loss

Gradient descent: Updates weights to minimize cost

Training: 10,000 iterations with learning rate 0.00001

2. Scikit-learn Implementation
Using sklearn's LogisticRegression with default parameters

Results
Manual Implementation Accuracy: ~80%

Scikit-learn Accuracy: 80%

Analysis
Data Quality:

The dataset had significant duplicates (723 out of 1025)

Some features like 'ca' required cleaning (removing invalid value 4)

No missing values found

Feature Engineering:

Normalization helps models converge faster

Binning continuous variables can help capture non-linear relationships

Standard scaling (for thalach and oldpeak) centers data around 0 with unit variance

Model Performance:

Both implementations achieved similar accuracy (80%)

The cost function plot shows the manual implementation successfully reduced loss over iterations

Performance suggests the model learned meaningful patterns

Potential Improvements:

Try different learning rates or optimization algorithms

Experiment with feature selection/dimensionality reduction

Consider more complex models if higher accuracy is needed

Add regularization to prevent overfitting

Key Takeaways
The logistic regression model shows decent predictive power for heart disease

Careful data cleaning and preprocessing was crucial

Manual implementation helps understand the underlying math

Scikit-learn provides a convenient, optimized implementation

80% accuracy is a good baseline that could potentially be improved
