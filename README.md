# deep-learning-challenge - README
# Module 21 Neural Networks and Deep Learning

## Overview
This project aims to develop a binary classifier using neural networks to help Alphabet Soup, a nonprofit foundation, identify funding applicants with the highest likelihood of success. The model analyzes metadata from over 34,000 past funded organizations to predict whether future funding will be used effectively.

## Repository Structure
```
deep-learning-challenge/
│
├── DeepLearningCode.ipynb # Initial model notebook
├── AlphabetSoupCharity.h5 # Initial model weights
├── AlphabetSoupCharity_Optimization.ipynb # Optimized model notebook
├── AlphabetSoupCharityOptimization.h5 # Optimized model weights
├── Alphabet Soup Neural Network Model Report.pdf # Analysis report
├── charity_data.csv # Dataset
├── LICENSE # License file
└── README.md # Project documentation

## Steps Performed

### STEP 1. Data Preprocessing
- Dataset: charity_data.csv (34,000+ funded organizations)
- Target (y): IS_SUCCESSFUL (1 = effective, 0 = ineffective)
- Features (X): APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, etc.
- Processing steps:
  - Dropped EIN and NAME columns
  - Binned rare categorical values
  - One-hot encoded categorical variables
  - Scaled features using StandardScaler
  - Split data: 75% training, 25% testing

### STEP 2. Neural Network Model
- Initial Model Architecture:
  - Input layer (scaled features)
  - Hidden Layer 1: 80 neurons, ReLU activation
  - Hidden Layer 2: 30 neurons, ReLU activation
  - Output Layer: 1 neuron, Sigmoid activation
- Training: 50 epochs
- Initial Accuracy: 72.8 %

### STEP 3. Model Optimization
- Modifications:
  - Increased binning for rare categories
  - Expanded network architecture:
    - Hidden Layer 1: 10 neurons
    - Hidden Layer 2: 64 neurons  
    - Hidden Layer 3: 32 neurons
  - Increased training to 75 epochs
- Optimized Accuracy: 73.1% ( increased by 0.3% , but did not exceed the 75% target)

## Results

### Model Performance
- **Initial Model:**
  - Test Accuracy: 72.8%
  - Loss: 0.55

- **Optimized Model:**
  - Test Accuracy: 73.1%
  - Loss: 0.55

### Key Findings
1. The optimized neural network achieved 73.1% accuracy in predicting funding success
2. Model improvements came from:
   - Better handling of categorical data
   - Increased network depth and complexity
   - Extended training duration
3. The model shows potential but may benefit from alternative approaches

## Technologies & Methods
- **Python Libraries:**
  - pandas, numpy for data processing
  - sklearn for preprocessing (StandardScaler, train_test_split)
  - tensorflow/keras for neural network implementation

- **Machine Learning Techniques:**
  - Neural network architecture design
  - Binary classification with sigmoid output
  - Hyperparameter tuning
  - Model evaluation metrics (accuracy, loss)

## Recommendations
While the neural network achieved the target accuracy, alternative models may perform better since 72 -75% accuracy is not accurate enough to make fair descisions. It might help sift through the applicats to start, however, greater human involvement , ir the use of other methods such as the following, is recomended:
1. **Random Forest or XGBoost:** Often more effective for structured tabular data
2. **Feature Engineering:** Deeper analysis of feature importance
3. **AutoML:** Platforms like H2O.ai for automated model optimization

## Code source
Columbia University Activities for module 21
Deep Seek
Chat GBT

## License
General Public License