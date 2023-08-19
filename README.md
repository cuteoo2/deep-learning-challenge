# deep-learning-challenge


**Overview**

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. This project was done to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

Neural net deep learning model as used to make a binary prediction of funding success based on a sample size of approximately 34,000 organizations that have received funding from Alphabet Soup over the years. 

The data was preprocessed to get rid of unnecessary columns, bin rare variable values, and convert categorical data to numeric for the purpose of modeling.

Tensorflow Keras was used to build and compile a neural net model based on the number of features with the number of layers and neurons set to attempt to generate highly accurate result.

As the initial model fell slightly below 75% accuracy, 3 more attempts were made to optimize the model and increase its accuracy.




**Results**



- Preprocessing


The only target variable in the dataset is IS_SUCCESSFUL.
The features which contribute to the analysis include: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT.
EIN and NAME are both identifications for the specific businesses that received funding in the past. As such, they do not contribute directly to the success of the funding and therefor are neither targets nor features.


- Compiling, Training, and Evaluating the Model



The model was built with 3 hidden layers because there was a relatively high number of input dimensions, namely 39-43 depending on which setup I was running, with a later modification to 4 layers having little impact on the model's accuracy.
For the number of neurons, I went with the rule-of-thumb stating that the number should be less than twice the size of the input layer, with that leading to the number of 80 neurons for the first layer. For the second hidden layer, I went with 30 to be somewhat fewer than the number of inputs. For the output layer I chose 1 to match the number of target dimensions.
I used ReLU as the method for both hidden layers and sigmoid for the output layer due to being faimiliar with them from previous experience.
The model was unable to reach the target accuracy of 75% in any of my attempts. The peak value was ~73% with all other attempts being virtually identical.
I attempted 3 different methods to increase the performance of my model.
First, I tried adding another hidden layer between my two original hidden layers with 60 neurons.
Second, I tried doubling the number of neurons in each hidden layer.
Third, I tried dropping the STATUS and SPECIAL_CONSIDERATIONS variables from the data to see if they were confusing the analysis.
None of these methods yielded positive results.



**Summary:**


On the whole, while the model never reached the target accuracy of 75%, it did come quite close at 73% for the best iteration.
One issue was the lack of any real impact from the attempted optimization methods for the model. It may have worked better to commit to using Tensorflow's Keras Tuner library to more rigorously examine the effects of varying the hyperparameters.
It is also possible that some of the other feature variables may have been able to be dropped to improve model accuracy. Determining which variables are more valuable to preidicting funding success would take a more rigorous investigation than was possible on the scale of this project.
As for whether some other type of model would be more appropriate for creating a binary classifier for investment success, I can't come up with one.
