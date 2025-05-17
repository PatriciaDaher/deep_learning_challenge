# Alphabet Soup Neural Network Model Report

## OVERVIEW
With the goal to support the Non-Profit Organization Alphabet Soup in optimizing the distribution of funds, the aim is to build a predictive tool that identifies the applicants who are likely to be successful if funded. 
To achieve this goal, I create a binary classification model using deep learning and neural networks to classify metadata for over 34,000 organizations that have received funding from Alphabet Soup over the years. The classification considers the following features:
APPLICATION_TYPE—Alphabet Soup application type
AFFILIATION—Affiliated sector of industry
CLASSIFICATION—Government organization classification
USE_CASE—Use case for funding
ORGANIZATION—Organization type
STATUS—Active status
INCOME_AMT—Income classification
SPECIAL_CONSIDERATIONS—Special considerations for application
ASK_AMT—Funding amount requested
IS_SUCCESSFUL—Was the money used effectively
The analysis involved the following steps:
Step 1: Preprocessing the data to prepare it for modeling
Step 2: Building and evaluating a neural network for binary classification
Step 3: Optimizing the model to “hopefully” achieve an accuracy above 75%


# RESULTS

## A- Data Processing:
### Target variable: 
A binary variable indicating if an organization’s funding was used effectively (1-Yes, 0= No)
### Feature Variable: 
All columns except for and EIN, NAME, IS_SUCCESFUL
### Variables Removed: 
EIN and NAME because they are identification columns
IS_SUCCESFUL is separated as the target 
### Other Processing Techniques:
Combined rare categories in APPLICATION_TYPE and CLASSIFICATION into”Other” to reduce dimensionality. 
Used pd.get_dummies() to one-hot encode categorical features.
Scaled all numeric features using StandardScaler.
## B- Compiling, Training, and Evaluating the Model
### Initial Model:
Neural Network Architecture:
1- Input: Scaled features (based on dummies + numeric features)
2- Hidden Layer 1: 80 neurons relu activation
3- Hidden Layer2: 30 neurons relu activation
4- Output Layer: 1 neuron, sigmoid activation
Results:
	1- Epochs:50
	2- Test Accuracy: Approx 72%
	3- Model did not meet the 75% accuracy goal
### Optimized Model:
Modifications:
	1-  Increased category binning (cutoff from 500 to 100) to better group rare categories
	2 - Expanded model depth and complexity:
		a - Hidden layer 1: 128
		b - Hidden layer 2: 64
		c - Hidden layer 3: 32
	3- Increased training epochs from 50 to 150
Results:
	1- Test accuracy approx 77%
	2- The model met the 75% target performance

# SUMMARY
After processing and testing several neural network architectures, I successfully improved the model to exceed the 75% accuracy threshold.
## A- The improvements were achieved through:
Better encoding of categorical variables
Expanding and deepening the neural network.
Training the model for more epochs.
## B - Recommendation:
Although a deep neural network achieved reasonable accuracy, tabular data like this is often better handled by traditional machine learning models such as:
	1- Random Forrest
	2- Gradient Boosting (e.g. XGBoost or LightGBM)
	3- AutoML platforms (e.g. Google AutoML or H2O.ai
These models are often more interpretable and can in most cases outperform neural networks on structured datasets. For further analysis and feature importance insights, i recommend testing with XGBoost, which also handles missing and categorical data effectively. 
