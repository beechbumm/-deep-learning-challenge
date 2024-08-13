# Alphabet Soup Charity Success Predictor

## Overview
Alphabet Soup, a nonprofit foundation, seeks a tool to help select applicants for funding who have the best chance of success in their ventures. Using machine learning and neural networks, I have developed a binary classifier to predict the likelihood of success for applicants funded by Alphabet Soup.

### Project Objective
The goal of this project is to build and optimize a deep learning model using the Alphabet Soup dataset to predict the success of charity donations, with a target predictive accuracy of over 75%.

## Dataset
The dataset provided by Alphabet Soup contains over 34,000 records of organizations that have received funding. The key columns in the dataset include:

- **EIN** and **NAME**: Identification columns
- **APPLICATION_TYPE**: Type of application submitted to Alphabet Soup
- **AFFILIATION**: Affiliated industry sector
- **CLASSIFICATION**: Government organization classification
- **USE_CASE**: Purpose for which the funding is requested
- **ORGANIZATION**: Type of organization
- **STATUS**: Organization's operational status
- **INCOME_AMT**: Income classification of the organization
- **SPECIAL_CONSIDERATIONS**: Any special considerations for the application
- **ASK_AMT**: Amount of funding requested
- **IS_SUCCESSFUL**: Binary indicator of whether the funding was successfully utilized

## Analysis

### Data Preprocessing
- **Target Variable**: The `IS_SUCCESSFUL` column serves as the target variable, indicating whether a donation was successful.
- **Feature Variables**: All other columns are used as features to predict the success of donations.
- **Removed Variables**: The `EIN` and `NAME` columns were removed as they do not contribute to the prediction model.

### Model Development
#### Neural Network Architecture
The deep learning model consists of the following layers:
1. **First Hidden Layer**: 80 neurons, ReLU activation function
2. **Second Hidden Layer**: 30 neurons, ReLU activation function
3. **Output Layer**: 1 neuron, Sigmoid activation function

#### Training and Evaluation
- **Target Performance**: The model aimed to achieve an accuracy of at least 75%. Despite various optimization attempts, the highest accuracy obtained was approximately 72.76%.
- **Optimization Attempts**:
  - Adjusted input data by dropping irrelevant columns and binning categorical variables with rare occurrences.
  - Increased model complexity by adding more neurons and layers.
  - Tested different activation functions for hidden layers.
  - Adjusted training parameters, including increasing the number of epochs to 300, setting batch size to 32, and using a 20% validation split.

### Results
The final model achieved an accuracy of approximately 72.76%, falling short of the target accuracy of 75%.

## Further Considerations

### Alternative Model: Random Forest
Given the complexity of the dataset and the limitations of the neural network, a Random Forest model may be a better alternative. 

#### Why Random Forest?
- **Robustness to Overfitting**: As an ensemble method, Random Forest combines predictions from multiple decision trees, reducing overfitting.
- **Interpretability**: Easier to interpret, with clear insights into feature importance and decision-making processes.
- **Handling of Categorical Variables**: Effectively handles categorical variables with minimal preprocessing.
- **Less Tuning Required**: Requires fewer hyperparameter adjustments compared to neural networks.
- **Performance on Tabular Data**: Generally performs well on tabular data, capturing complex relationships between features and the target variable.

#### Implementation Steps
1. **Preprocessing**: Drop irrelevant columns and label encode categorical variables.
2. **Model Training**: Train a Random Forest classifier with a fixed number of trees, such as 100.
3. **Evaluation**: Assess model performance using accuracy, precision, and recall.
4. **Feature Importance**: Analyze feature importance scores to identify the most influential variables.

## Summary
Despite various optimization strategies, the deep learning model did not meet the desired accuracy. Exploring alternative models like Random Forest could potentially yield better results. Random Forest offers robustness, interpretability, and strong performance with tabular data, making it a promising approach for this problem.

