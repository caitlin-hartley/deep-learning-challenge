# deep-learning-challenge

![nn](https://github.com/caitlin-hartley/deep-learning-challenge/blob/main/images/News_Image_(47).png)

## Report:

### Data Preprocessing

* Target Variable:
  - IS_SUCCESSFUL: This binary variable indicates whether the applicant was successful (1) or not (0)

*Feature Variable(s):
  - APPLICATION_TYPE: The type of application submitted
  - AFFILIATION: The affiliation of the organization
  - CLASSIFICATION: Classification codes representing the type of organization
  - USE_CASE: The intended use of funds by the organization
  - STATUS: The current status of the organization
  - INCOME_AMT: Income ranges of the organizations (converted to numerical values)
  - ASK_AMT: The amount of funding requested by the organization
    
* Variables to be Removed:
  - EIN: This identifier does not contribute to the predictive power of the model
  - NAME: The name of the organization is also not useful for predictions
 

### Compiling, Training, and Evaluating the Model

Models

---

Model 1:
* Layers: 3 layers (1 input layer, 2 hidden layers, 1 output layer)
* Neurons:
  * Hidden Layer 1: 8 neurons
  * Hidden Layer 2: 5 neurons
* Activation Functions: ReLU for hidden layers, Sigmoid for output layer.

* Reasoning: The selection of ReLU activation for the hidden layers is based on its ability to facilitate faster training. The output layer used Sigmoid because it is suitable for binary classification tasks.

--- 

Model 2:
* Layers: 4 layers (1 input layer, 3 hidden layers, 1 output layer)
* Neurons:
  * Hidden Layer 1: 16 neurons
  * Hidden Layer 2: 12 neurons
  * Hidden Layer 3: 8 neurons
  * Hidden Layer 4: 5 neurons
* Activation Functions: ReLU and Tanh for hidden layers, Sigmoid for output layer.

* Reasoning: The larger number of neurons in the first two hidden layers allows for greater capacity to learn complex patterns. Tanh was included for the second hidden layer to capture potential non-linearities more effectively, while Sigmoid in the output layer remains appropriate for binary classification.

---
  
Model 3:
* Layers: 4 layers (1 input layer, 3 hidden layers, 1 output layer)
* Neurons:
  * Hidden Layer 1: 16 neurons
  * Hidden Layer 2: 8 neurons
  * Hidden Layer 3: 4 neurons
*Activation Functions: ReLU for hidden layers, Sigmoid for output layer.

* Reasoning: This model's structure maintains a similar design to Model 2, but with fewer neurons in the later layers to investigate if a more compact architecture could perform better.

---

Model 4:
* Layers: 3 layers (1 input layer, 2 hidden layers, 1 output layer)
* Neurons:
  * Hidden Layer 1: 8 neurons
  * Hidden Layer 2: 5 neurons
  * Activation Functions: Sigmoid for hidden layers, Sigmoid for output layer.

Reasoning: This model was tested with Sigmoid activation in the hidden layers to explore if it would impact performance differently compared to ReLU. However, it was expected that this choice may lead to slower convergence and potential issues with learning capacity.

--- 

Performance Results
Achieved Accuracies:
* Model 1: 72.43%
* Model 2: 72.56%
* Model 3: 72.62%
* Model 4: 72.43%

The target accuracy of 75% was not achieved. The best performance was 72.62% with Model 3, indicating that the current architectures and hyperparameters do not fully capture the underlying patterns in the data necessary for improved predictive accuracy.

---

Steps Taken to Increase Model Performance:

* Layer and Neuron Adjustments: Experimented with various configurations for the number of layers and neurons per layer to find the optimal architecture.
* Activation Functions: Utilized different activation functions (ReLU, Tanh, Sigmoid) to assess their impact on the model's ability to learn complex patterns.
* Epochs: Increased the number of training epochs to allow the model more time to learn from the training data.
* Data Preprocessing: Applied scaling techniques to standardize input features, bucketed income amts, and changed cutoff value for application type. 
* Model Evaluation: Continuously evaluated models against a validation dataset to monitor overfitting and generalization.

The models demonstrated a consistent performance in the range of 72.43% to 72.62% accuracy across various configurations. While adjustments to the architecture and activation functions were made, they did not yield a significant increase in model performance.

--- 

Recommendation:

To improve the classification performance further, I recommend exploring the random forest model. This model combines multiple decision trees to improve prediction accuracy and control overfitting. It is particularly effective for handling categorical features and can offer insight into feature importance.

