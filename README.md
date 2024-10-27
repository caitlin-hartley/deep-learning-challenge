# deep-learning-challenge

![nn](https://github.com/caitlin-hartley/deep-learning-challenge/blob/main/images/News_Image_(47).png)

## Report:

### Data Preprocessing

* Target Variable:
  - IS_SUCCESSFUL: This binary variable indicates whether the applicant was successful (1) or not (0)

* Feature Variable(s):
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
 
---

### Compiling, Training, and Evaluating the Model

Model 1:
* Layers: 3 layers (1 input layer, 2 hidden layers, 1 output layer)
* Neurons:
  * Hidden Layer 1: 8 neurons
  * Hidden Layer 2: 5 neurons
* Activation Functions: ReLU for hidden layers, Sigmoid for output layer.

* Reasoning: ReLU helps speed up training, while Sigmoid is ideal for binary classification tasks.

--- 

Model 2:
* Layers: 4 layers (1 input layer, 3 hidden layers, 1 output layer)
* Neurons:
  * Hidden Layer 1: 16 neurons
  * Hidden Layer 2: 12 neurons
  * Hidden Layer 3: 8 neurons
  * Hidden Layer 4: 5 neurons
* Activation Functions: ReLU and Tanh for hidden layers, Sigmoid for output layer.

* Reasoning: More neurons in the first two layers give the model a better chance to learn complex patterns. I included Tanh to see if it could capture any non-linear relationships more effectively.



---
  
Model 3:
* Layers: 4 layers (1 input layer, 3 hidden layers, 1 output layer)
* Neurons:
  * Hidden Layer 1: 16 neurons
  * Hidden Layer 2: 8 neurons
  * Hidden Layer 3: 4 neurons
*Activation Functions: ReLU for hidden layers, Sigmoid for output layer.

* Reasoning: This model aims to maintain complexity while testing a more compact architecture with fewer neurons in the later layers.
---

Model 4:
* Layers: 3 layers (1 input layer, 2 hidden layers, 1 output layer)
* Neurons:
  * Hidden Layer 1: 8 neurons
  * Hidden Layer 2: 5 neurons
  * Activation Functions: Sigmoid for hidden layers, Sigmoid for output layer.

Reasoning: I wanted to see how Sigmoid in the hidden layers would affect performance, even though it might slow down learning and reduce capacity.

--- 

Performance Results
Achieved Accuracies:
* Model 1: 72.43%
* Model 2: 72.56%
* Model 3: 72.62%
* Model 4: 72.43%

Unfortunately, I didn’t hit the target accuracy of 75%. The best performance was 72.62% with Model 3, suggesting that the current architectures and hyperparameters aren’t fully capturing the data patterns needed for better predictions.

---

Steps Taken to Increase Model Performance:

* Layer and Neuron Adjustments: Tried different configurations to see what worked best.
* Activation Functions: Experimented with various activation functions (ReLU, Tanh, Sigmoid) to find the right fit.
* Epochs: Increased training epochs to give the model more learning time.
* Data Preprocessing: Scaled input features, bucketed income amounts, and adjusted cutoffs for application types.

Overall, the models performed consistently between 72.43% and 72.62%. Despite efforts to adjust architecture and functions, I didn’t see significant improvements in accuracy.

--- 

Recommendation:

To boost classification performance, I suggest trying a random forest model. This approach combines multiple decision trees, which can enhance prediction accuracy and help control overfitting. It’s particularly effective for categorical features and can also provide insights into feature importance.
